# Organization Policy Service

> **Level:** Intermediate · **Topic:** [Identity and security](../README.md) · **Cited in:** 8 practice-exam questions

## What it is

Enforces constraints on everything below the node where it is applied.

## Triggers and facts

- Location: `gcp.resourceLocations`, with value groups such as `in:australia-locations` ([E2Q15](../../99-practice-exams/exam-2.md#q15)). For the whole company: apply at the **root** ([E1Q43](../../99-practice-exams/exam-1.md#q43)).
- Allowed services: `gcp.restrictServiceUsage` ([E6Q21](../../99-practice-exams/exam-6.md#q21)).
- Block external accounts: **Restrict allowed policy members**, plus remove the existing ones ([E3Q30](../../99-practice-exams/exam-3.md#q30)).
- Service account keys: disable creation and limit the validity period ([E5Q9](../../99-practice-exams/exam-5.md#q9)).
- Require OS Login ([E4Q40](../../99-practice-exams/exam-4.md#q40)).
- A folder is the unit for a group of projects ([E1Q19](../../99-practice-exams/exam-1.md#q19), [E1Q23](../../99-practice-exams/exam-1.md#q23)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q19](../../99-practice-exams/exam-1.md#q19) | BluePeak Games has several software engineering teams based in the United States. Each team uses a separate Go... |
| [E1Q23](../../99-practice-exams/exam-1.md#q23) | Northstar Health operates separate Google Cloud environments for its clinical, finance, and research divisions... |
| [E1Q43](../../99-practice-exams/exam-1.md#q43) | NordicCare Analytics is migrating several healthcare reporting workloads to Google Cloud. Its projects are org... |
| [E2Q15](../../99-practice-exams/exam-2.md#q15) | SouthernCross Health Analytics processes regulated healthcare data in Google Cloud. The compliance team requir... |
| [E3Q30](../../99-practice-exams/exam-3.md#q30) | AsterPeak Logistics discovers that 11 external contractor accounts have IAM access to resources in its Google ... |
| [E4Q40](../../99-practice-exams/exam-4.md#q40) | NexaFleet manages Linux Compute Engine instances across dozens of Google Cloud projects. The security team wan... |
| [E5Q9](../../99-practice-exams/exam-5.md#q9) | BrightForge develops a mobile application, and its engineers currently use many user-managed service account k... |
| [E6Q21](../../99-practice-exams/exam-6.md#q21) | OrionVista Analytics is establishing a sandbox environment for a new research team. The researchers will run e... |

## Official documentation

- [Organization policy / Restrict locations](https://docs.cloud.google.com/organization-policy/restrict-locations)
- [Organization policy / Domain restricted sharing](https://docs.cloud.google.com/organization-policy/domain-restricted-sharing)
- [Organization policy / Hierarchy evaluation](https://docs.cloud.google.com/organization-policy/hierarchy-evaluation)
- [Organization policy / Overview](https://docs.cloud.google.com/organization-policy/overview)
- [Organization policy / Restrict locations supported services](https://docs.cloud.google.com/organization-policy/reference/restrict-locations-supported-services)
- [Organization policy / Restrict domains](https://docs.cloud.google.com/organization-policy/restrict-domains)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
