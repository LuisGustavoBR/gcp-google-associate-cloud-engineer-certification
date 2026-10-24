# Service account impersonation

> **Level:** Advanced · **Topic:** [Identity and security](../README.md) · **Cited in:** 3 practice-exam questions

## What it is

The developer assumes the identity of the service account without downloading a key. Requires `roles/iam.serviceAccountTokenCreator`.

## Trigger

"test with the service account's permissions, without long-lived credentials" ([E1Q39](../../99-practice-exams/exam-1.md#q39), [E5Q39](../../99-practice-exams/exam-5.md#q39), [E6Q44](../../99-practice-exams/exam-6.md#q44)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q39](../../99-practice-exams/exam-1.md#q39) | BrightTrail Media is developing a local automation script that runs several gcloud CLI commands to inspect Clo... |
| [E5Q39](../../99-practice-exams/exam-5.md#q39) | QuantaFleet is developing a data-processing tool that will run in Google Cloud and access BigQuery and Cloud S... |
| [E6Q44](../../99-practice-exams/exam-6.md#q44) | NovaCart Analytics is building an application that will run on Google Cloud and use a dedicated service accoun... |

## Official documentation

- [Authentication / Use service account impersonation](https://docs.cloud.google.com/docs/authentication/use-service-account-impersonation)
- [IAM / Service account impersonation](https://docs.cloud.google.com/iam/docs/service-account-impersonation)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
