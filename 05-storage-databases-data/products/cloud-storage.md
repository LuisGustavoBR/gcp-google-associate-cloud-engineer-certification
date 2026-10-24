# Cloud Storage

> **Level:** Basic · **Topic:** [Storage, databases and data](../README.md) · **Cited in:** 12 practice-exam questions

## What it is

Object storage. Classes: Standard, Nearline (30 days), Coldline (90 days), and Archive (365 days).

## Triggers and facts

- Automatic class change: **Lifecycle** with `age` and `SetStorageClass` ([E2Q24](../../99-practice-exams/exam-2.md#q24), [E2Q27](../../99-practice-exams/exam-2.md#q27), [E3Q47](../../99-practice-exams/exam-3.md#q47), [E6Q35](../../99-practice-exams/exam-6.md#q35)).
- Old versions and deletion: **Object Versioning** plus Lifecycle ([E2Q23](../../99-practice-exams/exam-2.md#q23), [E6Q22](../../99-practice-exams/exam-6.md#q22)).
- Temporary access for partners without an identity: **signed URLs** ([E3Q28](../../99-practice-exams/exam-3.md#q28)).
- Filter by prefix: *uniform bucket-level access* and **IAM condition** ([E5Q37](../../99-practice-exams/exam-5.md#q37)).
- Read-only access to a bucket: `Storage Object Viewer` on the bucket ([E6Q15](../../99-practice-exams/exam-6.md#q15)).
- Sync a local folder: `gcloud storage rsync` with cron ([E3Q21](../../99-practice-exams/exam-3.md#q21), [E6Q8](../../99-practice-exams/exam-6.md#q8)).
- Continuous-read pipeline: dual-region and Standard ([E2Q26](../../99-practice-exams/exam-2.md#q26)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E2Q23](../../99-practice-exams/exam-2.md#q23) | LedgerPeak Insurance is migrating claim documents from its data center to Cloud Storage. The documents have th... |
| [E2Q24](../../99-practice-exams/exam-2.md#q24) | LedgerHaven operates a digital records portal that stores signed audit documents in a Cloud Storage bucket con... |
| [E2Q26](../../99-practice-exams/exam-2.md#q26) | HarborPulse, a maritime logistics company, stores vessel telemetry files in Cloud Storage. A business-critical... |
| [E2Q27](../../99-practice-exams/exam-2.md#q27) | PixelNest Media stores completed image-processing files in a Cloud Storage bucket by using Standard storage. I... |
| [E3Q21](../../99-practice-exams/exam-3.md#q21) | BrightFrame Studios stores completed animation render files on a local network-attached storage system. The co... |
| [E3Q28](../../99-practice-exams/exam-3.md#q28) | DataBridge Logistics is developing an application that receives shipping files from 2,500 partner companies. T... |
| [E3Q47](../../99-practice-exams/exam-3.md#q47) | LedgerNest stores monthly compliance reports in Cloud Storage. Each report is uploaded once and accessed frequ... |
| [E5Q37](../../99-practice-exams/exam-5.md#q37) | PixelNest runs a Cloud Run service that displays product media stored in an existing shared Cloud Storage buck... |
| [E6Q8](../../99-practice-exams/exam-6.md#q8) | CineVault Studios stores completed video footage on an on-premises file server. The company wants to archive t... |
| [E6Q15](../../99-practice-exams/exam-6.md#q15) | BrightTrail, an online travel-planning company, stores destination photographs in a Cloud Storage bucket named... |
| [E6Q22](../../99-practice-exams/exam-6.md#q22) | SilverLeaf Publishing stores digital publications and compliance records in Cloud Storage. An administrator mu... |
| [E6Q35](../../99-practice-exams/exam-6.md#q35) | ClearLedger Services plans to store customer statements and tax documents in Google Cloud for four years. Fina... |

## Official documentation

- [Storage / Lifecycle](https://docs.cloud.google.com/storage/docs/lifecycle)
- [Storage / Object versioning](https://docs.cloud.google.com/storage/docs/object-versioning)
- [Storage / Storage classes](https://docs.cloud.google.com/storage/docs/storage-classes)
- [SDK / Rsync](https://docs.cloud.google.com/sdk/gcloud/reference/storage/rsync)
- [Storage / IAM roles](https://docs.cloud.google.com/storage/docs/access-control/iam-roles)
- [Storage / Using IAM permissions](https://docs.cloud.google.com/storage/docs/access-control/using-iam-permissions)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
