# Study plan

## Suggested study order

1. **Fundamentals** ([01](../01-fundamentals/README.md)): resource hierarchy, projects, gcloud, APIs and quotas.
2. **Identity and security** ([02](../02-identity-security/README.md)): IAM, service accounts, federation, Organization Policy. This is the most referenced area of the exam.
3. **Compute and containers** ([03](../03-compute-containers/README.md)) and **events** ([04](../04-events-integration/README.md)).
4. **Storage, databases and data** ([05](../05-storage-databases-data/README.md)).
5. **Networking** ([06](../06-networking/README.md)).
6. **Operations and cost** ([07](../07-operations-cost/README.md)) and **IaC and platform tooling** ([08](../08-iac-platform-ai/README.md)).
7. Read the [trigger cheat sheet](trigger-cheatsheet.md), then take the [practice exams](../99-practice-exams/README.md) and use the "Related notes" links to review what you get wrong.

## Areas that need extra attention

- **Identity and IAM:** Workload vs. Workforce Identity Federation, impersonation, service agents, service accounts of nodes and VMs, groups, and where to apply Organization Policy.
- **Choosing a serverless service:** Cloud Run service vs. job vs. function vs. App Engine; GKE Autopilot vs. Standard.
- **Networking:** firewall rules (by service account and tag, hierarchical), Private Google Access, Cloud NAT, Private Service Connect, load balancer types.
- **Cloud SQL:** Auth Proxy and IAM authentication, backup vs. export.
- **"Choose two" questions:** read the stem for two distinct requirements, one per answer. See the [multi-answer question list](../99-practice-exams/multi-answer-questions.md).
- **Newer products:** Database Center, Managed Lustre, NetApp Volumes, Application Design Center, Cloud Hub, Personalized Service Health, Observability Analytics.
- **General rule:** the right answer is usually the most managed, most native option with the lowest operational effort. Options that are plausible but need more manual work are the usual distractors.

## Most-covered topics

Approximate number of practice-exam questions touching each topic, by keyword (a question can count in several):

Compute Engine/MIG (79) > IAM/service accounts (72) > Billing/cost (56) > gcloud/CLI (55) > Cloud Storage (50) > GKE (39) > VPC/firewall (34) > Cloud Run (33) > BigQuery (26) > Logging/Monitoring (25) > Migration/data transfer (23) > Pub/Sub and events (20) > Cloud SQL (19) > NoSQL databases/Spanner (18) > Org Policy/hierarchy (16) > Cloud Identity/groups (15).

[Back](README.md)
