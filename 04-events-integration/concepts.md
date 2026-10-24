# Events and integration: concepts from basic to advanced

> Official exam guide sections covered: 3.3 (see the [exam guide map](../00-start-here/exam-guide-map.md)).

## Basic

### Synchronous vs asynchronous

- **Synchronous**: the caller sends a request and waits for the response (HTTP call to a service). Simple, but the caller is blocked and a slow or failing callee affects it. Traffic spikes hit the callee directly.
- **Asynchronous**: the sender hands a message or event to an intermediary and moves on. The receiver processes it later, at its own pace. This **decouples** producer and consumer, absorbs spikes, and allows retries.

The tools on this page cover different async needs:

| Need | Tool |
|---|---|
| Decouple services, fan out, absorb bursts | Pub/Sub |
| React to something that happened in Google Cloud | Eventarc, Cloud Storage notifications |
| Run something on a schedule (cron) | Cloud Scheduler |
| Dispatch individual work items with rate control and retries | Cloud Tasks |

### Pub/Sub core concepts

- **Topic**: a named channel that publishers send messages to.
- **Subscription**: attached to one topic; each subscription gets its own copy of every message. Several subscriptions on one topic mean fan-out. Several subscribers on **one** subscription share the work.
- **Message**: data plus attributes. Delivery is **at-least-once**, so consumers should be idempotent.
- **Acknowledgement (ack)**: the subscriber confirms processing. If no ack arrives within the **ack deadline**, Pub/Sub redelivers.

```bash
gcloud pubsub topics create orders
gcloud pubsub subscriptions create orders-sub --topic=orders --ack-deadline=30
gcloud pubsub topics publish orders --message='{"id": 42}' --attribute=type=new
gcloud pubsub subscriptions pull orders-sub --auto-ack --limit=5
```

## Intermediate

### Pull vs push subscriptions

| | Pull | Push |
|---|---|---|
| Who initiates | Subscriber requests messages | Pub/Sub sends an HTTPS POST to an endpoint |
| Good for | Workers you control, high throughput, batch consumers | Cloud Run services, webhooks, serverless endpoints |
| Ack | Explicit ack call | A success HTTP response (2xx) acknowledges |
| Auth | IAM on the subscription | Optional OIDC token from a service account that the endpoint verifies |

There are also export subscriptions that write straight to **BigQuery** or **Cloud Storage** with no code.

```bash
gcloud pubsub subscriptions create orders-push --topic=orders \
  --push-endpoint=https://my-svc-abc123-uc.a.run.app/handle \
  --push-auth-service-account=pusher@my-project.iam.gserviceaccount.com
```

### Retention, replay, and expiry

- Unacknowledged messages are kept per subscription for the **message retention duration** (default 7 days, configurable up to 31 days).
- A subscription can optionally **retain acknowledged messages** so you can **seek** to a timestamp or snapshot and replay (`gcloud pubsub subscriptions seek`).
- A topic can also retain messages, so new subscriptions can read history.
- Subscriptions that stay inactive for a long period (31 days by default) can expire.

### Roles

`roles/pubsub.publisher` (publish), `roles/pubsub.subscriber` (consume), `roles/pubsub.viewer`, `roles/pubsub.editor`, `roles/pubsub.admin`. Grant them on the specific topic or subscription.

## Advanced

### Dead-letter topics, retry, and ordering

- A **dead-letter topic** receives messages that could not be processed after a maximum number of delivery attempts (configurable, default 5). It prevents one poison message from looping forever. The Pub/Sub service agent needs publisher rights on the dead-letter topic and subscriber rights on the source subscription.
- **Retry policy**: choose immediate redelivery or exponential backoff between attempts.
- **Ordering**: set an **ordering key** when publishing and enable message ordering on the subscription. Messages with the same key are delivered in order. There is no global ordering across keys.
- **Exactly-once delivery** can be enabled on pull subscriptions when duplicates are unacceptable; otherwise design for at-least-once.
- **Filters** on a subscription deliver only messages whose attributes match.

```bash
gcloud pubsub topics create orders-dead
gcloud pubsub subscriptions create orders-sub2 --topic=orders \
  --dead-letter-topic=orders-dead --max-delivery-attempts=5 \
  --enable-message-ordering --message-filter='attributes.type="new"'
gcloud pubsub topics publish orders --message=x --ordering-key=customer-1
```

### Eventarc

**Eventarc** routes events from Google Cloud sources, Pub/Sub, and some third-party sources to targets such as **Cloud Run**, GKE, or Workflows, using the CloudEvents format. Event types include direct service events (for example a Cloud Storage object finalized) and **Cloud Audit Logs** events (any audited API call). Cloud Run functions use Eventarc triggers under the hood. The trigger needs a service account with permission to invoke the target and to receive events (`roles/eventarc.eventReceiver`).

```bash
gcloud eventarc triggers create on-upload --location=us-central1 \
  --destination-run-service=processor --destination-run-region=us-central1 \
  --event-filters="type=google.cloud.storage.object.v1.finalized" \
  --event-filters="bucket=my-bucket" \
  --service-account=trigger-sa@my-project.iam.gserviceaccount.com
```

### Cloud Storage notifications

Cloud Storage can publish **Pub/Sub notifications** when objects change (event types such as `OBJECT_FINALIZE`, `OBJECT_DELETE`, `OBJECT_ARCHIVE`, `OBJECT_METADATA_UPDATE`). The Cloud Storage service agent needs `roles/pubsub.publisher` on the topic. Use this when you want messages in your own Pub/Sub pipeline; use an Eventarc or Cloud Run functions Storage trigger when you want a managed route straight to code.

```bash
gcloud storage buckets notifications create gs://my-bucket \
  --topic=uploads --event-types=OBJECT_FINALIZE
```

### Cloud Scheduler

A managed **cron** service. A job has a unix-cron schedule, a time zone, a target (HTTP/HTTPS, Pub/Sub topic, or App Engine HTTP), and an optional retry configuration. It starts things; it does not queue work or react to events. For HTTP targets inside Google Cloud, use a service account so Scheduler sends an OIDC or OAuth token.

```bash
gcloud scheduler jobs create http nightly --location=us-central1 \
  --schedule="0 2 * * *" --time-zone="Europe/London" \
  --uri="https://my-svc-abc123-uc.a.run.app/run" --http-method=POST \
  --oidc-service-account-email=sched@my-project.iam.gserviceaccount.com
gcloud scheduler jobs create pubsub tick --location=us-central1 \
  --schedule="*/5 * * * *" --topic=ticks --message-body="go"
```

A Cloud Run **job** run on a schedule uses Cloud Scheduler to trigger the job.

### Cloud Tasks

A managed **task queue** with delivery to HTTP targets (or App Engine). The producer creates tasks that name a specific target. You control **dispatch rate**, **max concurrent dispatches**, retries with backoff, and can **schedule** a task for later. Task names allow de-duplication.

```bash
gcloud tasks queues create email-queue --location=us-central1 --max-dispatches-per-second=5
gcloud tasks create-http-task --queue=email-queue --location=us-central1 \
  --url=https://my-svc-abc123-uc.a.run.app/send --body-content='{"to":"a@example.com"}'
```

### Which one to pick

| Scenario | Choose |
|---|---|
| Traffic spikes must not overwhelm the processor; many consumers | Pub/Sub |
| Upload to a bucket should trigger code | Cloud Run function or Eventarc trigger (or Pub/Sub notification) |
| React to any audited API call | Eventarc with Cloud Audit Logs |
| Run a job every night at 02:00 | Cloud Scheduler |
| Throttle calls to a rate-limited API, retry each work item | Cloud Tasks |
| Send logs or budget alerts to external or serverless consumers | Pub/Sub |
| Fan-out one event to several services | Pub/Sub (several subscriptions) |

## Exam tips

- Spikes that must not overload the processing tier: Pub/Sub. Cloud Scheduler is not a buffer.
- Cloud Scheduler triggers at a time. Cloud Tasks controls rate and retries of individual tasks. Pub/Sub decouples publishers from unknown subscribers.
- Pull for workers you control, push for Cloud Run or HTTPS endpoints.
- Unprocessable messages keep returning: add a dead-letter topic with a maximum delivery attempts value.
- In-order processing per entity: ordering keys plus enabling ordering on the subscription.
- `gcloud pubsub subscriptions pull NAME --auto-ack` reads and acknowledges messages.
- Budget notifications and log sinks to external systems use Pub/Sub as the delivery channel.
- Upload triggers a small function: Cloud Run function with a Cloud Storage trigger (Cloud Functions is now Cloud Run functions).

## What appeared on the practice exams

Condensed from the 300 practice questions. Question IDs link to the full question and explanation.

### Cloud Run, App Engine, and events

- **Cloud Run service:** HTTP, scales to zero, traffic split by revision, min-instances to reduce cold start and max-instances to limit load on the database.
- **Cloud Run jobs:** batch.
- **Events:** Pub/Sub and Eventarc.
- **Cloud Tasks / Scheduler:** scheduled or queued execution.
- **Private connection:** Direct VPC egress with ILB and private DNS.

## Official documentation
- [Pub/Sub overview](https://docs.cloud.google.com/pubsub/docs/overview)
- [Pub/Sub subscriptions](https://docs.cloud.google.com/pubsub/docs/subscription-overview)
- [Publish and receive messages with gcloud](https://docs.cloud.google.com/pubsub/docs/publish-receive-messages-gcloud)
- [Pub/Sub access control](https://docs.cloud.google.com/pubsub/docs/access-control)
- [Eventarc documentation](https://docs.cloud.google.com/eventarc/docs)
- [Cloud Storage Pub/Sub notifications](https://docs.cloud.google.com/storage/docs/pubsub-notifications)
- [Cloud Run Storage triggers](https://docs.cloud.google.com/run/docs/triggering/storage-triggers)
- [Triggering Cloud Run with Pub/Sub](https://cloud.google.com/run/docs/triggering/pubsub-triggers)
- [Executing Cloud Run jobs on a schedule](https://docs.cloud.google.com/run/docs/execute/jobs-on-schedule)
- [Triggering Cloud Run with Cloud Tasks](https://docs.cloud.google.com/run/docs/triggering/using-tasks)

[Back to topic](README.md)
