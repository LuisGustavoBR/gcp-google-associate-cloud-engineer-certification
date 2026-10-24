# HPA, VPA, and cluster autoscaler

> **Level:** Intermediate · **Topic:** [Compute and containers](../README.md) · **Cited in:** 4 practice-exam questions

## What it is

HPA changes the number of replicas, VPA adjusts CPU and memory, and the cluster autoscaler changes the number of nodes (with a minimum and maximum).

## Trigger

"recommend CPU and memory based on usage" points to VPA ([E2Q2](../../99-practice-exams/exam-2.md#q2), [E3Q14](../../99-practice-exams/exam-3.md#q14)). "Single replica" points to VPA ([E4Q36](../../99-practice-exams/exam-4.md#q36)). "Pods pending for lack of nodes" points to the cluster autoscaler ([E5Q16](../../99-practice-exams/exam-5.md#q16)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E2Q2](../../99-practice-exams/exam-2.md#q2) | StreamForge runs a video-processing service on a Google Kubernetes Engine cluster. The team does not yet know ... |
| [E3Q14](../../99-practice-exams/exam-3.md#q14) | StreamWave operates a media-processing platform with hundreds of containerized services in a Google Kubernetes... |
| [E4Q36](../../99-practice-exams/exam-4.md#q36) | LedgerNest runs a stateful transaction-processing service on Google Kubernetes Engine (GKE). The service is de... |
| [E5Q16](../../99-practice-exams/exam-5.md#q16) | BrightRoute, a logistics software company, runs several containerized services and expects development teams t... |

## Official documentation

- [Run / About instance autoscaling](https://docs.cloud.google.com/run/docs/about-instance-autoscaling)
- [Spanner / Autoscaling overview](https://docs.cloud.google.com/spanner/docs/autoscaling-overview)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
