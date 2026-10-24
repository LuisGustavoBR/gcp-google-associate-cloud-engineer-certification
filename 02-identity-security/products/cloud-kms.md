# Cloud KMS

> **Level:** Intermediate · **Topic:** [Identity and security](../README.md) · **Cited in:** 5 practice-exam questions

## What it is

Manages encryption keys (CMEK).

## Triggers and facts

- The service's service agent needs `cryptoKeyEncrypterDecrypter` on the key ([E3Q43](../../99-practice-exams/exam-3.md#q43), [E5Q47](../../99-practice-exams/exam-5.md#q47)).
- Old key versions can still decrypt old data ([E3Q16](../../99-practice-exams/exam-3.md#q16)).
- Cloud SQL instance with an inaccessible CMEK key: **re-enable the key version** ([E3Q13](../../99-practice-exams/exam-3.md#q13)).
- Require CMEK across the whole organization: org policy ([E3Q49](../../99-practice-exams/exam-3.md#q49)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E3Q13](../../99-practice-exams/exam-3.md#q13) | OrbitLend, a digital lending website, stores customer applications in a Cloud SQL for PostgreSQL instance encr... |
| [E3Q16](../../99-practice-exams/exam-3.md#q16) | CedarPay uses a Cloud KMS symmetric encryption key as a customer-managed encryption key for transaction record... |
| [E3Q43](../../99-practice-exams/exam-3.md#q43) | SkyRoute Media stores uploaded video files in a Cloud Storage bucket located in its application project. The b... |
| [E3Q49](../../99-practice-exams/exam-3.md#q49) | Meridian BioLabs operates several Google Cloud projects that store regulated research data in CMEK-supported s... |
| [E5Q47](../../99-practice-exams/exam-5.md#q47) | BrightCart Media stores product images in a Cloud Storage bucket that uses a customer-managed encryption key l... |

## Official documentation

- [KMS / Permissions and roles](https://docs.cloud.google.com/kms/docs/reference/permissions-and-roles)
- [KMS / Cmek org policy](https://docs.cloud.google.com/kms/docs/cmek-org-policy)
- [KMS / Cmek rotation](https://docs.cloud.google.com/kms/docs/cmek-rotation)
- [KMS / Enable disable](https://docs.cloud.google.com/kms/docs/enable-disable)
- [KMS / IAM](https://docs.cloud.google.com/kms/docs/iam)
- [KMS / Key rotation](https://docs.cloud.google.com/kms/docs/key-rotation)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
