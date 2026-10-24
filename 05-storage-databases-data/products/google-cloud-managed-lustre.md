# Google Cloud Managed Lustre

> **Level:** Advanced · **Topic:** [Storage, databases and data](../README.md) · **Cited in:** 4 practice-exam questions

## What it is

Fully managed parallel file system for AI/ML, HPC, and rendering. It delivers very high throughput to hundreds or thousands of workers accessing the same files at the same time. It has a CSI driver for GKE.

## Trigger

"thousands of VMs reading and writing the same set of files", "high parallel throughput", "distributed training with a PersistentVolumeClaim".

## Watch out

For simple legacy NFS, the answer is Filestore. For enterprise SMB, it is NetApp Volumes.

## Where it appeared

[E5Q49](../../99-practice-exams/exam-5.md#q49), [E6Q23](../../99-practice-exams/exam-6.md#q23), [E6Q11](../../99-practice-exams/exam-6.md#q11) (and as a distractor in [E6Q49](../../99-practice-exams/exam-6.md#q49)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E5Q49](../../99-practice-exams/exam-5.md#q49) | NovaRender Studios runs a large-scale visual-effects pipeline across several hundred Compute Engine instances.... |
| [E6Q11](../../99-practice-exams/exam-6.md#q11) | NeuralVista Labs runs distributed machine learning jobs on Google Kubernetes Engine. Multiple training Pods ne... |
| [E6Q23](../../99-practice-exams/exam-6.md#q23) | PixelForge Studios operates a large rendering farm with 4,500 Compute Engine workers. The workers must simulta... |
| [E6Q49](../../99-practice-exams/exam-6.md#q49) | Northbridge Design Group is moving its Windows-based CAD document repository to Google Cloud. Employees and en... |

## Official documentation

- [Managed lustre / Overview](https://docs.cloud.google.com/managed-lustre/docs/overview)
- [Kubernetes engine / Managed lustre](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/managed-lustre)
- [Kubernetes engine / Lustre csi driver new volume](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/persistent-volumes/lustre-csi-driver-new-volume)
- [Managed lustre / Create instance](https://docs.cloud.google.com/managed-lustre/docs/create-instance)
- [Managed lustre / Transfer data](https://docs.cloud.google.com/managed-lustre/docs/transfer-data)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
