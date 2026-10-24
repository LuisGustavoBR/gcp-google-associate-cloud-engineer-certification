# Compute Engine

> **Level:** Basic · **Topic:** [Compute and containers](../README.md) · **Cited in:** 10 practice-exam questions

## What it is

VMs in the cloud.

## Triggers and facts

- HA across zones: create resources in another zone of the same region and distribute the traffic ([E1Q12](../../99-practice-exams/exam-1.md#q12)).
- VM with only an internal IP reachable over the WAN: create it without an external IP ([E4Q12](../../99-practice-exams/exam-4.md#q12)).
- IP that must remain the same: promote the current IP to a **static internal IP** ([E3Q24](../../99-practice-exams/exam-3.md#q24)).
- Protection against accidental deletion: *deletion protection* ([E3Q37](../../99-practice-exams/exam-3.md#q37)).
- High memory: **M1** series ([E5Q28](../../99-practice-exams/exam-5.md#q28)).
- Code using CUDA: **NVIDIA GPU** ([E1Q13](../../99-practice-exams/exam-1.md#q13), [E5Q22](../../99-practice-exams/exam-5.md#q22)).
- Before creating the template with a GPU: check zones and quotas ([E1Q21](../../99-practice-exams/exam-1.md#q21)).

## Watch out

In a new project, enable `compute.googleapis.com` first ([E5Q32](../../99-practice-exams/exam-5.md#q32), [E4Q43](../../99-practice-exams/exam-4.md#q43)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q12](../../99-practice-exams/exam-1.md#q12) | BrightCart hosts its online ordering application on Compute Engine VMs in europe-west1-b. The company wants th... |
| [E1Q13](../../99-practice-exams/exam-1.md#q13) | NovaLens Analytics runs a PyTorch application that uses custom CUDA extensions for model processing and GPU ac... |
| [E1Q21](../../99-practice-exams/exam-1.md#q21) | PixelForge Studio is preparing a Compute Engine batch-rendering service in asia-southeast1. The selected NVIDI... |
| [E3Q24](../../99-practice-exams/exam-3.md#q24) | BrightTrail Logistics runs a shipment-tracking service on a Compute Engine VM connected to an IPv4-only subnet... |
| [E3Q37](../../99-practice-exams/exam-3.md#q37) | Northstar Retail is running its order-processing application on a Compute Engine VM named orders-prod-vm. The ... |
| [E4Q12](../../99-practice-exams/exam-4.md#q12) | HarborTrack runs inventory applications on Compute Engine and in its private data center. Its Google Cloud Vir... |
| [E4Q43](../../99-practice-exams/exam-4.md#q43) | LumenFleet Systems wants to deploy a Compute Engine VM for a new route-planning service. The destination Googl... |
| [E5Q22](../../99-practice-exams/exam-5.md#q22) | PixelForge Labs is developing a web platform that automatically creates animated product previews. Its model u... |
| [E5Q28](../../99-practice-exams/exam-5.md#q28) | AsterPeak Manufacturing is migrating its global supply-chain planning platform to Google Cloud. The platform u... |
| [E5Q32](../../99-practice-exams/exam-5.md#q32) | NovaCart, an online retail company, has created a Google Cloud project named novacart-prod by using the Google... |

## Official documentation

- [Compute / GPUs](https://docs.cloud.google.com/compute/docs/gpus)
- [Compute / Accelerator optimized machines](https://docs.cloud.google.com/compute/docs/accelerator-optimized-machines)
- [Compute / Modify persistent disk](https://docs.cloud.google.com/compute/docs/disks/modify-persistent-disk)
- [Compute / Create VM with GPUs](https://docs.cloud.google.com/compute/docs/gpus/create-vm-with-gpus)
- [Compute / Install drivers GPU](https://docs.cloud.google.com/compute/docs/gpus/install-drivers-gpu)
- [Compute / Preventing accidental VM deletion](https://docs.cloud.google.com/compute/docs/instances/preventing-accidental-vm-deletion)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
