# IaC, platform and AI tooling: concepts from basic to advanced

> Official exam guide sections covered: 3.6 (see the [exam guide map](../00-start-here/exam-guide-map.md)).

## Basic

### Infrastructure as Code (IaC)

IaC describes infrastructure in files that are versioned, reviewed and applied by a tool, instead of clicking in the console or running ad hoc commands.

- **Declarative** IaC (Terraform, Config Connector) states the desired end state. The tool computes the difference and converges to it. Re-running is safe.
- **Imperative** scripts (a series of `gcloud` commands) list steps. Re-running them can fail or create duplicates.
- Benefits: repeatable environments, peer review through pull requests, drift detection and an audit trail.

### Terraform

Terraform is an open source, multi-cloud IaC tool. It uses **providers** (for Google Cloud: `google` and `google-beta`) to call APIs.

Workflow:

1. `terraform init` downloads providers and modules and configures the backend.
2. `terraform plan` previews changes without making them.
3. `terraform apply` creates or changes resources (to apply exactly what was reviewed, use `plan -out` and apply that file).
4. `terraform destroy` removes the resources.

```hcl
terraform {
  required_providers {
    google = { source = "hashicorp/google" }
  }
  backend "gcs" {
    bucket = "my-tf-state-bucket"
    prefix = "prod/network"
  }
}

provider "google" {
  project = var.project_id
  region  = "us-central1"
}

resource "google_storage_bucket" "logs" {
  name     = "${var.project_id}-logs"
  location = "US"
  uniform_bucket_level_access = true
}
```

```bash
terraform init
terraform plan -out=tfplan
terraform apply tfplan
```

### Other tools in the toolbox

| Tool | What it is |
|---|---|
| Terraform | Multi-cloud IaC with a large provider ecosystem |
| Infrastructure Manager | Google Cloud managed service that runs Terraform for you |
| Config Connector | Manage Google Cloud resources as Kubernetes objects |
| Deployment Manager | Older Google-only IaC service. Legacy; see below |
| Helm | Packages Kubernetes applications, not cloud infrastructure |

## Intermediate

### Terraform state, backends and modules

- **State** maps your configuration to real resources. Never edit it by hand and never commit it to Git. It can contain secrets in plain text, so restrict access.
- A **remote backend** in a Cloud Storage bucket (`gcs`) lets a team share state and supports locking so two runs do not collide. The bucket must exist before `terraform init`. Turning on Object Versioning on that bucket lets you recover earlier states.
- **Modules** are reusable groups of resources with inputs and outputs. Use them to enforce standards (for example, a network or a hardened bucket). Google publishes blueprints built from modules (the Cloud Foundation Toolkit).
- Common layout: one root configuration per application or environment, each with its own state.
- Authentication uses Application Default Credentials. Prefer an attached service account, impersonation, or Workload Identity Federation over downloaded keys.

```hcl
module "network" {
  source  = "terraform-google-modules/network/google"
  version = "~> 9.0"  # pin to a current major version
  project_id   = var.project_id
  network_name = "prod-vpc"
  subnets = [{
    subnet_name   = "web"
    subnet_ip     = "10.10.0.0/24"
    subnet_region = "us-central1"
  }]
}
```

### Infrastructure Manager

Infrastructure Manager deploys and manages resources from Terraform configurations, running Terraform in a managed way. A **deployment** has revisions, and a **preview** shows the plan (like `terraform plan`) before you apply. The configuration can come from a Git repository or local source, and a service account you choose performs the changes.

```bash
gcloud infra-manager deployments apply \
    projects/PROJECT/locations/us-central1/deployments/my-deploy \
    --service-account=projects/PROJECT/serviceAccounts/deployer@PROJECT.iam.gserviceaccount.com \
    --local-source=. --input-values=project_id=PROJECT
```

> The flags above were written from memory. Confirm them in the Infrastructure Manager documentation before relying on them.

### Deployment Manager (be careful)

Deployment Manager is Google's older, Google Cloud-only IaC service using YAML, Jinja or Python templates. It is a legacy product that Google is retiring. Google points customers to Infrastructure Manager (Terraform) for new work. Check the current Deployment Manager documentation for the official end-of-support date and do not start new projects with it.

### Config Connector

Config Connector is a Kubernetes add-on that lets you declare Google Cloud resources (buckets, Pub/Sub topics, Cloud SQL) as custom resources in YAML. A controller keeps reality equal to the YAML, which fits GitOps. **Deleting the Kubernetes object deletes the real resource**, unless the deletion policy annotation is set to `abandon`.

```yaml
apiVersion: storage.cnrm.cloud.google.com/v1beta1
kind: StorageBucket
metadata:
  name: my-config-connector-bucket
  annotations:
    cnrm.cloud.google.com/deletion-policy: abandon
spec:
  location: US
  uniformBucketLevelAccess: true
```

## Advanced

### Platform tooling for teams

- **Secure Source Manager:** managed, private Git hosting with branches, pull requests and review. Use it for peer review of infrastructure code. A Cloud Storage bucket stores files but offers no code review.
- **Application Design Center:** design applications from approved components and templates (including Terraform modules) in shared catalogs, then deploy them through a self-service flow. Platform teams standardize architectures without approving every deployment.
- **Google Cloud Marketplace:** a catalog of ready-to-deploy solutions (for example CMS, Jenkins, partner databases) from Google and partners. Deployment can use the console, and some listings support command line or Terraform deployment. Usage appears on your Google Cloud bill.
- **Cloud Workstations:** managed, browser-accessible development environments. A **workstation configuration** defines the machine type, a container image, persistent home disk and idle timeout. Standardizes tooling across engineers and shuts down idle machines to save cost. Configuration changes apply to a workstation after it restarts.

A typical secure pipeline: code in Secure Source Manager, review by pull request, Terraform run through Infrastructure Manager with a preview, and state kept by the service.

### Gemini and AI tooling

- **Gemini Cloud Assist:** AI assistant in the Google Cloud console with built-in project context. Investigations help find the root cause of an issue across services, and Logs Explorer can explain a log entry. It must be enabled by an administrator (Gemini for Google Cloud API, and the user needs the Gemini for Google Cloud User role). Folder-level enablement is done in the Admin for Gemini page in the console.
- **Gemini CLI:** an open source AI agent that runs in your terminal and works with your local files and repository (for example generating code or Terraform). Its output must be reviewed, validated and checked with `terraform plan` before deployment.
- **Workbench:** managed JupyterLab notebook instances on the Gemini Enterprise Agent Platform (formerly Vertex AI), with common ML frameworks and optional GPUs, so you avoid maintaining notebook VMs.
- **Agent Runtime:** the managed place on the same platform to deploy, run and scale AI agents without managing Kubernetes or VMs. If the agent calls other services, grant roles to the service account it runs as.

```bash
npm install -g @google/gemini-cli
gemini -p "Explain this Terraform plan and list risky changes"
```

## Exam tips

- Reusable mandatory standards in Terraform: **modules**. Team-shared state: **gcs backend** on a protected bucket. One root configuration per application or environment.
- Preview before changing anything: `terraform plan` (not `validate`). In Infrastructure Manager, use a **preview**.
- Managed Terraform on Google Cloud: **Infrastructure Manager**. Do not pick Deployment Manager for new work.
- Manage Google Cloud resources from a Kubernetes cluster with YAML: **Config Connector**. Deleting the object removes the resource.
- Peer review of infrastructure code: **Secure Source Manager** (pull requests), not a bucket.
- Approved, self-service architecture templates: **Application Design Center**.
- Fast deployment of ready-made software: **Marketplace**.
- Standard developer environment with idle shutdown: **Cloud Workstations** configuration.
- Root cause across services or explain an unfamiliar log entry: **Gemini Cloud Assist**. Terminal agent for local code: **Gemini CLI**.
- Notebook without managing a VM: **Workbench**. Deploy and scale an AI agent: **Agent Runtime**.
- AI-generated code is never deployed unreviewed: validate and plan first.

## What appeared on the practice exams

Condensed from the 300 practice questions. Question IDs link to the full question and explanation.

### IaC and platform

- **Terraform:** reusable modules, remote state in the `gcs` backend, and one root directory per application.
- **Infrastructure Manager:** runs managed Terraform. Combine it with **Secure Source Manager** (Git) for review and preview.
- **Application Design Center:** approved templates and components for self-service.
- **Marketplace:** faster deployment of ready-made software.
- **AI (appears often in the newer practice exams):**
  - Gemini Cloud Assist (investigations, "Explain this log entry").
  - Gemini CLI (agent in the terminal).
  - Agent Runtime in the Gemini Enterprise Agent Platform.
  - Workbench for notebooks.

## Official documentation
- [Terraform on Google Cloud overview](https://docs.cloud.google.com/docs/terraform/terraform-overview)
- [Store Terraform state in Cloud Storage](https://docs.cloud.google.com/docs/terraform/resource-management/store-state)
- [Terraform best practices: reusable modules](https://docs.cloud.google.com/docs/terraform/best-practices/reusable-modules)
- [Infrastructure Manager overview](https://docs.cloud.google.com/infrastructure-manager/docs/overview)
- [Config Connector overview](https://docs.cloud.google.com/config-connector/docs/overview)
- [Application Design Center overview](https://docs.cloud.google.com/application-design-center/docs/overview)
- [Secure Source Manager overview](https://docs.cloud.google.com/secure-source-manager/docs/overview)
- [Cloud Workstations overview](https://docs.cloud.google.com/workstations/docs/overview)
- [Set up Gemini Cloud Assist](https://docs.cloud.google.com/cloud-assist/set-up-gemini)
- [Gemini CLI](https://docs.cloud.google.com/gemini/docs/codeassist/gemini-cli)

[Back to topic](README.md)
