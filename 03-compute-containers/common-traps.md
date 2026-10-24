# Compute and containers: common traps

Rules that decide questions people often get wrong. Read these after the concepts page: they are the traps the practice exams used.

| Question | Rule to remember |
|---|---|
| [E1Q38](../99-practice-exams/exam-1.md#q38), [E4Q19](../99-practice-exams/exam-4.md#q19) | Small piece of code triggered by an upload to a bucket: **Cloud Run function with a Cloud Storage trigger** (Cloud Functions was renamed Cloud Run functions). |
| [E1Q16](../99-practice-exams/exam-1.md#q16) | Event spikes: **Pub/Sub** decouples producer and consumer, and triggers the function. Scheduler does not fit. |
| [E3Q17](../99-practice-exams/exam-3.md#q17) | Cloud Run reachable by **internal IP** from the VPC and on-premises: **Private Service Connect**. Private Google Access does not solve it. |
| [E4Q3](../99-practice-exams/exam-4.md#q3) | Keep N warm instances on a revision with no traffic: **min-instances per revision**. |
| [E5Q6](../99-practice-exams/exam-5.md#q6), [E2Q38](../99-practice-exams/exam-2.md#q38) | Containerized nightly batch process: **Cloud Run jobs + Cloud Scheduler**. Not a Cloud Run service. |
| [E5Q23](../99-practice-exams/exam-5.md#q23), [E6Q7](../99-practice-exams/exam-6.md#q7), [E1Q49](../99-practice-exams/exam-1.md#q49) | Ready-made Docker images and serverless: **Cloud Run service**. A Cloud Run function starts from source code and changes the build process. |
| [E2Q22](../99-practice-exams/exam-2.md#q22) | App Engine: traffic splitting is between **versions of the same service**. Do not create another service. |
| [E3Q12](../99-practice-exams/exam-3.md#q12), [E6Q13](../99-practice-exams/exam-6.md#q13), [E5Q21](../99-practice-exams/exam-5.md#q21) | HA with minimal management on GKE: **Autopilot, which is always regional**. |
| [E3Q29](../99-practice-exams/exam-3.md#q29) | Fixed number of VMs: **GKE Standard with a fixed-size node pool and no autoscaling**. |
| [E2Q2](../99-practice-exams/exam-2.md#q2), [E3Q14](../99-practice-exams/exam-3.md#q14), [E4Q36](../99-practice-exams/exam-4.md#q36) | **VPA** adjusts CPU/memory. **HPA** adjusts the number of replicas. For a single replica, use VPA. |
| [E1Q27](../99-practice-exams/exam-1.md#q27), [E4Q2](../99-practice-exams/exam-4.md#q2), [E5Q3](../99-practice-exams/exam-5.md#q3) | Workload that needs a different machine type: **new node pool** in the same cluster. |
| [E5Q8](../99-practice-exams/exam-5.md#q8), [E6Q26](../99-practice-exams/exam-6.md#q26), [E5Q32](../99-practice-exams/exam-5.md#q32), [E5Q1](../99-practice-exams/exam-5.md#q1) | Before creating resources in a new project, **enable the API** (`gcloud services enable ...`). A 403 "API has not been used" error is also fixed this way. |
| [E5Q8](../99-practice-exams/exam-5.md#q8) | To see the cluster's nodes: `gcloud container clusters get-credentials` and then `kubectl get nodes`. |

[Back to topic](README.md)
