# 02 · Identity and security

IAM, service accounts, identity federation, Organization Policy, encryption, secrets and audit logs.

**Exam guide sections:** 1.1, 5.1, 5.2

## Study path

1. [Concepts, basic to advanced](concepts.md)
2. Products, grouped by level (tables below). Each page has triggers, pitfalls, related questions and official links.
3. [Common traps](common-traps.md)
4. Practice: use the "Related practice questions" table on each product page, then the full exams in [99-practice-exams](../99-practice-exams/README.md).

## Basic products

| Product | Cited in | What it is |
|---|---|---|
| [IAM (roles, bindings, and service accounts)](products/iam.md) | 15 q. | Who (principal) can do what (role) on which resource. |
| [Secret Manager](products/secret-manager.md) | 1 q. | Stores passwords and API keys, with versions and IAM-based control. |
| [Sensitive Data Protection](products/sensitive-data-protection.md) | distractor only | Current name of Cloud DLP. |

## Intermediate products

| Product | Cited in | What it is |
|---|---|---|
| [Organization Policy Service](products/organization-policy-service.md) | 8 q. | Enforces constraints on everything below the node where it is applied. |
| [Cloud KMS](products/cloud-kms.md) | 5 q. | Manages encryption keys (CMEK). |
| [Cloud Audit Logs](products/cloud-audit-logs.md) | 4 q. | Admin Activity (always on), Data Access (must be enabled, except in BigQuery), and System Event. |
| [Identity-Aware Proxy (IAP)](products/identity-aware-proxy.md) | 4 q. | Has two uses. |
| [Cloud Asset Inventory](products/cloud-asset-inventory.md) | 3 q. | Searchable inventory of resources and IAM policies across the whole organization. |
| [Cloud Identity and Google Cloud Directory Sync](products/cloud-identity-and-google-cloud-directory-sync.md) | 3 q. | Cloud Identity manages users, groups, and MFA. |
| [OS Login](products/os-login.md) | 3 q. | Manages SSH access centrally through IAM and groups. |
| [Application Default Credentials (ADC)](products/application-default-credentials.md) | 2 q. | The libraries' strategy for finding credentials automatically. |
| [Cloud SQL Auth Proxy](products/cloud-sql-auth-proxy.md) | 1 q. | Encrypted, IAM-authorized connection to Cloud SQL, without managing certificates (E1Q17). |
| [OS Config / VM Manager](products/os-config-vm-manager.md) | 1 q. | Manages patches and generates OS vulnerability reports. |

## Advanced products

| Product | Cited in | What it is |
|---|---|---|
| [Workload Identity Federation and Workforce Identity Federation](products/workload-identity-federation-and-workforce-identity-federati.md) | 7 q. | The first is for external workloads (GitHub Actions, AWS, another cloud), with a pool, an OIDC provider, and service account impersonation. |
| [Service account impersonation](products/service-account-impersonation.md) | 3 q. | The developer assumes the identity of the service account without downloading a key. |
| [Workload Identity Federation for GKE](products/workload-identity-federation-for-gke.md) | 3 q. | The Pod uses the identity of a Kubernetes ServiceAccount to access Google APIs, with no key. |

---
[Repository home](../README.md) · [Glossary A-Z](../glossary.md)
