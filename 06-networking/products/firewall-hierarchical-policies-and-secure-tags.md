# Firewall, Hierarchical Policies, and Secure Tags (Cloud NGFW)

> **Level:** Intermediate · **Topic:** [Networking](../README.md) · **Cited in:** 7 practice-exam questions

## What it is

Firewall rules control traffic. Policies can be **hierarchical** (organization or folder) or network-level (global), and support **secure tags**.

## Triggers and facts

- Block SSH or RDP for the whole company: **hierarchical firewall policy** on the organization ([E1Q9](../../99-practice-exams/exam-1.md#q9), [E5Q18](../../99-practice-exams/exam-5.md#q18)).
- Same policy for several VPCs in the same project: **global network policy** associated with the VPCs ([E3Q34](../../99-practice-exams/exam-3.md#q34)).
- Ephemeral VMs (IP changes): **service account** or **secure tag** as source and target ([E1Q26](../../99-practice-exams/exam-1.md#q26), [E3Q42](../../99-practice-exams/exam-3.md#q42)).
- Egress only on approved ports: egress deny-all with priority 65000 and allow with priority 900 ([E1Q31](../../99-practice-exams/exam-1.md#q31)).
- Why the connection is blocked: the organization policy is evaluated before the project rule ([E3Q40](../../99-practice-exams/exam-3.md#q40)).

## Watch out

The network includes implied rules (ingress denied and egress allowed by default).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q9](../../99-practice-exams/exam-1.md#q9) | Northstar Media operates multiple Google Cloud projects for its video-streaming platform. The security team mu... |
| [E1Q26](../../99-practice-exams/exam-1.md#q26) | FreshBasket, an online grocery platform, runs PostgreSQL database VMs in data-subnet. Its checkout application... |
| [E1Q31](../../99-practice-exams/exam-1.md#q31) | ParcelPilot is deploying an order-processing application in a new Google Cloud VPC network. The application mu... |
| [E3Q34](../../99-practice-exams/exam-3.md#q34) | BlueHarbor Analytics operates five isolated VPC networks in a single Google Cloud project. Its security team n... |
| [E3Q40](../../99-practice-exams/exam-3.md#q40) | Northwind Health hosts a patient portal on a Compute Engine VM. A project administrator creates a VPC firewall... |
| [E3Q42](../../99-practice-exams/exam-3.md#q42) | BrightPath Health runs patient-processing and analytics VMs in multiple Google Cloud projects. The workloads a... |
| [E5Q18](../../99-practice-exams/exam-5.md#q18) | BlueHarbor Financial operates Windows-based workloads in multiple Google Cloud projects. Its security team mus... |

## Official documentation

- [Firewall / Firewall policies](https://docs.cloud.google.com/firewall/docs/firewall-policies)
- [Firewall / Firewall policies rule details](https://docs.cloud.google.com/firewall/docs/firewall-policies-rule-details)
- [Firewall / Firewall policies rule eval order](https://docs.cloud.google.com/firewall/docs/firewall-policies-rule-eval-order)
- [Firewall / Firewall policies overview](https://docs.cloud.google.com/firewall/docs/firewall-policies-overview)
- [Firewall / Firewalls](https://docs.cloud.google.com/firewall/docs/firewalls)
- [Firewall / Network firewall policies](https://docs.cloud.google.com/firewall/docs/network-firewall-policies)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
