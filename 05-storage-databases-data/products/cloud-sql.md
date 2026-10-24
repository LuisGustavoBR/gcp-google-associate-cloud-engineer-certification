# Cloud SQL

> **Level:** Intermediate · **Topic:** [Storage, databases and data](../README.md) · **Cited in:** 5 practice-exam questions

## What it is

Managed MySQL, PostgreSQL, and SQL Server, regional.

## Triggers and facts

- Relational without rewriting the application ([E2Q8](../../99-practice-exams/exam-2.md#q8), [E3Q10](../../99-practice-exams/exam-3.md#q10)).
- IAM authentication and encrypted connection: **IAM database authentication** plus **Cloud SQL Auth Proxy** ([E1Q17](../../99-practice-exams/exam-1.md#q17)).
- Independent copy kept for years: **scheduled export** to Archive ([E6Q31](../../99-practice-exams/exam-6.md#q31)).
- First troubleshooting step: read the full error message ([E1Q50](../../99-practice-exams/exam-1.md#q50)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q17](../../99-practice-exams/exam-1.md#q17) | MediLedger is deploying a patient appointment application on Google Cloud. The application requires a Cloud SQ... |
| [E1Q50](../../99-practice-exams/exam-1.md#q50) | Northwind Media uses a Cloud SQL instance to support an internal content-management application. An employee n... |
| [E2Q8](../../99-practice-exams/exam-2.md#q8) | HarborDesk Logistics uses an internal order-processing portal that is accessed only by employees at its Bengal... |
| [E3Q10](../../99-practice-exams/exam-3.md#q10) | NorthPeak Rentals operates an internal application that tracks equipment checkouts, customer deposits, invento... |
| [E6Q31](../../99-practice-exams/exam-6.md#q31) | BlueHarbor Retail runs its order-processing system on a Cloud SQL for MySQL instance. After financial records ... |

## Official documentation

- [SQL / Postgres](https://docs.cloud.google.com/sql/docs/postgres)
- [SQL / Debugging connectivity](https://docs.cloud.google.com/sql/docs/debugging-connectivity)
- [SQL / Connect auth proxy](https://docs.cloud.google.com/sql/docs/postgres/connect-auth-proxy)
- [SQL / IAM authentication](https://docs.cloud.google.com/sql/docs/postgres/iam-authentication)
- [SQL / SQL proxy](https://docs.cloud.google.com/sql/docs/postgres/sql-proxy)
- [SQL / Troubleshooting](https://docs.cloud.google.com/sql/docs/troubleshooting)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
