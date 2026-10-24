# Operations and cost: common traps

Rules that decide questions people often get wrong. Read these after the concepts page: they are the traps the practice exams used.

| Question | Rule to remember |
|---|---|
| [E6Q10](../99-practice-exams/exam-6.md#q10) | Logs to an external SaaS with the lowest delay: **sink to Pub/Sub**. Storage has batch delay. |
| [E6Q1](../99-practice-exams/exam-6.md#q1) | MIG does not recreate VMs: check the **template**, remove **disks with conflicting names** and use `autoDelete=true`. |
| [E3Q18](../99-practice-exams/exam-3.md#q18) | Recreate only one VM of the MIG: `gcloud compute instance-groups managed recreate-instances`. |
| [E2Q33](../99-practice-exams/exam-2.md#q33), [E2Q42](../99-practice-exams/exam-2.md#q42) | Stop a resource when the budget is reached: **budget with programmatic notification to Pub/Sub and a Cloud Run function**. |
| [E3Q36](../99-practice-exams/exam-3.md#q36), [E6Q46](../99-practice-exams/exam-6.md#q46) | Audit object reads: **Data Access audit logs** (disabled by default on Cloud Storage). |
| [E3Q13](../99-practice-exams/exam-3.md#q13) | Disabled KMS key: **re-enable the key version**. |

[Back to topic](README.md)
