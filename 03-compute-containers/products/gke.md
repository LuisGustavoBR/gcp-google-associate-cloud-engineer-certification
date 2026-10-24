# GKE (Autopilot and Standard)

> **Level:** Basic · **Topic:** [Compute and containers](../README.md) · **Cited in:** 15 practice-exam questions

## What it is

Managed Kubernetes. In Autopilot, Google manages the nodes and it is always regional. In Standard, the node pools are controlled by the user.

## Triggers and facts

- Without managing nodes or node pools: **Autopilot** ([E1Q14](../../99-practice-exams/exam-1.md#q14), [E5Q21](../../99-practice-exams/exam-5.md#q21), [E6Q13](../../99-practice-exams/exam-6.md#q13)).
- HA on zone failure: **regional**, and Autopilot ([E3Q12](../../99-practice-exams/exam-3.md#q12)).
- Fixed number of nodes: **Standard**, fixed node pool and no autoscaling ([E3Q29](../../99-practice-exams/exam-3.md#q29)).
- Verify node integrity and boot: private cluster and Autopilot, with Shielded nodes ([E2Q1](../../99-practice-exams/exam-2.md#q1)).
- Critical production: **Stable** channel ([E5Q4](../../99-practice-exams/exam-5.md#q4)).
- Running out of IPs: expand the subnet range ([E1Q6](../../99-practice-exams/exam-1.md#q6)).
- Workload needing a different machine type: **new node pool** ([E1Q27](../../99-practice-exams/exam-1.md#q27), [E4Q2](../../99-practice-exams/exam-4.md#q2), [E5Q3](../../99-practice-exams/exam-5.md#q3)).
- Mix of API and jobs: Spot node pool only for the jobs ([E2Q36](../../99-practice-exams/exam-2.md#q36)).
- Database with a persistent disk: **StatefulSet** ([E6Q45](../../99-practice-exams/exam-6.md#q45)).
- Undo a bad deployment: `kubectl rollout undo` ([E2Q28](../../99-practice-exams/exam-2.md#q28)).
- View the nodes: `gcloud container clusters get-credentials` and then `kubectl get nodes` ([E5Q8](../../99-practice-exams/exam-5.md#q8)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q6](../../99-practice-exams/exam-1.md#q6) | StreamWave runs three VPC-native Google Kubernetes Engine clusters that share the same subnet. The subnet’s av... |
| [E1Q14](../../99-practice-exams/exam-1.md#q14) | ParcelPilot is preparing to launch a containerized shipment-tracking service on Google Cloud. The operations t... |
| [E1Q27](../../99-practice-exams/exam-1.md#q27) | VistaMetrics runs a data-processing application in a Google Kubernetes Engine Standard cluster. The applicatio... |
| [E2Q1](../../99-practice-exams/exam-2.md#q1) | MediCore Analytics is preparing a Google Kubernetes Engine cluster for a healthcare processing service. The cl... |
| [E2Q28](../../99-practice-exams/exam-2.md#q28) | Northstar Retail deployed a new version of its inventory API to Google Kubernetes Engine (GKE) by using a roll... |
| [E2Q36](../../99-practice-exams/exam-2.md#q36) | ParcelPulse operates a package-tracking platform on Google Kubernetes Engine. Its real-time tracking API must ... |
| [E3Q12](../../99-practice-exams/exam-3.md#q12) | StreamHive Media runs a video-processing application in a single-zone Google Kubernetes Engine cluster in euro... |
| [E3Q29](../../99-practice-exams/exam-3.md#q29) | PixelForge Media is launching a collaborative video-editing portal. The application uses a microservices archi... |
| [E4Q2](../../99-practice-exams/exam-4.md#q2) | PixelWave Media runs several microservices in a Google Kubernetes Engine cluster. Its thumbnail-generation ser... |
| [E5Q3](../../99-practice-exams/exam-5.md#q3) | PixelHarbor operates a photo-sharing platform on a Google Kubernetes Engine cluster. A thumbnail-generation mi... |
| [E5Q4](../../99-practice-exams/exam-5.md#q4) | LedgerNest has developed a containerized payment-reconciliation application that must run on Kubernetes. Becau... |
| [E5Q8](../../99-practice-exams/exam-5.md#q8) | NimbusCart operates two Google Kubernetes Engine (GKE) clusters created with the gcloud container clusters com... |
| [E5Q21](../../99-practice-exams/exam-5.md#q21) | Northstar Health is rebuilding its internal appointment-processing platform as containerized microservices. Th... |
| [E6Q13](../../99-practice-exams/exam-6.md#q13) | AsterFit, a mobile fitness platform, is migrating its containerized API services to Google Kubernetes Engine (... |
| [E6Q45](../../99-practice-exams/exam-6.md#q45) | Evergreen Tickets is moving its reservation database and stateless booking service to a Standard Google Kubern... |

## Official documentation

- [Kubernetes engine / Autopilot overview](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview)
- [Kubernetes engine / Node pools](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/node-pools)
- [Kubernetes engine / Node pools](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/node-pools)
- [Kubernetes engine / Configuration overview](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/configuration-overview)
- [Kubernetes engine / Regional clusters](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/regional-clusters)
- [Kubernetes engine / Choose cluster mode](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/choose-cluster-mode)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
