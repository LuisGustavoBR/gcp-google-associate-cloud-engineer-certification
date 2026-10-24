# Spot VMs

> **Level:** Intermediate · **Topic:** [Compute and containers](../README.md) · **Cited in:** 6 practice-exam questions

## What it is

Heavily discounted VMs that Google can interrupt.

## Trigger

"interruption-tolerant batch that saves its progress" and "reduce cost".

## Watch out

A long job with no tolerance for interruption (34 hours, once every six weeks) uses a **regular VM that is turned on and off**, not Spot ([E3Q25](../../99-practice-exams/exam-3.md#q25), [E4Q8](../../99-practice-exams/exam-4.md#q8)). Validate fault tolerance before migrating to Spot.

## Where it appeared

[E1Q18](../../99-practice-exams/exam-1.md#q18), [E2Q14](../../99-practice-exams/exam-2.md#q14), [E2Q36](../../99-practice-exams/exam-2.md#q36), [E6Q38](../../99-practice-exams/exam-6.md#q38).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q18](../../99-practice-exams/exam-1.md#q18) | NightPulse Media processes video analytics every evening by running a batch job across many Compute Engine VMs... |
| [E2Q14](../../99-practice-exams/exam-2.md#q14) | Northstar Media processes analytics data for its streaming platform every evening. Each processing run needs m... |
| [E2Q36](../../99-practice-exams/exam-2.md#q36) | ParcelPulse operates a package-tracking platform on Google Kubernetes Engine. Its real-time tracking API must ... |
| [E3Q25](../../99-practice-exams/exam-3.md#q25) | PixelForge Media runs a single video-processing job on an on-premises server. The job takes approximately 34 h... |
| [E4Q8](../../99-practice-exams/exam-4.md#q8) | BrightCart Analytics generates a full customer-demand forecast every month. The batch job takes approximately ... |
| [E6Q38](../../99-practice-exams/exam-6.md#q38) | ClipStream Labs operates a video-processing platform that converts thousands of uploaded recordings into multi... |

## Official documentation

- [Compute / Spot](https://docs.cloud.google.com/compute/docs/instances/spot)
- [Compute / Create use spot](https://docs.cloud.google.com/compute/docs/instances/create-use-spot)
- [Kubernetes engine / Spot VMs](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/spot-vms)
- [Kubernetes engine / Spot VMs](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/spot-vms)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
