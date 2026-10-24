# Pub/Sub

> **Level:** Basic · **Topic:** [Events and integration](../README.md) · **Cited in:** 6 practice-exam questions

## What it is

Asynchronous messaging that decouples producer and consumer and absorbs traffic spikes.

## Trigger

"traffic spikes that must not overwhelm processing" ([E1Q16](../../99-practice-exams/exam-1.md#q16)). Destination of a log sink for a SIEM or external SaaS ([E2Q47](../../99-practice-exams/exam-2.md#q47), [E6Q10](../../99-practice-exams/exam-6.md#q10)). Destination of budget notifications ([E2Q33](../../99-practice-exams/exam-2.md#q33), [E2Q42](../../99-practice-exams/exam-2.md#q42)).

## Command

`gcloud pubsub subscriptions pull NAME --auto-ack` ([E1Q46](../../99-practice-exams/exam-1.md#q46)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q16](../../99-practice-exams/exam-1.md#q16) | ArcadeWave operates an online gaming platform that receives match-result events from millions of players. Even... |
| [E1Q46](../../99-practice-exams/exam-1.md#q46) | ParcelPulse uses Pub/Sub to process shipment status events. A pull subscription named tracking-worker is conne... |
| [E2Q33](../../99-practice-exams/exam-2.md#q33) | BrightCart is launching an online storefront on a Compute Engine VM. The company has created a monthly Cloud B... |
| [E2Q42](../../99-practice-exams/exam-2.md#q42) | LedgerLoop operates many independent Google Cloud projects for its financial analytics teams. Each project has... |
| [E2Q47](../../99-practice-exams/exam-2.md#q47) | HealthAxis operates a patient analytics platform backed by a Bigtable instance with five nodes. The tables con... |
| [E6Q10](../../99-practice-exams/exam-6.md#q10) | BluePeak Media operates workloads across Google Cloud and other cloud providers. The company uses an external ... |

## Official documentation

- [Logging / Pub/Sub](https://docs.cloud.google.com/logging/docs/export/pubsub)
- [Pub/Sub / Overview](https://docs.cloud.google.com/pubsub/docs/overview)
- [Pub/Sub / Publish receive messages gcloud](https://docs.cloud.google.com/pubsub/docs/publish-receive-messages-gcloud)
- [Pub/Sub / Subscription overview](https://docs.cloud.google.com/pubsub/docs/subscription-overview)
- [Pub/Sub / Use with cloud function triggers](https://docs.cloud.google.com/pubsub/docs/use-with-cloud-function-triggers)
- [SDK / Pull](https://docs.cloud.google.com/sdk/gcloud/reference/pubsub/subscriptions/pull)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
