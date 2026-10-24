# Managed Instance Group (MIG)

> **Level:** Basic · **Topic:** [Compute and containers](../README.md) · **Cited in:** 5 practice-exam questions

## What it is

Group of identical VMs created from an instance template. It provides autoscaling, auto-healing, and distribution across zones.

## Triggers and facts

- Load that varies during the day: MIG with CPU-based autoscaling ([E3Q46](../../99-practice-exams/exam-3.md#q46), [E6Q12](../../99-practice-exams/exam-6.md#q12)).
- MIG with a disk that cannot be lost: **stateful MIG** with size 1 ([E3Q45](../../99-practice-exams/exam-3.md#q45)).
- Recreate only one VM: `gcloud compute instance-groups managed recreate-instances` ([E3Q18](../../99-practice-exams/exam-3.md#q18)).
- MIG cannot recreate VMs: check the template, remove disks with conflicting names, and use `autoDelete=true` ([E6Q1](../../99-practice-exams/exam-6.md#q1)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E3Q18](../../99-practice-exams/exam-3.md#q18) | ParcelPilot runs a shipment-tracking API on Compute Engine VMs in a managed instance group. Cloud Logging indi... |
| [E3Q45](../../99-practice-exams/exam-3.md#q45) | MercuryMart operates a retail analytics platform and needs to install a third-party application on one Compute... |
| [E3Q46](../../99-practice-exams/exam-3.md#q46) | TransitPulse, a city transport tracking company, has built a stateless application that depends on an operatin... |
| [E6Q1](../../99-practice-exams/exam-6.md#q1) | DataPulse runs a batch-processing platform on Compute Engine using a managed instance group. The group reports... |
| [E6Q12](../../99-practice-exams/exam-6.md#q12) | WaveCast provides an online audio-transcoding service on Compute Engine. Demand changes throughout the day, an... |

## Official documentation

- [Compute / Autoscaler](https://docs.cloud.google.com/compute/docs/autoscaler)
- [Compute / Instance groups](https://docs.cloud.google.com/compute/docs/instance-groups)
- [Compute / Scaling cpu](https://docs.cloud.google.com/compute/docs/autoscaler/scaling-cpu)
- [Compute / Autohealing instances in migs](https://docs.cloud.google.com/compute/docs/instance-groups/autohealing-instances-in-migs)
- [Compute / Delete mig](https://docs.cloud.google.com/compute/docs/instance-groups/delete-mig)
- [Compute / Rolling out updates to managed instance groups](https://docs.cloud.google.com/compute/docs/instance-groups/rolling-out-updates-to-managed-instance-groups)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
