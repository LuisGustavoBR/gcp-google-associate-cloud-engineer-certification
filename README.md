# Google Cloud Associate Cloud Engineer (ACE) study repo

Study notes for the Associate Cloud Engineer certification, organized by topic from basic concepts to the advanced points that appeared on six practice exams (300 questions). Every product page lists the trigger phrases that point to it, the traps, the related practice questions and official documentation links.

## How to use it

1. Read [00-start-here](00-start-here/README.md) for the exam guide map and the study plan.
2. Go through the topics in order. In each topic: `concepts.md` (basic to advanced), then the products table.
3. Test yourself with the "Related practice questions" of each product, then do the full [practice exams](99-practice-exams/README.md).
4. Before the exam, read the [trigger cheat sheet](00-start-here/trigger-cheatsheet.md) and each topic's `common-traps.md`.

## Repository map

| Directory | What is in it |
|---|---|
| [00-start-here](00-start-here/README.md) | Exam guide map, study plan, trigger cheat sheet, resources |
| [01-fundamentals](01-fundamentals/README.md) | Resource hierarchy, projects, regions and zones, the gcloud toolchain, APIs and quotas. (1 products) |
| [02-identity-security](02-identity-security/README.md) | IAM, service accounts, identity federation, Organization Policy, encryption, secrets and audit logs. (16 products) |
| [03-compute-containers](03-compute-containers/README.md) | Compute Engine, managed instance groups, GKE, Cloud Run, App Engine and Artifact Registry. (13 products) |
| [04-events-integration](04-events-integration/README.md) | Pub/Sub, Eventarc, Cloud Scheduler and Cloud Tasks: asynchronous, event-driven and scheduled work. (4 products) |
| [05-storage-databases-data](05-storage-databases-data/README.md) | Cloud Storage, disks and file storage, relational and NoSQL databases, BigQuery, Dataflow and data transfer. (17 products) |
| [06-networking](06-networking/README.md) | VPC, firewalls, NAT, private access, load balancing, DNS and hybrid connectivity. (12 products) |
| [07-operations-cost](07-operations-cost/README.md) | Cloud Monitoring, Cloud Logging, health and diagnostics tools, billing, budgets and quotas. (9 products) |
| [08-iac-platform-ai](08-iac-platform-ai/README.md) | Terraform, Infrastructure Manager, Config Connector, templates, Marketplace, workstations and Gemini tools. (11 products) |
| [99-practice-exams](99-practice-exams/README.md) | The 6 practice exams with explanations, plus the multi-answer question list |
| [glossary.md](glossary.md) | A-Z index of every product page |

## Conventions

- **Level:** Basic (core service), Intermediate (needs a few design choices) or Advanced (commonly confused or newer products).
- **Trigger:** a phrase in the question stem that points to the product.
- **IDs:** `E5Q36` means practice exam 5, question 36. Every ID links to the question.
- Product names change often (Cloud Functions is now Cloud Run functions, Log Analytics is now Observability Analytics, Data Studio is Looker Studio). Check the official documentation when a name looks unfamiliar.
