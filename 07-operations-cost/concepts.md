# Operations and cost: concepts from basic to advanced

> Official exam guide sections covered: 1.1, 1.2, 4.6 (see the [exam guide map](../00-start-here/exam-guide-map.md)).

## Basic

Google Cloud's operations suite answers four questions: how is it performing (Monitoring), what happened (Logging), who did it (Audit Logs), and what does it cost (Billing).

### Cloud Monitoring

- **Metrics** are numeric time series, for example `compute.googleapis.com/instance/cpu/utilization`. Most Google Cloud services emit metrics automatically.
- **Metrics scope:** a project can be set as a **scoping project** that shows metrics from several monitored projects in one place. Use one scoping project for a multi-project view.
- **Dashboards** chart metrics. Many services have built-in dashboards, and you can create custom ones.
- **Alerting policies** have conditions plus **notification channels** (email, SMS, Slack, PagerDuty, webhooks, Pub/Sub, mobile app). The condition has a threshold and a duration (retest window): "CPU above 80% for 7 minutes". The duration is how long the problem must persist before an incident opens.
- **Uptime checks** probe a public endpoint (HTTP, HTTPS, TCP) from several locations and can feed an alerting policy. Private resources need a private uptime check.
- **Custom metrics** (`custom.googleapis.com/...`) are written by your application through OpenTelemetry or the Monitoring API. A **log-based metric** is the alternative when the signal already exists in logs.

```bash
gcloud monitoring dashboards list
```

Alerting policies and notification channels are usually created in the console (Monitoring > Alerting) or with Terraform.

### Cloud Logging

Logging collects, stores and routes log entries from Google Cloud services, VMs and applications.

- **Logs Explorer** is the UI for viewing, filtering (Logging query language) and reading entry details. Gemini Cloud Assist can explain a selected log entry.
- **Log buckets** store entries. Each project has two by default.

| Bucket | Retention | Notes |
|---|---|---|
| `_Required` | 400 days, fixed | Admin Activity and System Event audit logs. Free. Cannot be changed or disabled. |
| `_Default` | 30 days by default, configurable | Everything else, including Data Access logs if enabled |

You can create user-defined buckets with custom retention and a chosen location.

```bash
gcloud logging read 'resource.type="gce_instance" AND severity>=ERROR' --limit=10
gcloud logging buckets update _Default --location=global --retention-days=90
```

### Cloud Audit Logs

| Type | Records | Default |
|---|---|---|
| Admin Activity | Configuration and metadata changes | Always on, cannot be disabled |
| System Event | Google-initiated system changes | Always on |
| Data Access | Reading config or reading/writing user data | **Off by default** (except BigQuery), must be enabled per service |
| Policy Denied | Access denied by a security policy | On by default |

Viewing Data Access logs requires the Private Logs Viewer role (`roles/logging.privateLogViewer`). To audit who read Cloud Storage objects, enable Data Access logs for Cloud Storage.

## Intermediate

### Log routing: sinks and filters

The **Log Router** evaluates every entry against **sinks**. A sink has a destination, an inclusion filter, and optional exclusion filters.

| Destination | Use for |
|---|---|
| Cloud Logging bucket | Central storage, Observability Analytics |
| BigQuery | SQL analysis in the cloud |
| Cloud Storage | Cheap archive, batch delay |
| Pub/Sub | Streaming to external systems (SIEM, SaaS) with the lowest delay |

Key rules:
- The sink's **writer identity** needs a write role on the destination (for example BigQuery Data Editor, Pub/Sub Publisher, Storage Object Creator).
- Sinks are not retroactive; they only route entries from the time they exist.
- An **exclusion filter** stops matching entries from being stored in the bucket, cutting ingestion cost. Excluded entries can still be routed by another sink.
- An **aggregated sink** created at a folder or organization with `--include-children` collects logs from all projects below it.

```bash
gcloud logging sinks create siem-sink \
    pubsub.googleapis.com/projects/PROJECT/topics/logs-out \
    --log-filter='severity>=WARNING'
gcloud logging sinks create org-sink storage.googleapis.com/central-logs \
    --organization=ORG_ID --include-children --log-filter='logName:"cloudaudit.googleapis.com"'
```

Sinks are managed in the Log Router. If a sink stops working, check that the service agent or writer identity still has its role.

### Log-based metrics and Observability Analytics

- **Counter** log-based metrics count matching entries. **Distribution** metrics extract numeric values (for example latency) and support percentile charts. Both feed dashboards and alerting policies.
- **Observability Analytics** (formerly Log Analytics) lets you query logs with SQL in buckets upgraded for analytics. A linked BigQuery dataset lets you join logs with other data without an export pipeline. The upgrade of a bucket is irreversible.
- **Log views** restrict who can read which logs in a bucket. Grant `roles/logging.viewAccessor` on a specific view for fine-grained access.

```bash
gcloud logging metrics create checkout-errors \
    --description="Checkout errors" \
    --log-filter='resource.type="cloud_run_revision" AND severity=ERROR AND textPayload:"checkout"'
```

### Ops Agent and Managed Service for Prometheus

- The **Ops Agent** runs on Compute Engine VMs. It collects system metrics that the hypervisor cannot see (memory, disk usage) and application logs from files. Without it, application log files never reach Logging. The VM's service account needs Logs Writer and Monitoring Metric Writer.
- **Managed Service for Prometheus** is Google's managed, Prometheus-compatible metrics store. You keep PromQL and Prometheus exporters. Collection can be managed (GKE) or self-deployed.

```bash
curl -sSO https://dl.google.com/cloudagents/add-google-cloud-ops-agent-repo.sh
sudo bash add-google-cloud-ops-agent-repo.sh --also-install
sudo systemctl status "google-cloud-ops-agent*"
```

### Seeing the health of Google Cloud

| Tool | Scope |
|---|---|
| Cloud Hub | Application-centric view of the health and operations of your own resources |
| Personalized Service Health | Google Cloud incidents and maintenance that affect your projects, with alerts via notification channels |
| Google Cloud status page | Public status of Google Cloud services, not specific to your projects |

If many things fail together and your own metrics look normal, check Personalized Service Health.

## Advanced

### Billing

- A **Cloud Billing account** pays for the usage of linked projects. A project links to one billing account at a time. Changing the link does not interrupt services.
- Billing roles: **Billing Account Administrator** (everything, including payments and IAM), **Billing Account User** (link projects), **Billing Account Costs Manager** (budgets, exports), **Billing Account Viewer** (read only), **Project Billing Manager** (link or unlink on the project side).
- To let engineers create projects without personal cards: central billing account, with `Project Creator` on the organization/folder and `Billing Account User` on the account.
- **Budgets and alerts:** a budget has an amount, a scope (projects, services, labels) and thresholds on actual or forecasted spend. A budget **only alerts; it never stops usage**.
- **Programmatic budget notifications** publish to Pub/Sub. A Cloud Run function can react by, for example, stopping a VM or disabling billing on a project.
- **Billing export to BigQuery** (standard usage, detailed usage, pricing) gives line-item analysis, and Looker Studio (formerly Data Studio) can chart it. Enable it early; do not count on a full history.
- **Labels** (key-value) on resources flow into billing data so you can group and filter costs.

```bash
gcloud billing accounts list
gcloud billing projects link my-project --billing-account=0X0X0X-0X0X0X-0X0X0X
gcloud billing projects describe my-project
```

### Discounts and estimates

- **Sustained use discounts** apply automatically for some machine families that run a large part of the month.
- **Committed use discounts** trade a 1 or 3 year commitment for a lower price, whether or not you use the resource.
- **Spot VMs** are cheapest but can be preempted.
- The **Pricing Calculator** estimates the cost of an architecture before you build it.

### Quotas

Quotas limit resource use per project (and per region), for example CPUs or API request rates. They are not budgets. Check them in IAM & Admin > Quotas & System limits or with `gcloud compute regions describe REGION`, and request an increase there. Budgets never raise or cap quotas. Check GPU and CPU quotas, and zone availability, before creating an instance template.

## Exam tips

- Alert on CPU for 7 minutes: metric alerting policy with a **retest window** of 7 minutes, plus a notification channel.
- Many projects, one view: **metrics scope** with a scoping project.
- Application logs missing from Logging: install the **Ops Agent**.
- Logs to an external SIEM or SaaS with the lowest delay: sink to **Pub/Sub**. Central logs from many projects: **aggregated sink**.
- Query logs with SQL and join with other data: **Observability Analytics** with a linked BigQuery dataset.
- Dashboard or alert from a pattern in log text: **log-based metric (counter)**.
- Who read objects: **Data Access audit logs**, enabled first. Admin Activity is always on.
- Budget cannot stop spending alone: use **Pub/Sub plus a Cloud Run function**.
- Detailed cost analysis and history: **billing export to BigQuery**, enabled as early as possible.
- Move a project to another payer: change its billing account link.
- Quota error: increase the quota, because budgets do not affect it.

## What appeared on the practice exams

Condensed from the 300 practice questions. Question IDs link to the full question and explanation.

### Observability

- **Ops Agent** sends logs from files and system metrics.
- **Log-based metrics** (counter) feed dashboards and alerts.
- **Alerts:** metric policy with a retest window (for example, 7 minutes) and a notification channel.
- **Log sinks:** BigQuery, Storage, Pub/Sub. For the SIEM, use Pub/Sub.
- **Observability Analytics** + linked BigQuery dataset to query logs with SQL.
- **Metrics scope:** one scoping project aggregates several.
- **Google Cloud health:** Cloud Hub and **Personalized Service Health**.
- **Logging:** log view + `logging.viewAccessor` for fine-grained access.
- **Auditing:** Admin Activity (always on) and Data Access (must be enabled).

## Official documentation
- [Cloud Monitoring alerting](https://docs.cloud.google.com/monitoring/alerts)
- [Metrics scopes and monitoring settings](https://docs.cloud.google.com/monitoring/settings)
- [Log buckets](https://docs.cloud.google.com/logging/docs/buckets)
- [Aggregated sinks](https://docs.cloud.google.com/logging/docs/export/aggregated_sinks_overview)
- [Log-based metrics](https://docs.cloud.google.com/logging/docs/logs-based-metrics)
- [Cloud Audit Logs](https://docs.cloud.google.com/logging/docs/audit)
- [Install the Ops Agent](https://docs.cloud.google.com/logging/docs/agent/ops-agent/installation)
- [Personalized Service Health](https://docs.cloud.google.com/service-health/docs/overview)
- [Cloud Billing budgets](https://docs.cloud.google.com/billing/docs/how-to/budgets)
- [Export Cloud Billing data to BigQuery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery)

[Back to topic](README.md)
