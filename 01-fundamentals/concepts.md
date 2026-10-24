# Fundamentals: concepts from basic to advanced

> Official exam guide sections covered: 1.1 (see the [exam guide map](../00-start-here/exam-guide-map.md)).

## Basic

Everything in Google Cloud lives inside a **project**, and projects are organized in a **resource hierarchy**:

```
Organization  (tied to a Cloud Identity / Workspace domain)
  |-- Folders  (optional, can be nested)
        |-- Projects
              |-- Resources (VMs, buckets, topics, ...)
```

- The **organization** is the root node. It exists only when you have a verified domain in Cloud Identity or Google Workspace. Without it you only have standalone projects.
- **Folders** group projects (by team, environment, or business unit). They are the right place to apply a policy to "a group of projects".
- A **project** is the unit of billing association, API enablement, quotas, and IAM. Deleting a project deletes everything inside it.
- IAM policies and Organization Policies attach at any node and **inherit downward**.

### Project identifiers

| Identifier | Who sets it | Unique | Can change |
|---|---|---|---|
| Project name | You | No | Yes |
| Project ID | You (at creation) | Globally | No |
| Project number | Google | Globally | No |

Use the project ID in `gcloud` commands and in resource names. The project number appears in service-agent and default service account emails. A deleted project ID cannot be reused.

### Regions, zones, and multi-regions

- A **region** is a geographic area (for example `us-central1`). It contains several **zones**, typically three or more (for example `us-central1-a`).
- A zone is a failure domain. A zonal resource (a VM, a zonal disk) is lost if its zone fails.
- A **multi-region** (for example `US`, `EU`) is a larger geography offered by some services (Cloud Storage, BigQuery, Spanner configurations). It trades higher cost or latency for geo-redundancy.
- Resource scope matters: a VPC network is **global**, a subnet is **regional**, a VM is **zonal**, a snapshot and an image are **global**, a static external IP is **regional or global**.
- Availability pattern: spread across zones to survive a zone failure, use a regional or multi-region service to survive a region failure.

### Cloud Console, Cloud Shell, and gcloud

- **Cloud Console**: the web UI.
- **Cloud Shell**: a browser terminal with `gcloud`, `kubectl`, and an editor preinstalled. The VM is temporary, but your `$HOME` directory persists (about 5 GB).
- **gcloud CLI**: installed locally or used in Cloud Shell. It authenticates as you (`gcloud auth login`) and calls the same APIs as the Console.

## Intermediate

### gcloud configurations and common commands

A **configuration** is a named set of properties (account, project, default region and zone). Use one per environment or customer.

```bash
gcloud init                                   # guided first-time setup
gcloud auth login                             # sign in as a user
gcloud config set project my-project-id
gcloud config set compute/region us-central1
gcloud config set compute/zone us-central1-a

gcloud config configurations create dev       # new named configuration
gcloud config configurations activate dev
gcloud config configurations list
gcloud config list                            # show active properties

gcloud projects list
gcloud compute instances list --filter="zone:us-central1-a" --format="table(name,status)"
gcloud compute instances list --project=other-project   # per-command override
```

Precedence, highest first: command-line flag (`--project`), environment variable (`CLOUDSDK_CORE_PROJECT`), active configuration. `CLOUDSDK_*` variables also cover proxy settings.

`gcloud auth login` authenticates the CLI. `gcloud auth application-default login` creates credentials for your own code (see the identity page). They are separate.

### Enabling APIs

Each service must be **enabled per project** before you create resources. A `403` with `SERVICE_DISABLED` or "API has not been used in project" means the API is off.

```bash
gcloud services enable compute.googleapis.com container.googleapis.com
gcloud services list --enabled
```

Enabling needs permission such as Service Usage Admin. Billable services also need the project linked to a billing account.

### Quotas

- **Quotas** are per-project limits that protect you and other customers. Examples: CPUs per region, in-use IP addresses, API requests per minute.
- They are checked **per region** or globally depending on the metric, so a new region can hit a quota even if another region has headroom.
- **Allocation quotas** cap how much you hold at once (CPUs). **Rate quotas** cap requests over time.
- View them in Console under IAM & Admin > Quotas & System Limits. You can ask for an increase from the same page. Some are approved automatically and others are reviewed.
- **System limits** are fixed and cannot be raised.
- A budget never enforces a quota. Quotas and budgets are unrelated controls.

### Labels vs network tags vs resource tags

| | Labels | Network tags | Resource tags (Resource Manager) |
|---|---|---|---|
| Form | key=value | plain string | key/value defined under an org or project |
| Applied to | Many resource types | Compute Engine VMs | Org, folder, project, and some resources |
| Inherited | No | No | Yes, down the hierarchy |
| Used for | Cost reports, billing export filtering, grouping, automation | Firewall rules and routes targeting | IAM conditions, Organization Policy conditions, firewall policies (secure tags) |

Do not confuse them: a label does not affect firewall behavior, and a network tag does not appear as a cost dimension.

## Advanced

### Moving and protecting projects

- A project can be moved between folders or organizations. It then **inherits** the new parent's IAM and Organization Policies, and loses the old parent's. Project-level bindings move with it.
- Moving a project between organizations is done with the Resource Manager `projects.move` operation and needs permission on both sides.
- A **project lien** blocks deletion of the project. It does not block billing changes.
- A deleted project is recoverable for roughly 30 days before permanent removal.

### Designing the hierarchy

- Mirror policy boundaries, not the org chart. Put things that share policy in the same folder (for example `prod`, `non-prod`, `sandbox`).
- Apply organization-wide controls at the **organization**, group-specific ones at a **folder**, and exceptions at a project.
- Use separate projects to isolate quotas, billing, and blast radius.
- The user who creates a project becomes its Owner in the project IAM policy. There is no "creator" label.

### Defaults and automation

- Setting default region and zone saves typing but can hide mistakes. Always check `gcloud config list` before running destructive commands.
- Use `--format` (json, yaml, table, value) and `--filter` to script against `gcloud` output.
- In CI, prefer short-lived credentials or federation over downloaded service account keys.

## Exam tips

- "Apply to all current and future projects of the company": attach at the **organization**. "A group of projects": a **folder**.
- Allow policies inherit additively; a child cannot remove a parent's grant.
- Project ID is unique and immutable. Name is not unique and can change.
- A resource creation fails with `SERVICE_DISABLED`: `gcloud services enable ...`.
- Quota error in a region: request an increase for that region's quota, or pick another region.
- Labels are for organization and cost analysis; network tags are for firewall rules and routes; resource tags are inherited and usable in policy conditions.
- Set a default zone with `gcloud config set compute/zone`; use separate configurations to switch between projects or accounts.
- Cloud Shell keeps only `$HOME` between sessions.

## What appeared on the practice exams

Condensed from the 300 practice questions. Question IDs link to the full question and explanation.

### Environment structure

- **Hierarchy:** Organization > Folders > Projects > Resources. IAM and Org Policy are **inherited** downward.
- **Projects:** the ID is unique and immutable. Each project has its own billing, quotas and lifecycle.
- **Billing:**
  - A central Cloud Billing account, with **Project Creator** and **Billing Account User** granted to engineers.
  - To change the billing account, link the project to the new account.
  - A **Budget** only alerts, it does not block anything.
  - **Billing export to BigQuery** should be enabled early. It is **not retroactive**.
  - For detailed cost, use the *detailed* export.
- **Pricing:** Pricing Calculator to estimate the cost of an architecture.
- **Moving a project between organizations:** `projects.move`.
- **Cloud Identity / Workspace:** unmanaged accounts are migrated through a transfer invitation. **Google Cloud Directory Sync** syncs users from LDAP/AD.

### gcloud and CLI

- Before using it, run `gcloud auth login` and `gcloud config set project`.
- **Default configuration:**
  - `gcloud config set compute/zone`
  - `gcloud config set container/cluster`
  - Proxy credentials through the `CLOUDSDK_PROXY_*` environment variables.
- **Service account:** `gcloud auth activate-service-account --key-file`.
- **Other commands that appeared:**
  - `gcloud pubsub subscriptions pull NAME --auto-ack`
  - `gcloud storage rsync` (for synchronization, together with cron)
  - `gcloud projects get-iam-policy`
  - `gcloud asset search-all-resources` (organization-wide inventory)
  - `gcloud iam roles copy --dest-organization`
  - `gcloud compute ssh --tunnel-through-iap`

## Official documentation
- [Resource hierarchy](https://docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)
- [Creating and managing projects](https://docs.cloud.google.com/resource-manager/docs/creating-managing-projects)
- [Labels overview](https://docs.cloud.google.com/resource-manager/docs/labels-overview)
- [Global, regional, and zonal resources](https://docs.cloud.google.com/compute/docs/regions-zones/global-regional-zonal-resources)
- [Changing the default region and zone](https://docs.cloud.google.com/compute/docs/regions-zones/changing-default-zone-region)
- [gcloud CLI configurations](https://docs.cloud.google.com/sdk/docs/configurations)
- [Enabling and disabling services](https://docs.cloud.google.com/service-usage/docs/enable-disable)
- [Compute Engine quotas and limits](https://docs.cloud.google.com/compute/quotas-limits)

[Back to topic](README.md)
