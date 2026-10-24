# Identity-Aware Proxy (IAP)

> **Level:** Intermediate · **Topic:** [Identity and security](../README.md) · **Cited in:** 4 practice-exam questions

## What it is

Has two uses. One protects web applications. The other is **TCP forwarding**, which provides SSH and RDP without an external IP.

## Trigger

"VMs with internal IPs, many SSH accesses, nothing to configure per VM" ([E2Q40](../../99-practice-exams/exam-2.md#q40)). Allow `35.235.240.0/20` in the firewall and use `--tunnel-through-iap` ([E1Q3](../../99-practice-exams/exam-1.md#q3)).

## Watch out

Requires a Google identity. For a contractor without a Google account, use an SSH key in the metadata ([E1Q32](../../99-practice-exams/exam-1.md#q32), [E4Q10](../../99-practice-exams/exam-4.md#q10)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q3](../../99-practice-exams/exam-1.md#q3) | CloudNest Retail operates several Linux virtual machines in Google Cloud for its internal inventory platform. ... |
| [E1Q32](../../99-practice-exams/exam-1.md#q32) | Northstar Media runs Linux-based build servers on Compute Engine. A new support vendor must connect to these v... |
| [E2Q40](../../99-practice-exams/exam-2.md#q40) | AuroraFleet, a logistics analytics company, runs 11 Linux virtual machines on Compute Engine and expects to de... |
| [E4Q10](../../99-practice-exams/exam-4.md#q10) | Northstar Analytics hosts an internal reporting service on a Linux Compute Engine VM. A temporary support engi... |

## Official documentation

- [IAP / Using tcp forwarding](https://docs.cloud.google.com/iap/docs/using-tcp-forwarding)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
