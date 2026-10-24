# Cloud Billing

> **Level:** Intermediate · **Topic:** [Operations and cost](../README.md) · **Cited in:** 9 practice-exam questions

## What it is

Billing account, linked to projects.

## Triggers and facts

- Engineers creating projects without a personal card: central account, `Project Creator`, and `Billing Account User` ([E1Q2](../../99-practice-exams/exam-1.md#q2)).
- Charging an initiative only to Finance: new project linked to the Finance account ([E4Q4](../../99-practice-exams/exam-4.md#q4)).
- Project linked to a personal card: **change the billing account** of the project ([E6Q50](../../99-practice-exams/exam-6.md#q50)).
- Budget per project: one budget per project ([E3Q48](../../99-practice-exams/exam-3.md#q48)). Per folder: budget scoped to the folder ([E4Q37](../../99-practice-exams/exam-4.md#q37)).
- A budget only **alerts**. To stop the VM: programmatic notification to Pub/Sub and a Cloud Run function ([E2Q33](../../99-practice-exams/exam-2.md#q33), [E2Q42](../../99-practice-exams/exam-2.md#q42)).
- Detailed analysis and full history: **billing export to BigQuery**, enabled early, with the *detailed* export ([E2Q32](../../99-practice-exams/exam-2.md#q32), [E6Q29](../../99-practice-exams/exam-6.md#q29)). The export is **not retroactive**.

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q2](../../99-practice-exams/exam-1.md#q2) | NovaTrail Analytics was incorporated nine months ago and is rapidly expanding its use of Google Cloud. The pla... |
| [E2Q32](../../99-practice-exams/exam-2.md#q32) | NimbusCart is moving its retail applications from an on-premises environment to Google Cloud. The finance team... |
| [E2Q33](../../99-practice-exams/exam-2.md#q33) | BrightCart is launching an online storefront on a Compute Engine VM. The company has created a monthly Cloud B... |
| [E2Q42](../../99-practice-exams/exam-2.md#q42) | LedgerLoop operates many independent Google Cloud projects for its financial analytics teams. Each project has... |
| [E3Q48](../../99-practice-exams/exam-3.md#q48) | BrightForge Labs gives each of its 12 application developers a separate Google Cloud project for testing servi... |
| [E4Q4](../../99-practice-exams/exam-4.md#q4) | BrightCart Retail has four existing Google Cloud projects. The Finance department is starting a new expense-an... |
| [E4Q37](../../99-practice-exams/exam-4.md#q37) | NimbusSketch, a collaborative design platform, allows developers to create experimental resources in multiple ... |
| [E6Q29](../../99-practice-exams/exam-6.md#q29) | Finora Health operates several patient-scheduling applications across multiple Google Cloud projects. The fina... |
| [E6Q50](../../99-practice-exams/exam-6.md#q50) | BluePeak Analytics has several Google Cloud projects that an engineer originally linked to a personal Cloud Bi... |

## Official documentation

- [Billing / Export data BigQuery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery)
- [Billing / Budgets](https://docs.cloud.google.com/billing/docs/how-to/budgets)
- [Billing / Export data BigQuery setup](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-setup)
- [Billing / Billing access](https://docs.cloud.google.com/billing/docs/how-to/billing-access)
- [Billing / Budgets notification recipients](https://docs.cloud.google.com/billing/docs/how-to/budgets-notification-recipients)
- [Billing / Detailed usage](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-tables/detailed-usage)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
