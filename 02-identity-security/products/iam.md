# IAM (roles, bindings, and service accounts)

> **Level:** Basic · **Topic:** [Identity and security](../README.md) · **Cited in:** 15 practice-exam questions

## What it is

Who (principal) can do what (role) on which resource. Inheritance flows down the hierarchy.

## Triggers and facts

- Least privilege: a predefined role at the smallest scope. Custom role only when necessary ([E1Q4](../../99-practice-exams/exam-1.md#q4), [E6Q16](../../99-practice-exams/exam-6.md#q16), [E5Q33](../../99-practice-exams/exam-5.md#q33)).
- Predefined roles can change with updates. Whoever requires stability uses a custom role ([E3Q35](../../99-practice-exams/exam-3.md#q35)).
- DevOps group with full permissions on Compute and read-only on everything else: `viewer` plus `compute.admin` ([E5Q2](../../99-practice-exams/exam-5.md#q2)).
- Entire governance team needs read access across all projects: `Viewer` at the organization level ([E4Q50](../../99-practice-exams/exam-4.md#q50)).
- Cross-project access: grant the role on the data project ([E4Q14](../../99-practice-exams/exam-4.md#q14)).
- Default service account with Editor: create another, dedicated one, and remove Editor ([E1Q20](../../99-practice-exams/exam-1.md#q20)).
- One service account per workload ([E1Q35](../../99-practice-exams/exam-1.md#q35), [E5Q29](../../99-practice-exams/exam-5.md#q29), [E5Q40](../../99-practice-exams/exam-5.md#q40)).
- Write-only access to a bucket: `objectCreator` on the bucket ([E2Q30](../../99-practice-exams/exam-2.md#q30)).
- Finding out who is an Owner: `gcloud projects get-iam-policy` ([E1Q41](../../99-practice-exams/exam-1.md#q41), [E6Q20](../../99-practice-exams/exam-6.md#q20)).
- Why a deployment fails: review both the direct and the inherited roles ([E1Q25](../../99-practice-exams/exam-1.md#q25)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q4](../../99-practice-exams/exam-1.md#q4) | SkyRoute Analytics uses Compute Engine resources in the project skyroute-inventory-47. A contractor from a par... |
| [E1Q20](../../99-practice-exams/exam-1.md#q20) | BrightCart runs an order-processing service on a Compute Engine VM. The VM uses the Compute Engine default ser... |
| [E1Q25](../../99-practice-exams/exam-1.md#q25) | BrightForge Media uses a Jenkins deployment server that authenticates to Google Cloud with a service account. ... |
| [E1Q35](../../99-practice-exams/exam-1.md#q35) | BrightCart operates several applications on Google Cloud, including an order-processing service and an invento... |
| [E1Q41](../../99-practice-exams/exam-1.md#q41) | NovaLedger has assigned you responsibility for maintaining an existing Google Cloud project named ledger-archi... |
| [E2Q30](../../99-practice-exams/exam-2.md#q30) | TrailPulse operates a fitness-tracking application on a Compute Engine VM instance. The application must write... |
| [E3Q35](../../99-practice-exams/exam-3.md#q35) | CloudVista Media operates its customer-facing platform in a dedicated Google Cloud production project, while e... |
| [E4Q14](../../99-practice-exams/exam-4.md#q14) | BrightCart runs its customer portal on Compute Engine VMs in the storefront-services project. The VMs use a se... |
| [E4Q50](../../99-practice-exams/exam-4.md#q50) | BluePeak Insurance has a governance team that must view resources across all current and future Google Cloud p... |
| [E5Q2](../../99-practice-exams/exam-5.md#q2) | NovaForge Games maintains a development project in Google Cloud. Its DevOps group must be able to create, modi... |
| [E5Q29](../../99-practice-exams/exam-5.md#q29) | BrightCart runs its catalog, payment, and reporting applications on separate Compute Engine VM instances withi... |
| [E5Q33](../../99-practice-exams/exam-5.md#q33) | BrightCart operates an online retail platform that uses a Google Kubernetes Engine (GKE) cluster and a Cloud S... |
| [E5Q40](../../99-practice-exams/exam-5.md#q40) | SilverOak Analytics is deploying a licensed reporting application on a new Compute Engine VM. Several existing... |
| [E6Q16](../../99-practice-exams/exam-6.md#q16) | Northwind Media runs a video-processing service on several existing Compute Engine VM instances in a Google Cl... |
| [E6Q20](../../99-practice-exams/exam-6.md#q20) | AsterWave Health recently introduced an automated workflow for creating Google Cloud projects. During a govern... |

## Official documentation

- [IAM / Best practices service accounts](https://docs.cloud.google.com/iam/docs/best-practices-service-accounts)
- [IAM / Choose role type](https://docs.cloud.google.com/iam/docs/choose-role-type)
- [IAM / Creating custom roles](https://docs.cloud.google.com/iam/docs/creating-custom-roles)
- [IAM / Resource hierarchy access control](https://docs.cloud.google.com/iam/docs/resource-hierarchy-access-control)
- [IAM / Roles overview](https://docs.cloud.google.com/iam/docs/roles-overview)
- [IAM / Using IAM securely](https://docs.cloud.google.com/iam/docs/using-iam-securely)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
