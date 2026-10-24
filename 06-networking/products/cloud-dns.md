# Cloud DNS

> **Level:** Basic · **Topic:** [Networking](../README.md) · **Cited in:** 3 practice-exam questions

## What it is

**public** and **private** zones (authorize the VPC to query the private zone).

## Triggers and facts

- Public domain pointing to the load balancer: **A** record ([E3Q7](../../99-practice-exams/exam-3.md#q7)).
- Internal name for the ILB: private zone ([E3Q8](../../99-practice-exams/exam-3.md#q8)).
- **CNAME** is not valid at the apex. Use A on the root domain and CNAME for subdomains ([E1Q29](../../99-practice-exams/exam-1.md#q29)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q29](../../99-practice-exams/exam-1.md#q29) | HarborView Media hosts its public website behind a Google Cloud load balancer with a reserved IPv4 address. Th... |
| [E3Q7](../../99-practice-exams/exam-3.md#q7) | EventSphere is deploying a public ticket-booking website on Compute Engine virtual machines in a managed insta... |
| [E3Q8](../../99-practice-exams/exam-3.md#q8) | Northstar Health is launching an employee scheduling portal behind an internal Application Load Balancer. The ... |

## Official documentation

- [DNS / Set up DNS records domain name](https://docs.cloud.google.com/dns/docs/set-up-dns-records-domain-name)
- [DNS / Best practices](https://docs.cloud.google.com/dns/docs/best-practices)
- [DNS / Key terms](https://docs.cloud.google.com/dns/docs/key-terms)
- [DNS / Records overview](https://docs.cloud.google.com/dns/docs/records-overview)
- [DNS / Server policies overview](https://docs.cloud.google.com/dns/docs/server-policies-overview)
- [DNS / Zones overview](https://docs.cloud.google.com/dns/docs/zones/zones-overview)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
