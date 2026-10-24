# Cloud Audit Logs

> **Level:** Intermediate · **Topic:** [Identity and security](../README.md) · **Cited in:** 4 practice-exam questions

## What it is

Admin Activity (always on), Data Access (must be enabled, except in BigQuery), and System Event.

## Triggers and facts

- "Who read objects in the bucket?": enable Cloud Storage **Data Access** logs ([E3Q36](../../99-practice-exams/exam-3.md#q36), [E6Q46](../../99-practice-exams/exam-6.md#q46)).
- Viewing data access logs: `roles/logging.privateLogViewer` ([E3Q2](../../99-practice-exams/exam-3.md#q2)).
- Auditing Bigtable and exporting to the SIEM: enable Data Read, Data Write, and Admin Read, and use a sink to Pub/Sub ([E2Q47](../../99-practice-exams/exam-2.md#q47)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E2Q47](../../99-practice-exams/exam-2.md#q47) | HealthAxis operates a patient analytics platform backed by a Bigtable instance with five nodes. The tables con... |
| [E3Q2](../../99-practice-exams/exam-3.md#q2) | LedgerLeaf, a financial reporting platform, stores confidential transaction records in a BigQuery table. After... |
| [E3Q36](../../99-practice-exams/exam-3.md#q36) | VaultBridge stores confidential legal documents in a private Cloud Storage bucket. Compliance auditors require... |
| [E6Q46](../../99-practice-exams/exam-6.md#q46) | Northwind Analytics stores confidential customer reports in several Cloud Storage buckets. A compliance review... |

## Official documentation

- [Logging / Configure data access](https://docs.cloud.google.com/logging/docs/audit/configure-data-access)
- [Storage / Audit logging](https://docs.cloud.google.com/storage/docs/audit-logging)
- [BigQuery / Auditlogs](https://docs.cloud.google.com/bigquery/docs/reference/auditlogs)
- [Bigtable / Audit logging](https://docs.cloud.google.com/bigtable/docs/audit-logging)
- [Logging / Audit](https://docs.cloud.google.com/logging/docs/audit)
- [Compute / View audit logs](https://docs.cloud.google.com/compute/docs/oslogin/view-audit-logs)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
