# Cloud Logging

> **Level:** Basic · **Topic:** [Operations and cost](../README.md) · **Cited in:** 7 practice-exam questions

## What it is

Collects and routes logs.

## Triggers and facts

- Sinks to BigQuery, Storage, and Pub/Sub. For a SaaS or SIEM with the lowest delay: **Pub/Sub** ([E6Q10](../../99-practice-exams/exam-6.md#q10)).
- Aggregated sink at the folder level, protected against modification ([E1Q23](../../99-practice-exams/exam-1.md#q23)).
- Counter-type **log-based metric** for dashboards and alerts ([E2Q12](../../99-practice-exams/exam-2.md#q12), [E4Q11](../../99-practice-exams/exam-4.md#q11), [E6Q30](../../99-practice-exams/exam-6.md#q30)).
- **Log view** with `logging.viewAccessor` for fine-grained access ([E6Q37](../../99-practice-exams/exam-6.md#q37)).
- Sink stopped working: restore the Cloud Logging service agent's role ([E1Q45](../../99-practice-exams/exam-1.md#q45)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q23](../../99-practice-exams/exam-1.md#q23) | Northstar Health operates separate Google Cloud environments for its clinical, finance, and research divisions... |
| [E1Q45](../../99-practice-exams/exam-1.md#q45) | AsterBank routes security logs from Cloud Logging to a centralized destination. After an IAM policy review, th... |
| [E2Q12](../../99-practice-exams/exam-2.md#q12) | ShopSphere is deploying an order-processing service on Cloud Run that connects to a Cloud SQL database. The de... |
| [E4Q11](../../99-practice-exams/exam-4.md#q11) | ParcelPulse operates a delivery-tracking platform on Google Cloud. After detecting an unauthorized configurati... |
| [E6Q10](../../99-practice-exams/exam-6.md#q10) | BluePeak Media operates workloads across Google Cloud and other cloud providers. The company uses an external ... |
| [E6Q30](../../99-practice-exams/exam-6.md#q30) | NorthStar Tickets operates an event-booking application on Google Cloud. Users report a sudden increase in fai... |
| [E6Q37](../../99-practice-exams/exam-6.md#q37) | AsterLink operates a customer portal and an order-processing service in separate Google Cloud projects named p... |

## Official documentation

- [Logging / Access control](https://docs.cloud.google.com/logging/docs/access-control)
- [Logging / Audit](https://docs.cloud.google.com/logging/docs/audit)
- [Logging / Central log storage](https://docs.cloud.google.com/logging/docs/central-log-storage)
- [Logging / Aggregated sinks overview](https://docs.cloud.google.com/logging/docs/export/aggregated_sinks_overview)
- [Logging / Configure export v2](https://docs.cloud.google.com/logging/docs/export/configure_export_v2)
- [Logging / Pub/Sub](https://docs.cloud.google.com/logging/docs/export/pubsub)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
