# Workload Identity Federation for GKE

> **Level:** Advanced · **Topic:** [Identity and security](../README.md) · **Cited in:** 3 practice-exam questions

## What it is

The Pod uses the identity of a **Kubernetes ServiceAccount** to access Google APIs, with no key.

## Trigger

"remove the service account key mounted in a Kubernetes Secret" ([E4Q48](../../99-practice-exams/exam-4.md#q48), [E5Q7](../../99-practice-exams/exam-5.md#q7), [E5Q46](../../99-practice-exams/exam-5.md#q46)).

## Watch out

Do not confuse it with Workforce Identity Federation, which is for people.

## Related practice questions

| Question | Question stem |
|---|---|
| [E4Q48](../../99-practice-exams/exam-4.md#q48) | BlueHarbor Media runs a content-processing application on GKE. The application needs to upload generated media... |
| [E5Q7](../../99-practice-exams/exam-5.md#q7) | TrailNest operates a hiking-route application on Google Kubernetes Engine (GKE). A backend workload running in... |
| [E5Q46](../../99-practice-exams/exam-5.md#q46) | MetricHaven operates a monitoring agent in a Google Kubernetes Engine cluster. The agent must use an existing ... |

## Official documentation

- [Kubernetes engine / Workload identity](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/workload-identity)
- [Kubernetes engine / Workload identity](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/workload-identity)
- [Kubernetes engine / Networking](https://docs.cloud.google.com/kubernetes-engine/docs/best-practices/networking)
- [Kubernetes engine / Autopilot overview](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview)
- [Kubernetes engine / Choose cluster mode](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/choose-cluster-mode)
- [Kubernetes engine / Cluster autoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
