# Cloud Run (service, job, and functions)

> **Level:** Basic · **Topic:** [Compute and containers](../README.md) · **Cited in:** 15 practice-exam questions

## What it is

Serverless platform for containers. The **service** serves HTTP and scales to zero. The **job** runs and finishes. **Functions** start from source code (Cloud Functions was renamed to Cloud Run functions).

## Triggers and facts

- Ready-made Docker image, serverless: **service** ([E1Q49](../../99-practice-exams/exam-1.md#q49), [E5Q23](../../99-practice-exams/exam-5.md#q23), [E6Q7](../../99-practice-exams/exam-6.md#q7)). The build process does not change.
- Nightly batch: **job** plus Cloud Scheduler ([E2Q38](../../99-practice-exams/exam-2.md#q38), [E5Q6](../../99-practice-exams/exam-5.md#q6)).
- Small piece of code triggered by an upload: **function** with a bucket trigger ([E1Q38](../../99-practice-exams/exam-1.md#q38), [E4Q19](../../99-practice-exams/exam-4.md#q19)).
- Slow first request: **min-instances** ([E1Q34](../../99-practice-exams/exam-1.md#q34)). Keep N warm instances on a revision with no traffic: **per-revision min-instances** ([E4Q3](../../99-practice-exams/exam-4.md#q3)).
- Protect the database at peak: **max-instances** ([E3Q33](../../99-practice-exams/exam-3.md#q33)).
- Zero idle cost: min-instances equal to zero ([E3Q23](../../99-practice-exams/exam-3.md#q23)).
- Gradual rollout: traffic split between **revisions** ([E2Q3](../../99-practice-exams/exam-2.md#q3), [E4Q32](../../99-practice-exams/exam-4.md#q32)).
- Private access over an internal IP: **Private Service Connect** ([E3Q17](../../99-practice-exams/exam-3.md#q17)). To reach GKE: Direct VPC egress plus ILB and private DNS ([E6Q9](../../99-practice-exams/exam-6.md#q9)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q34](../../99-practice-exams/exam-1.md#q34) | TrailNest Travel operates a trip-planning website on Cloud Run for approximately 650 customers. Users report t... |
| [E1Q38](../../99-practice-exams/exam-1.md#q38) | ImageForge operates a media platform where customers upload images to a Cloud Storage bucket. A small code com... |
| [E1Q49](../../99-practice-exams/exam-1.md#q49) | FestivalNest has created a containerized website that publishes schedules and accepts registrations for a week... |
| [E2Q3](../../99-practice-exams/exam-2.md#q3) | StreamNest operates a serverless video-processing application on Google Cloud. The development team wants to r... |
| [E2Q38](../../99-practice-exams/exam-2.md#q38) | LedgerSpring Insurance generates daily financial reconciliation reports after business hours. The processing a... |
| [E3Q17](../../99-practice-exams/exam-3.md#q17) | CareBridge Portal, a healthcare operations company, has created one stateless web application that provides a ... |
| [E3Q23](../../99-practice-exams/exam-3.md#q23) | Northstar HR has built a containerized employee benefits portal that authenticated staff members use only on w... |
| [E3Q33](../../99-practice-exams/exam-3.md#q33) | TicketNest, an event-booking platform, runs its web service on Cloud Run and connects to a Cloud SQL database.... |
| [E4Q3](../../99-practice-exams/exam-4.md#q3) | StreamForge operates a video-processing API on Cloud Run. The engineering team has created a new revision and ... |
| [E4Q19](../../99-practice-exams/exam-4.md#q19) | VoxLoom, a customer-research platform, stores newly uploaded interview recordings in a Cloud Storage bucket. E... |
| [E4Q32](../../99-practice-exams/exam-4.md#q32) | MarketWave operates an online retail platform through an existing Cloud Run service. The engineering team need... |
| [E5Q6](../../99-practice-exams/exam-5.md#q6) | DataForge Labs runs an on-premises inventory-reconciliation program composed of several compiled executables. ... |
| [E5Q23](../../99-practice-exams/exam-5.md#q23) | ParcelPilot operates an on-premises shipment-tracking platform composed of several Python microservices. Each ... |
| [E6Q7](../../99-practice-exams/exam-6.md#q7) | FitMeal Labs has packaged its meal-planning web service as Docker container images. The company expects traffi... |
| [E6Q9](../../99-practice-exams/exam-6.md#q9) | Northstar Retail hosts its order-processing frontend on Cloud Run and runs a pricing API on Google Kubernetes ... |

## Official documentation

- [Run / About instance autoscaling](https://docs.cloud.google.com/run/docs/about-instance-autoscaling)
- [Run / Min instances](https://docs.cloud.google.com/run/docs/configuring/min-instances)
- [Run / Rollouts rollbacks traffic migration](https://docs.cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration)
- [Run / Create jobs](https://docs.cloud.google.com/run/docs/create-jobs)
- [Run / Deploying](https://docs.cloud.google.com/run/docs/deploying)
- [Run / Revisions](https://docs.cloud.google.com/run/docs/managing/revisions)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
