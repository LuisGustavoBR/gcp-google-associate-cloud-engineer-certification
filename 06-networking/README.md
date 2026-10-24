# 06 · Networking

VPC, firewalls, NAT, private access, load balancing, DNS and hybrid connectivity.

**Exam guide sections:** 2.3, 3.5, 4.5

## Study path

1. [Concepts, basic to advanced](concepts.md)
2. Products, grouped by level (tables below). Each page has triggers, pitfalls, related questions and official links.
3. [Common traps](common-traps.md)
4. Practice: use the "Related practice questions" table on each product page, then the full exams in [99-practice-exams](../99-practice-exams/README.md).

## Basic products

| Product | Cited in | What it is |
|---|---|---|
| [VPC, Subnets, and IPs](products/vpc-subnets-and-ips.md) | 6 q. | Global, private network. |
| [Cloud DNS](products/cloud-dns.md) | 3 q. | Public and private zones (authorize the VPC to query the private zone). |

## Intermediate products

| Product | Cited in | What it is |
|---|---|---|
| [Firewall, Hierarchical Policies, and Secure Tags (Cloud NGFW)](products/firewall-hierarchical-policies-and-secure-tags.md) | 7 q. | Firewall rules control traffic. |
| [Cloud Load Balancing](products/cloud-load-balancing.md) | 4 q. |  |
| [Firewall Rules Logging and VPC Flow Logs](products/firewall-rules-logging-and-vpc-flow-logs.md) | 3 q. | The first shows whether a specific rule was triggered. |
| [Cloud NAT](products/cloud-nat.md) | 2 q. | Outbound internet access for VMs and nodes without an external IP. |
| [Cloud Router, Cloud VPN, and Cloud Interconnect](products/cloud-router-cloud-vpn-and-cloud-interconnect.md) | 2 q. | Router provides dynamic routing via BGP and is also required for Cloud NAT. |
| [VPC Network Peering and Shared VPC](products/vpc-network-peering-and-shared-vpc.md) | 2 q. | Peering connects two VPCs simply and cheaply, and the IP ranges cannot overlap. |
| [Network Service Tiers](products/network-service-tiers.md) | 1 q. | *Premium* uses Google's global network. |
| [Private Google Access](products/private-google-access.md) | 1 q. | Lets VMs with only an internal IP reach Google APIs, enabled per subnet. |
| [Cloud Armor and Cloud CDN](products/cloud-armor-and-cloud-cdn.md) | distractor only | Cloud Armor is WAF and DDoS protection, attached to the external load balancer. |

## Advanced products

| Product | Cited in | What it is |
|---|---|---|
| [Private Service Connect](products/private-service-connect.md) | 1 q. | Private endpoint with an internal IP for Google services or services published by third parties. |

---
[Repository home](../README.md) · [Glossary A-Z](../glossary.md)
