# Identity and security: common traps

Rules that decide questions people often get wrong. Read these after the concepts page: they are the traps the practice exams used.

| Question | Rule to remember |
|---|---|
| [E1Q32](../99-practice-exams/exam-1.md#q32), [E4Q10](../99-practice-exams/exam-4.md#q10) | Contractor **without a Google account** accessing a VM: **public SSH key in the metadata**. IAP and OS Login require a Google identity. |
| [E4Q48](../99-practice-exams/exam-4.md#q48), [E5Q7](../99-practice-exams/exam-5.md#q7), [E5Q46](../99-practice-exams/exam-5.md#q46) | GKE Pod accessing Google APIs without a key: **Workload Identity Federation for GKE**. Do not confuse it with **Workforce** Identity Federation (external people). |
| [E4Q46](../99-practice-exams/exam-4.md#q46), [E4Q49](../99-practice-exams/exam-4.md#q49), [E5Q11](../99-practice-exams/exam-5.md#q11), [E6Q40](../99-practice-exams/exam-6.md#q40) | External pipeline (GitHub Actions, AWS, another cloud): **Workload Identity Federation** (pool + OIDC/AWS provider) and **impersonation of a service account** with least privilege. |
| [E4Q17](../99-practice-exams/exam-4.md#q17), [E4Q45](../99-practice-exams/exam-4.md#q45), [E4Q47](../99-practice-exams/exam-4.md#q47), [E6Q27](../99-practice-exams/exam-6.md#q27), [E6Q41](../99-practice-exams/exam-6.md#q41) | **People** from an external company with its own IdP: **Workforce Identity Federation**. An IdP attribute/claim becomes a principal set in IAM. |
| [E5Q34](../99-practice-exams/exam-5.md#q34) | GKE nodes pull images from Artifact Registry using the **nodes' service account**. Grant it the Reader role and configure the cluster with that account. |
| [E6Q42](../99-practice-exams/exam-6.md#q42) | External partner accessing your dataset: **they create the service account in their own project** and you grant that account access to your dataset. Whoever runs the workload takes care of the identity. |
| [E6Q15](../99-practice-exams/exam-6.md#q15) | Read-only access to a single bucket: predefined role **Storage Object Viewer on the bucket**. Do not use a custom role on the project. |
| [E6Q20](../99-practice-exams/exam-6.md#q20) | Who created a project: the **Owner** in the IAM policy. There is no creator label. |
| [E3Q11](../99-practice-exams/exam-3.md#q11), [E5Q43](../99-practice-exams/exam-5.md#q43) | Scale access with Cloud Identity **groups**. For IAM, use a **security** group (labels `discussion_forum` **and** `groups.security`) and MFA. |
| [E3Q30](../99-practice-exams/exam-3.md#q30) | Block external accounts: constraint **Restrict allowed policy members** (domain restricted sharing). It only prevents. **Remove existing ones manually.** |
| [E1Q43](../99-practice-exams/exam-1.md#q43), [E1Q19](../99-practice-exams/exam-1.md#q19) | Location Org Policy for the whole company: apply it at the **organization root**, not on each folder. For a group of projects, apply it on the **folder**. |
| [E6Q21](../99-practice-exams/exam-6.md#q21) | Sandbox with Owner and restrictions: folder, plus `gcp.resourceLocations`, plus `gcp.restrictServiceUsage`, plus Owner on the folder. |
| [E5Q50](../99-practice-exams/exam-5.md#q50), [E1Q45](../99-practice-exams/exam-1.md#q45) | If the role of a Google **service agent** was removed and something broke, **restore the documented role to the service agent**. |
| [E3Q43](../99-practice-exams/exam-3.md#q43), [E5Q47](../99-practice-exams/exam-5.md#q47) | CMEK: the **Cloud Storage service agent of the bucket's project** needs `cryptoKeyEncrypterDecrypter` on the key. |
| [E5Q39](../99-practice-exams/exam-5.md#q39), [E6Q44](../99-practice-exams/exam-6.md#q44), [E1Q39](../99-practice-exams/exam-1.md#q39) | Testing with a service account's identity without downloading a key: **impersonation** (`roles/iam.serviceAccountTokenCreator`, `gcloud config set auth/impersonate_service_account`). |
| [E5Q9](../99-practice-exams/exam-5.md#q9) | Service account keys: use Org Policy to disable creation in general and to limit their lifetime. |
| [E6Q48](../99-practice-exams/exam-6.md#q48) | To edit the IAM policy **of a service account** (who can use it), `roles/iam.serviceAccountAdmin` is required. |

[Back to topic](README.md)
