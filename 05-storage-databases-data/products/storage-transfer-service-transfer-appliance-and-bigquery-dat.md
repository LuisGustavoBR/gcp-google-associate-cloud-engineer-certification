# Storage Transfer Service, Transfer Appliance, and BigQuery Data Transfer Service

> **Level:** Intermediate · **Topic:** [Storage, databases and data](../README.md) · **Cited in:** 2 practice-exam questions

## What it is

- **Storage Transfer Service:** copies S3, Azure, HTTP, and on-premises file systems (with agents) to Cloud Storage.
- **Transfer Appliance:** physical device for huge volumes (TB to PB), with offline transfer.
- **BigQuery Data Transfer Service:** scheduled loads into BigQuery from SaaS, Redshift, and S3.

## Trigger

Huge on-premises SAN points to Transfer Appliance, Redshift points to BigQuery DTS, and S3 bucket points to Storage Transfer ([E1Q11](../../99-practice-exams/exam-1.md#q11)). Files from 250 MB to 80 GB with little impact on the production network: Storage Transfer with agents ([E4Q39](../../99-practice-exams/exam-4.md#q39)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q11](../../99-practice-exams/exam-1.md#q11) | VistaStream Studios is moving several datasets to Google Cloud. The company has below mentioned tech-stack. Th... |
| [E4Q39](../../99-practice-exams/exam-4.md#q39) | StreamForge Studios maintains a large collection of production footage on its on-premises file servers. Indivi... |

## Official documentation

- [Storage transfer / File system to cloud storage](https://docs.cloud.google.com/storage-transfer/docs/create-transfers/agent-based/file-system-to-cloud-storage)
- [Storage transfer / S3](https://docs.cloud.google.com/storage-transfer/docs/create-transfers/agentless/s3)
- [Storage transfer / Filter by last modified](https://docs.cloud.google.com/storage-transfer/docs/filter-by-last-modified)
- [Storage transfer / Obtaining bandwidth on prem](https://docs.cloud.google.com/storage-transfer/docs/obtaining-bandwidth-on-prem)
- [Transfer appliance / Overview](https://docs.cloud.google.com/transfer-appliance/docs/4.0/overview)
- [Database migration / Quickstart](https://docs.cloud.google.com/database-migration/docs/postgresql-to-alloydb/quickstart)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
