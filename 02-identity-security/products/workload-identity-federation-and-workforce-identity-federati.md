# Workload Identity Federation and Workforce Identity Federation

> **Level:** Advanced · **Topic:** [Identity and security](../README.md) · **Cited in:** 7 practice-exam questions

## What it is

The first is for external **workloads** (GitHub Actions, AWS, another cloud), with a pool, an OIDC provider, and service account impersonation. The second is for **people** from an external IdP.

## Trigger

"GitHub pipeline, no persistent key" ([E4Q46](../../99-practice-exams/exam-4.md#q46), [E5Q11](../../99-practice-exams/exam-5.md#q11), [E6Q6](../../99-practice-exams/exam-6.md#q6)). "Pipeline on AWS pushing images to Artifact Registry" ([E6Q40](../../99-practice-exams/exam-6.md#q40)). "Consultants with their own IdP, individual actions recorded in the log" ([E4Q45](../../99-practice-exams/exam-4.md#q45), [E6Q41](../../99-practice-exams/exam-6.md#q41)). "Permissions that change when the IdP moves the user to another team": map the attribute and use the principal set ([E4Q47](../../99-practice-exams/exam-4.md#q47)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E4Q45](../../99-practice-exams/exam-4.md#q45) | BrightPath Retail operates a sales forecasting portal that queries BigQuery. An external research agency has 6... |
| [E4Q46](../../99-practice-exams/exam-4.md#q46) | Northstar Analytics uses a GitHub Actions pipeline to publish application updates to a Cloud Run service. The ... |
| [E4Q47](../../99-practice-exams/exam-4.md#q47) | SilverLine Commerce uses Workforce Identity Federation to provide external incident-response specialists with ... |
| [E5Q11](../../99-practice-exams/exam-5.md#q11) | BlueHarbor Media uses GitHub Actions to deploy a standard three-tier content platform into separate developmen... |
| [E6Q6](../../99-practice-exams/exam-6.md#q6) | NovaCart is building an internal developer platform for its product teams. Developers need a self-service meth... |
| [E6Q40](../../99-practice-exams/exam-6.md#q40) | BlueHarbor Media operates a release pipeline on Amazon EC2 in an AWS account. The pipeline must push newly bui... |
| [E6Q41](../../99-practice-exams/exam-6.md#q41) | Northbridge Advisory needs to provide 32 independent compliance reviewers with temporary, read-only access to ... |

## Official documentation

- [IAM / Workload identity federation](https://docs.cloud.google.com/iam/docs/workload-identity-federation)
- [IAM / Workload identity federation with deployment pipelines](https://docs.cloud.google.com/iam/docs/workload-identity-federation-with-deployment-pipelines)
- [IAM / Configuring workforce identity federation](https://docs.cloud.google.com/iam/docs/configuring-workforce-identity-federation)
- [IAM / Workforce identity federation](https://docs.cloud.google.com/iam/docs/workforce-identity-federation)
- [IAM / Workload identity federation with other clouds](https://docs.cloud.google.com/iam/docs/workload-identity-federation-with-other-clouds)
- [IAM / Workload identity federation with other providers](https://docs.cloud.google.com/iam/docs/workload-identity-federation-with-other-providers)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
