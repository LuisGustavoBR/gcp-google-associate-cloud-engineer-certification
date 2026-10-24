# Storage, databases and data: common traps

Rules that decide questions people often get wrong. Read these after the concepts page: they are the traps the practice exams used.

| Question | Rule to remember |
|---|---|
| [E1Q17](../99-practice-exams/exam-1.md#q17) | Cloud SQL with IAM authentication and an encrypted connection: **IAM database authentication + Cloud SQL Auth Proxy**. |
| [E6Q31](../99-practice-exams/exam-6.md#q31) | Independent copy for 4 years: **scheduled export to an Archive bucket**. Automatic backups are not a portable copy. |
| [E1Q50](../99-practice-exams/exam-1.md#q50) | First troubleshooting step: **read the full error message**. |
| [E5Q36](../99-practice-exams/exam-5.md#q36) | Health of the entire database fleet: **Database Center**. Cloud Asset Inventory only lists resources. |
| [E6Q49](../99-practice-exams/exam-6.md#q49), [E5Q49](../99-practice-exams/exam-5.md#q49), [E6Q23](../99-practice-exams/exam-6.md#q23), [E6Q11](../99-practice-exams/exam-6.md#q11) | SMB and corporate NAS features: **NetApp Volumes**. Legacy NFS: **Filestore**. HPC/AI with high parallel throughput: **Managed Lustre**. |
| [E1Q8](../99-practice-exams/exam-1.md#q8), [E4Q34](../99-practice-exams/exam-4.md#q34) | Sensor time series: **Bigtable**, with row key `device_id + timestamp`. |
| [E1Q28](../99-practice-exams/exam-1.md#q28), [E2Q5](../99-practice-exams/exam-2.md#q5), [E4Q16](../99-practice-exams/exam-4.md#q16), [E4Q35](../99-practice-exams/exam-4.md#q35), [E6Q19](../99-practice-exams/exam-6.md#q19) | Global SQL with strong consistency and horizontal scale: **Spanner**. |
| [E3Q10](../99-practice-exams/exam-3.md#q10), [E2Q8](../99-practice-exams/exam-2.md#q8) | Regional relational database, without rewriting the application: **Cloud SQL**. Higher transactional performance: **AlloyDB**. |
| [E3Q26](../99-practice-exams/exam-3.md#q26) | `quotaExceeded` in BigQuery: **INFORMATION_SCHEMA** and **Cloud Audit Logs**. |

[Back to topic](README.md)
