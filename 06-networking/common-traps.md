# Networking: common traps

Rules that decide questions people often get wrong. Read these after the concepts page: they are the traps the practice exams used.

| Question | Rule to remember |
|---|---|
| [E1Q26](../99-practice-exams/exam-1.md#q26), [E3Q42](../99-practice-exams/exam-3.md#q42) | VMs replaced frequently (IP changes): firewall by **service account** or by **secure tags**. Do not use IP or network tag, which are less secure. |
| [E4Q7](../99-practice-exams/exam-4.md#q7), [E6Q25](../99-practice-exams/exam-6.md#q25) | VM with only an internal IP talking to Google APIs: **Private Google Access on the subnet**. For general internet egress: **Cloud NAT**. |
| [E4Q31](../99-practice-exams/exam-4.md#q31) | HA VPN with Cloud Router/BGP: use a **custom mode** VPC and **active-passive** routing to preserve capacity. |
| [E1Q30](../99-practice-exams/exam-1.md#q30), [E1Q6](../99-practice-exams/exam-1.md#q6), [E3Q44](../99-practice-exams/exam-3.md#q44), [E4Q15](../99-practice-exams/exam-4.md#q15) | Subnet out of IPs: **expand the primary range** (it can only grow, with no disruption). |
| [E1Q9](../99-practice-exams/exam-1.md#q9), [E5Q18](../99-practice-exams/exam-5.md#q18), [E3Q40](../99-practice-exams/exam-3.md#q40) | Central rule for the whole organization: **hierarchical firewall policy** at the organization. |
| [E3Q27](../99-practice-exams/exam-3.md#q27), [E5Q19](../99-practice-exams/exam-5.md#q19) | Check whether a firewall rule is blocking traffic: **Firewall Rules Logging**. |
| [E6Q43](../99-practice-exams/exam-6.md#q43) | Metadata and bytes between regions, without packet contents: **VPC Flow Logs**. |
| [E4Q23](../99-practice-exams/exam-4.md#q23), [E6Q36](../99-practice-exams/exam-6.md#q36) | TCP/UDP without a proxy, preserving the source IP: **Network Load Balancer (passthrough)**. HTTP(S): **Application Load Balancer**. |
| [E1Q47](../99-practice-exams/exam-1.md#q47) | Two VPCs with different ranges, simple and cheap: **VPC Peering**. |
| [E4Q27](../99-practice-exams/exam-4.md#q27) | Landing zone with a shared VPC: **Shared VPC** (host project and service projects). |
| [E6Q14](../99-practice-exams/exam-6.md#q14) | **Standard Tier** (cheaper) for dev and **Premium Tier** for production. |

[Back to topic](README.md)
