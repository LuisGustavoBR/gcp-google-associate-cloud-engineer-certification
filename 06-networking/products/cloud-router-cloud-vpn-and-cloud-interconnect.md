# Cloud Router, Cloud VPN, and Cloud Interconnect

> **Level:** Intermediate · **Topic:** [Networking](../README.md) · **Cited in:** 2 practice-exam questions

## What it is

Router provides dynamic routing via BGP and is also required for Cloud NAT. VPN is an IPsec tunnel over the internet (the HA version has a 99.99% SLA). Interconnect is a dedicated or partner physical connection.

## Trigger

"exchange routes dynamically with the on-premises router" points to Cloud Router and BGP ([E4Q31](../../99-practice-exams/exam-4.md#q31)). "Keep the same capacity when a path fails": **active-passive** routing, on a custom VPC. Private DNS to change the on-premises database IP in a single place ([E3Q41](../../99-practice-exams/exam-3.md#q41)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E3Q41](../../99-practice-exams/exam-3.md#q41) | BrightCart operates order-processing applications on Compute Engine in a Google Cloud VPC network. The VPC is ... |
| [E4Q31](../../99-practice-exams/exam-4.md#q31) | HarborLink Media is connecting a new Google Cloud VPC network to its corporate data center. The VPC must use t... |

## Official documentation

- [Network connectivity / Best practices](https://docs.cloud.google.com/network-connectivity/docs/vpn/concepts/best-practices)
- [Network connectivity / Choosing networks routing](https://docs.cloud.google.com/network-connectivity/docs/vpn/concepts/choosing-networks-routing)
- [Network connectivity / Topologies](https://docs.cloud.google.com/network-connectivity/docs/vpn/concepts/topologies)
- [Network connectivity / Overview](https://docs.cloud.google.com/network-connectivity/docs/interconnect/concepts/overview)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
