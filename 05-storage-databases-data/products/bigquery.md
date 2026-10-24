# BigQuery

> **Level:** Intermediate · **Topic:** [Storage, databases and data](../README.md) · **Cited in:** 6 practice-exam questions

## What it is

Serverless data warehouse queried with SQL.

## Triggers and facts

- Data that stays in Cloud Storage: **external table**, without copying ([E1Q5](../../99-practice-exams/exam-1.md#q5), [E5Q41](../../99-practice-exams/exam-5.md#q41)).
- `quotaExceeded`: `INFORMATION_SCHEMA` and Audit Logs ([E3Q26](../../99-practice-exams/exam-3.md#q26)).
- Nightly load failure: job history in BigQuery Studio ([E2Q19](../../99-practice-exams/exam-2.md#q19), [E6Q2](../../99-practice-exams/exam-6.md#q2)).
- Read access for the whole company: `bigquery.dataViewer` for `domain:empresa.com` on the dataset ([E2Q16](../../99-practice-exams/exam-2.md#q16)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q5](../../99-practice-exams/exam-1.md#q5) | FitJourney operates a mobile wellness application. The application stores each customer’s current profile and ... |
| [E2Q16](../../99-practice-exams/exam-2.md#q16) | AuroraMart publishes a BigQuery dataset containing anonymized inventory and customer-order trends. Every emplo... |
| [E2Q19](../../99-practice-exams/exam-2.md#q19) | Northwind Metrics uses Looker Studio to display sales dashboards based on a BigQuery summary table. New transa... |
| [E3Q26](../../99-practice-exams/exam-3.md#q26) | MealMetric, a food-delivery analytics company, stores order and customer activity data in BigQuery. When a dat... |
| [E5Q41](../../99-practice-exams/exam-5.md#q41) | Northstar Games maintains 4.8 petabytes of historical player-event data in Apache Avro files in an on-premises... |
| [E6Q2](../../99-practice-exams/exam-6.md#q2) | MetroCart, an online grocery platform, uses Looker Studio to display sales metrics from a BigQuery table. New ... |

## Official documentation

- [BigQuery / Managing jobs](https://docs.cloud.google.com/bigquery/docs/managing-jobs)
- [BigQuery / Access control](https://docs.cloud.google.com/bigquery/docs/access-control)
- [BigQuery / Admin jobs explorer](https://docs.cloud.google.com/bigquery/docs/admin-jobs-explorer)
- [BigQuery / BigQuery web ui](https://docs.cloud.google.com/bigquery/docs/bigquery-web-ui)
- [BigQuery / Control access to resources IAM](https://docs.cloud.google.com/bigquery/docs/control-access-to-resources-iam)
- [BigQuery / Error messages](https://docs.cloud.google.com/bigquery/docs/error-messages)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
