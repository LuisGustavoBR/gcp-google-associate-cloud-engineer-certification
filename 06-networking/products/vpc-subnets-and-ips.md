# VPC, Subnets, and IPs

> **Level:** Basic · **Topic:** [Networking](../README.md) · **Cited in:** 6 practice-exam questions

## What it is

Global, private network. Subnets are regional, and the **primary range can be expanded** without disruption (the range can only grow).

## Triggers and facts

- Subnet out of IPs: expand the range, for example from /21 to /19 ([E1Q30](../../99-practice-exams/exam-1.md#q30), [E3Q44](../../99-practice-exams/exam-3.md#q44), [E4Q15](../../99-practice-exams/exam-4.md#q15)).
- Three tiers with firewall per IP range: one custom VPC and one subnet per tier ([E3Q1](../../99-practice-exams/exam-3.md#q1)).
- Migration keeping communication intact: create subnets with the same CIDRs and static internal IPs ([E2Q4](../../99-practice-exams/exam-2.md#q4)).
- Expose VMs internally only: do not assign an external IP ([E4Q12](../../99-practice-exams/exam-4.md#q12)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q30](../../99-practice-exams/exam-1.md#q30) | RideWave operates a fleet-management platform on Google Cloud. Its Compute Engine VM instances use a subnet in... |
| [E2Q4](../../99-practice-exams/exam-2.md#q4) | BrightRoute Logistics must move its dispatch and warehouse applications to Google Cloud before its colocation ... |
| [E3Q1](../../99-practice-exams/exam-3.md#q1) | ParcelForge is deploying a three-tier logistics platform in a dedicated Google Cloud project. The platform req... |
| [E3Q44](../../99-practice-exams/exam-3.md#q44) | BrightCart Commerce runs its application servers on Compute Engine virtual machines in a custom mode VPC netwo... |
| [E4Q12](../../99-practice-exams/exam-4.md#q12) | HarborTrack runs inventory applications on Compute Engine and in its private data center. Its Google Cloud Vir... |
| [E4Q15](../../99-practice-exams/exam-4.md#q15) | DataForge Labs runs an Apache Hadoop analytics workload on a Dataproc cluster in one VPC network. The cluster ... |

## Official documentation

- [VPC / Subnets](https://docs.cloud.google.com/vpc/docs/subnets)
- [VPC / Create modify VPC networks](https://docs.cloud.google.com/vpc/docs/create-modify-vpc-networks)
- [VPC / VPC](https://docs.cloud.google.com/vpc/docs/vpc)
- [VPC / VPC peering](https://docs.cloud.google.com/vpc/docs/vpc-peering)
- [VPC / Ip addresses](https://docs.cloud.google.com/vpc/docs/ip-addresses)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
