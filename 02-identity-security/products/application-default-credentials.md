# Application Default Credentials (ADC)

> **Level:** Intermediate · **Topic:** [Identity and security](../README.md) · **Cited in:** 2 practice-exam questions

## What it is

The libraries' strategy for finding credentials automatically. The order is the `GOOGLE_APPLICATION_CREDENTIALS` variable, then the service account attached to the resource.

## Trigger

"the code works on the developer's workstation but is moving to a VM" ([E4Q13](../../99-practice-exams/exam-4.md#q13)). "On-premises server with a federation configuration file" ([E4Q30](../../99-practice-exams/exam-4.md#q30)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E4Q13](../../99-practice-exams/exam-4.md#q13) | BlueOrbit Logistics developed a shipment-tracking application on a developer workstation. The application uses... |
| [E4Q30](../../99-practice-exams/exam-4.md#q30) | HarborTrack Logistics runs a Java shipment-processing application in its private data center. The application ... |

## Official documentation

- [Authentication / Application default credentials](https://docs.cloud.google.com/docs/authentication/application-default-credentials)
- [Authentication / Set up adc on premises](https://docs.cloud.google.com/docs/authentication/set-up-adc-on-premises)
- [Authentication / Set up adc attached service account](https://docs.cloud.google.com/docs/authentication/set-up-adc-attached-service-account)
- [Authentication / Use service account impersonation](https://docs.cloud.google.com/docs/authentication/use-service-account-impersonation)
- [SQL / IAM authentication](https://docs.cloud.google.com/sql/docs/postgres/iam-authentication)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
