# Practice Exam 6

[Previous](exam-5.md) · [All exams](README.md)

50 questions in the original English. Open "Show answer" under each question to see the correct answer and the explanation.

## Index

| Q | Question |
|---|---|
| [Q1](#q1) | DataPulse runs a batch-processing platform on Compute Engine using a managed instance grou... |
| [Q2](#q2) | MetroCart, an online grocery platform, uses Looker Studio to display sales metrics from a ... |
| [Q3](#q3) | BluePeak Commerce operates several online retail platforms, with each platform hosted in a... |
| [Q4](#q4) | ParcelNest has received a new Google Cloud project with billing already enabled. The engin... |
| [Q5](#q5) | CedarLane Retail wants its software teams to launch a company-approved web application sta... |
| [Q6](#q6) | NovaCart is building an internal developer platform for its product teams. Developers need... |
| [Q7](#q7) | FitMeal Labs has packaged its meal-planning web service as Docker container images. The co... |
| [Q8](#q8) | CineVault Studios stores completed video footage on an on-premises file server. The compan... |
| [Q9](#q9) | Northstar Retail hosts its order-processing frontend on Cloud Run and runs a pricing API o... |
| [Q10](#q10) | BluePeak Media operates workloads across Google Cloud and other cloud providers. The compa... |
| [Q11](#q11) | NeuralVista Labs runs distributed machine learning jobs on Google Kubernetes Engine. Multi... |
| [Q12](#q12) | WaveCast provides an online audio-transcoding service on Compute Engine. Demand changes th... |
| [Q13](#q13) | AsterFit, a mobile fitness platform, is migrating its containerized API services to Google... |
| [Q14](#q14) | TradePulse, an online investment platform, is moving its trading APIs and testing systems ... |
| [Q15](#q15) | BrightTrail, an online travel-planning company, stores destination photographs in a Cloud ... |
| [Q16](#q16) | Northwind Media runs a video-processing service on several existing Compute Engine VM inst... |
| [Q17](#q17) | ParcelPulse runs its shipment-tracking web application as a Cloud Run for Anthos service. ... |
| [Q18](#q18) | BlueHarbor Logistics operates virtual machines across several Google Cloud projects in its... |
| [Q19](#q19) | GlobeSeat operates an international airline reservation platform that runs in several Goog... |
| [Q20](#q20) | AsterWave Health recently introduced an automated workflow for creating Google Cloud proje... |
| [Q21](#q21) | OrionVista Analytics is establishing a sandbox environment for a new research team. The re... |
| [Q22](#q22) | SilverLeaf Publishing stores digital publications and compliance records in Cloud Storage.... |
| [Q23](#q23) | PixelForge Studios operates a large rendering farm with 4,500 Compute Engine workers. The ... |
| [Q24](#q24) | StreamCart runs its order-processing service on one Compute Engine VM. The service writes ... |
| [Q25](#q25) | BrightCart, an online retail company, is deploying a package-processing service on a Compu... |
| [Q26](#q26) | PixelHarbor is preparing a containerized analytics service in a newly created Google Cloud... |
| [Q27](#q27) | BluePeak Analytics is adding 48 software engineers from a recently acquired company for an... |
| [Q28](#q28) | BrightLedger Solutions received a JSON key file for a service account that has permission ... |
| [Q29](#q29) | Finora Health operates several patient-scheduling applications across multiple Google Clou... |
| [Q30](#q30) | NorthStar Tickets operates an event-booking application on Google Cloud. Users report a su... |
| [Q31](#q31) | BlueHarbor Retail runs its order-processing system on a Cloud SQL for MySQL instance. Afte... |
| [Q32](#q32) | Northstar Retail is moving its analytics and commerce workloads to Google Cloud. The compa... |
| [Q33](#q33) | ParcelPilot, a package-tracking website, has containerized its stateless API as a Docker i... |
| [Q34](#q34) | TerraTrack, an agricultural monitoring platform, collects information from farms across se... |
| [Q35](#q35) | ClearLedger Services plans to store customer statements and tax documents in Google Cloud ... |
| [Q36](#q36) | PixelRaid Studios operates a real-time multiplayer battle game on Google Cloud. Players co... |
| [Q37](#q37) | AsterLink operates a customer portal and an order-processing service in separate Google Cl... |
| [Q38](#q38) | ClipStream Labs operates a video-processing platform that converts thousands of uploaded r... |
| [Q39](#q39) | PixelForge Media stores a large collection of images, audio recordings, text files, JSON d... |
| [Q40](#q40) | BlueHarbor Media operates a release pipeline on Amazon EC2 in an AWS account. The pipeline... |
| [Q41](#q41) | Northbridge Advisory needs to provide 32 independent compliance reviewers with temporary, ... |
| [Q42](#q42) | AuroraMart stores customer purchase and product data in a BigQuery dataset within its Goog... |
| [Q43](#q43) | NovaCast, a video-streaming company, notices a sharp increase in network charges between w... |
| [Q44](#q44) | NovaCart Analytics is building an application that will run on Google Cloud and use a dedi... |
| [Q45](#q45) | Evergreen Tickets is moving its reservation database and stateless booking service to a St... |
| [Q46](#q46) | Northwind Analytics stores confidential customer reports in several Cloud Storage buckets.... |
| [Q47](#q47) | BrightCart, an online retail platform, experiences simultaneous failures across multiple r... |
| [Q48](#q48) | NimbusRetail operates a private order-processing API on Cloud Run. A newly created service... |
| [Q49](#q49) | Northbridge Design Group is moving its Windows-based CAD document repository to Google Clo... |
| [Q50](#q50) | BluePeak Analytics has several Google Cloud projects that an engineer originally linked to... |

---

### Q1

> DataPulse runs a batch-processing platform on Compute Engine using a managed instance group. The group reports that it cannot create replacement VMs. You need to correct possible instance template errors, remove disk-name conflicts, and prevent deleted VMs from leaving boot disks that block future instance creation. What should you do?  

- **A.** Create a valid instance template for the managed instance group and delete any persistent disks whose names match the names of the VMs that the group is attempting to create.
- **B.** Create a valid instance template for the managed instance group and configure the template so that VM names and persistent disk names are always different.
- **C.** Verify that the managed instance group’s instance template contains valid properties, delete any existing persistent disks whose names match the required VM names, and set the disks.autoDelete property to true in the instance template.
- **D.** Delete the existing instance template, create a replacement template in which VM names and persistent disk names are different, and set the disks.autoDelete property to true.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because creating a valid instance template and removing conflicting persistent disks can resolve the immediate causes of VM creation failures, but this option does not address why conflicting disks might remain after VMs are deleted. By default, a newly created VM’s boot disk generally has the same name as the VM. If disks are configured not to be automatically deleted, an old boot disk can remain after its VM is removed. When the managed instance group later attempts to create another VM with the same name, Compute Engine cannot create the required boot disk because a disk with that name already exists. Setting disks.autoDelete to true prevents this issue from recurring.

**B is incorrect** because a VM and its automatically created boot disk normally having the same name is expected behavior and is not itself an invalid configuration. The failure occurs when a persistent disk with the required name already exists before the new VM is created. Merely attempting to make the names different does not properly address stale disks, invalid template properties, or disk lifecycle management. The appropriate remediation is to remove conflicting disks after preserving any required data and enable automatic disk deletion where the disks do not need to survive VM deletion.

**C is correct** because it addresses the principal configuration and disk-related causes of managed instance group creation failures. First, the instance template must be checked for invalid properties, such as a nonexistent source image, a misspelled resource name, an invalid network reference, or an unsupported disk attachment configuration. Second, any existing persistent disk whose name conflicts with the boot disk required for a new VM must be deleted, after taking a snapshot when its data must be preserved. Compute Engine normally creates a boot disk with the same name as the VM, so an existing disk with that name prevents creation. Finally, setting disks.autoDelete to true ensures that the disk is deleted with its associated VM, preventing abandoned boot disks from blocking later recreation or replacement operations.

**D is incorrect** because deleting the current instance template is unnecessary and can be problematic when the managed instance group still references it. Instance templates are immutable, so when a configuration change is required, the normal procedure is to create a corrected template and configure the managed instance group to use it; the existing template does not need to be deleted first. Additionally, requiring VM and persistent disk names to be different is not the correct solution because matching names are normal for automatically created boot disks. Although enabling disks.autoDelete is appropriate for disposable disks, the other proposed actions make this option incorrect.

**Reference links**

- [docs.cloud.google.com/compute/docs/troubleshooting/troubleshooting-migs](https://docs.cloud.google.com/compute/docs/troubleshooting/troubleshooting-migs)
- [docs.cloud.google.com/compute/docs/instance-templates/create-instance-templates](https://docs.cloud.google.com/compute/docs/instance-templates/create-instance-templates)
- [docs.cloud.google.com/compute/docs/instance-groups/delete-mig](https://docs.cloud.google.com/compute/docs/instance-groups/delete-mig)

**Related notes:** [Managed Instance Group (MIG)](../03-compute-containers/products/managed-instance-group.md)

</details>

[Back to index](#index)

---

### Q2

> MetroCart, an online grocery platform, uses Looker Studio to display sales metrics from a BigQuery table. New transaction records are appended throughout the day, and a scheduled process rebuilds the summary table every night at 2:30 AM by replacing its contents. One morning, the Looker Studio charts connected to the table begin showing errors. You need to determine whether the overnight data-processing operation failed. What should you do?  

- **A.** Create a Cloud Logging filter that searches for the Looker Studio report name.
- **B.** Use the Snapshot Debugger command-line tool to inspect why the table was not refreshed.
- **C.** Examine Error Reporting in the Google Cloud console for errors generated by the refresh process.
- **D.** Open BigQuery job history in the Google Cloud console, review the overnight job, and inspect its error details.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because creating a Cloud Logging filter for the Looker Studio report is unlikely to reveal why the BigQuery summary table was not rebuilt correctly. Looker Studio is the visualization layer that queries the underlying data source, while the suspected failure occurred in the nightly operation that overwrites the BigQuery table. Searching logs by the report name does not directly identify the BigQuery query, load, copy, or scheduled query job responsible for replacing the table. Cloud Logging can be useful when a custom application, workflow, or service explicitly writes relevant log entries, but the most direct source of diagnostic information for a failed BigQuery operation is BigQuery job history. Job history records execution status, timestamps, job type, SQL text, destination table, processing statistics, and error messages.

**B is incorrect** because Snapshot Debugger is not designed to troubleshoot BigQuery data-refresh or table-overwrite jobs. Debugging snapshots were intended to capture the runtime state of application code, such as variable values and call stacks, without stopping a running application. They do not provide the execution history, SQL errors, permissions failures, quota issues, invalid schema changes, or destination-table details associated with BigQuery jobs. The problem concerns a data warehouse operation rather than a defect that must be inspected inside running application code. In addition, Snapshot Debugger is not an appropriate currently supported tool for diagnosing this type of Google Cloud data-processing failure.

**C is incorrect** because Error Reporting primarily aggregates application error events, such as exceptions and stack traces produced by applications and services. It is useful when an application reports errors through Cloud Logging or the Error Reporting API, but a failed BigQuery query or table-overwrite operation does not necessarily appear there as an application exception. Error Reporting also does not provide the complete operational context of a BigQuery job, including its SQL statement, job ID, destination table, bytes processed, execution stages, and BigQuery-specific error result. Therefore, it is not the most direct or reliable place to investigate the nightly warehouse refresh.

**D is correct** because BigQuery executes operations such as queries, scheduled queries, load operations, copy operations, and table updates as jobs. The BigQuery job history in the Google Cloud console lets you review personal or project-level job activity and locate the job that ran during the nightly refresh period. You can inspect whether the job succeeded or failed, review its SQL statement or job configuration, confirm the destination table, and examine detailed error messages. These details can reveal issues such as invalid SQL, insufficient IAM permissions, schema incompatibilities, missing source data, quota limits, incorrect table locations, or failures while replacing the destination table. Because the Looker Studio report depends on the resulting BigQuery table, verifying the upstream BigQuery job is the most direct way to identify the cause of the broken charts. After correcting the BigQuery failure and rebuilding the table, the Looker Studio report can query the restored data, subject to its configured data-freshness settings.

**Reference links**

- [docs.cloud.google.com/bigquery/docs/managing-jobs](https://docs.cloud.google.com/bigquery/docs/managing-jobs)
- [docs.cloud.google.com/bigquery/docs/bigquery-web-ui](https://docs.cloud.google.com/bigquery/docs/bigquery-web-ui)
- [docs.cloud.google.com/data-studio/manage-data-freshness](https://docs.cloud.google.com/data-studio/manage-data-freshness)

**Related notes:** [BigQuery](../05-storage-databases-data/products/bigquery.md)

</details>

[Back to index](#index)

---

### Q3

> BluePeak Commerce operates several online retail platforms, with each platform hosted in a separate Google Cloud project and connected to a different Cloud Billing account. The finance team needs one dashboard that combines actual spending from every billing account and receives updated cost records automatically throughout the day. What should BluePeak Commerce do?  

- **A.** Enter the configurations of all deployed resources into the Google Cloud Pricing Calculator and use the resulting monthly estimate as the consolidated dashboard.
- **B.** Open the Reports page in the Cloud Billing console and use it to display costs from all Cloud Billing accounts in one report.
- **C.** Download a CSV file from the Cost table page for each Cloud Billing account and connect the files to Looker Studio.
- **D.** Enable Cloud Billing data export to BigQuery for each Cloud Billing account, consolidate the exported data in BigQuery, and visualize it in Looker Studio.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because the Google Cloud Pricing Calculator produces estimates based on manually entered resource configurations, expected usage, machine types, storage quantities, network traffic, and other assumptions. It does not automatically retrieve the actual costs incurred by existing resources, include credits and adjustments from the Cloud Billing accounts, or continuously add newly generated billing records. Maintaining the estimate would require someone to update the calculator whenever a resource, usage pattern, region, discount, or configuration changed. Therefore, the calculator is useful for planning the potential cost of a proposed architecture, but it is not an appropriate source for a unified dashboard of actual costs across multiple Cloud Billing accounts.

**B is incorrect** because the Reports page is primarily scoped to a selected Cloud Billing account. It can provide charts, filters, cost trends, forecasts, and breakdowns for the projects linked to that billing account, but the projects in this scenario are connected to different Cloud Billing accounts. The user would generally need to switch between billing accounts and inspect a separate report for each one rather than obtaining a single consolidated visualization containing all accounts. The Reports page is useful for interactive analysis within an individual billing account, but it does not provide the required centralized, customizable Looker Studio dashboard across multiple billing accounts.

**C is incorrect** because the Cost table is intended mainly for examining and reconciling the detailed charges associated with an invoice or statement. Although its contents can be downloaded as CSV, the download is a manual, point-in-time operation. New cost data would not automatically appear in Looker Studio unless someone repeatedly downloaded updated CSV files, replaced or appended the data, and refreshed the report’s data source. Separate exports would also be required for the different Cloud Billing accounts. This creates an operationally inefficient process and does not satisfy the requirement to include new cost data as soon as possible. The Cost table is appropriate for invoice-level investigation and offline reconciliation, not for building an automatically updated consolidated billing dashboard.

**D is correct** because Cloud Billing data export automatically sends detailed usage and cost data to BigQuery throughout the day. The export should be enabled for each relevant Cloud Billing account because billing export configuration is associated with an individual billing account. The exported tables contain fields such as the billing account ID, project information, services, SKUs, usage, costs, credits, adjustments, currency, and locations. BluePeak Commerce can query or consolidate the exported tables in BigQuery, such as by creating a unified view that combines the records from all billing accounts. Looker Studio can then use the BigQuery query or view as its data source and present all costs in a single visual dashboard. Because newly reported billing data is automatically added to BigQuery, the dashboard can be refreshed without repeatedly downloading or manually maintaining files. This solution provides actual cost information, supports multiple billing accounts, enables customized analysis, and most directly satisfies the requirement for one automatically updated visualization.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery)
- [docs.cloud.google.com/billing/docs/how-to/reports](https://docs.cloud.google.com/billing/docs/how-to/reports)
- [docs.cloud.google.com/billing/docs/how-to/cost-table](https://docs.cloud.google.com/billing/docs/how-to/cost-table)

**Related notes:** [Looker Studio](../05-storage-databases-data/products/looker-studio.md)

</details>

[Back to index](#index)

---

### Q4

> ParcelNest has received a new Google Cloud project with billing already enabled. The engineering team needs to deploy Compute Engine virtual machines, configure VPC firewall rules, and create Cloud Storage buckets for application backups. The team wants to enable only the services required for these tasks, following Google-recommended practices. What should the team do?  

- **A.** Run gcloud services enable cloudresourcemanager.googleapis.com and rely on the Cloud Resource Manager API to activate all other Google Cloud services.
- **B.** Run gcloud services enable compute.googleapis.com and gcloud services enable storage.googleapis.com for the project.
- **C.** Use the Google Cloud console API Library to enable every available Google Cloud API.
- **D.** Start Cloud Shell and run gcloud init --project=parcelnest-production to initialize access to all required services.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because cloudresourcemanager.googleapis.com enables the Cloud Resource Manager API, which is used to create and manage projects, folders, organizations, tags, and related resource-hierarchy operations. Enabling this API does not automatically enable Compute Engine, Cloud Storage, or every other Google Cloud service. Google Cloud APIs are enabled individually through Service Usage, so the Compute Engine API would still need to be enabled before creating VM instances or VPC firewall rules.

**B is correct** because compute.googleapis.com enables the Compute Engine API, which supports the creation and management of Compute Engine instances, VPC networks, and firewall rules. The storage.googleapis.com service enables the Cloud Storage API required for creating buckets and storing objects. Enabling only the APIs needed for the planned workload follows the principle of least privilege and reduces unnecessary service exposure, administrative complexity, and accidental use of unrelated services. Both commands should be executed against the intended Google Cloud project, either by setting that project in the active gcloud CLI configuration or by including the --project flag.

**C is incorrect** because enabling every Google Cloud API is unnecessary and does not follow recommended least-privilege practices. A project should generally have only the services required by its workloads enabled. Activating all APIs can expose additional service capabilities, make governance and auditing more complicated, and allow authorized identities to interact with services that the project does not need. The API Library can be used to enable APIs, but only the required Compute Engine and Cloud Storage APIs should be selected.

**D is incorrect** because gcloud init configures the gcloud CLI by setting properties such as the authenticated account, active project, and default region or zone. It does not automatically enable the Compute Engine or Cloud Storage APIs. Additionally, Cloud Shell already includes the gcloud CLI and is usually authenticated with the signed-in Google Cloud account, while the currently selected console project is commonly available to the session. Even after running gcloud init, the required service APIs must still be enabled explicitly.

**Reference links**

- [docs.cloud.google.com/service-usage/docs/enable-disable](https://docs.cloud.google.com/service-usage/docs/enable-disable)
- [docs.cloud.google.com/sdk/gcloud/reference/services/enable](https://docs.cloud.google.com/sdk/gcloud/reference/services/enable)
- [docs.cloud.google.com/storage/docs/json_api](https://docs.cloud.google.com/storage/docs/json_api)

</details>

[Back to index](#index)

---

### Q5

> CedarLane Retail wants its software teams to launch a company-approved web application stack that includes Cloud Run, Cloud SQL, and Cloud Load Balancing. The cloud platform team has already created and reviewed reusable Terraform modules for these resources. The team wants to manage the architecture centrally while allowing developers to configure and deploy the stack without independently designing its infrastructure. What should CedarLane Retail use?  

- **A.** Application Design Center with imported approved components and reusable application templates
- **B.** Gemini Cloud Assist investigations for each application deployment
- **C.** Cloud Hub application-health and troubleshooting views
- **D.** Cloud Asset Inventory exports containing the application resources

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Application Design Center is designed to help platform teams create, govern, share, and maintain standardized application architectures that developers can reuse. The platform team can import its reviewed Terraform modules into Application Design Center, where each imported module becomes a reusable component template in a private catalog. It can then combine approved Cloud Run, Cloud SQL, and Cloud Load Balancing components into a standard application template, define supported connections and configuration parameters, and make that template available to development teams. Developers can create an application from the template, provide permitted values such as a project ID, region, database settings, and container image, and deploy the generated Terraform configuration without designing every underlying resource. This approach preserves the platform team’s approved architecture and Terraform implementation while offering developers a simpler self-service deployment experience. The platform team can centrally maintain and version the components and templates, publish updated designs, and control access through IAM and Application Design Center catalogs.

**B is incorrect** because Gemini Cloud Assist investigations are intended for troubleshooting and root-cause analysis of problems in applications and cloud infrastructure. They can analyze telemetry and resource information to help diagnose deployment failures, performance problems, configuration issues, and operational incidents. They do not provide a catalog of reviewed Terraform modules or package Cloud Run, Cloud SQL, and load-balancing resources into a reusable, centrally managed application architecture. Gemini Cloud Assist investigations could help developers investigate a failure after the application is deployed, but they are not the service for defining and distributing the standardized deployment pattern.

**C is incorrect** because Cloud Hub provides centralized operational views and insights for Google Cloud projects and applications. It can display application health, monitoring alerts, incidents, performance metrics, deployment failures, security findings, costs, quotas, and other operational information. Cloud Hub is useful after applications and resources exist, especially for monitoring and troubleshooting them in an application-centric view. However, it is not the primary service for importing reviewed Terraform modules, assembling them into approved reusable templates, and enabling developers to deploy standardized application stacks. Application Design Center creates and manages the architecture, while Cloud Hub can complement it by showing operational information about deployed applications.

**D is incorrect** because Cloud Asset Inventory is a metadata inventory and analysis service. It can search, monitor, and export information about Google Cloud resources, IAM policies, organization policies, and resource relationships. Its exports can help with governance, security analysis, compliance reporting, and historical asset analysis, but they do not function as reusable deployment blueprints. An inventory export describes resources that exist or existed at a particular time; it does not package approved Terraform modules into a self-service application template or guide developers through deploying Cloud Run, Cloud SQL, and Cloud Load Balancing as a standardized architecture.

**Reference links**

- [docs.cloud.google.com/application-design-center/docs/overview](https://docs.cloud.google.com/application-design-center/docs/overview)
- [docs.cloud.google.com/application-design-center/docs/import-components](https://docs.cloud.google.com/application-design-center/docs/import-components)
- [docs.cloud.google.com/application-design-center/docs/design-application-templates](https://docs.cloud.google.com/application-design-center/docs/design-application-templates)

**Related notes:** [Application Design Center](../08-iac-platform-ai/products/application-design-center.md)

</details>

[Back to index](#index)

---

### Q6

Choose 2.

> NovaCart is building an internal developer platform for its product teams. Developers need a self-service method to deploy a company-approved architecture containing Cloud Run, Pub/Sub, and Cloud SQL. GitHub Actions performs each deployment, and the security team does not permit long-lived service account keys. Which two actions should NovaCart take? (Choose two.)  

- **A.** Create the approved architecture as an Application Design Center template and publish it through a catalog.
- **B.** Grant the Owner role to every developer so they can modify resources outside the approved template.
- **C.** Configure Workload Identity Federation to trust GitHub’s OIDC identity and permit it to impersonate a least-privileged deployment service account.
- **D.** Create a deployment service account key and save a copy in every GitHub repository.
- **E.** Require developers to deploy resources manually in the Google Cloud console after receiving approval by email.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A, C

**Explanation**

**A is correct** because Application Design Center enables platform teams to define standardized, reusable application architectures and make them available to development teams as approved templates. The platform team can model the required Cloud Run, Pub/Sub, and Cloud SQL resources, configure their connections and approved settings, and publish the template through a catalog. Developers can then select the template, provide permitted configuration values, and deploy the architecture through a governed self-service workflow. Application Design Center generates Terraform code from the design, which helps make deployments consistent and repeatable. Developers can customize exposed component properties, but a standard template prevents them from arbitrarily adding or removing components. This approach provides self-service without abandoning the organization’s architecture, security, and compliance standards.

**B is incorrect** because the Owner role provides extremely broad permissions across a Google Cloud project, including the ability to create, modify, and delete many resources and change IAM policies. Granting this role to every developer violates the principle of least privilege and would let developers bypass the controls embedded in the approved Application Design Center template. Template limitations should be corrected by the platform team by updating the template, its components, or its permitted inputs. They should not be addressed by granting developers unrestricted administrative access. Developers only need the narrowly scoped permissions required to discover, customize, and request deployments from approved templates.

**C is correct** because Workload Identity Federation allows GitHub Actions to authenticate to Google Cloud by exchanging GitHub-issued OIDC tokens for short-lived Google Cloud credentials. The organization can configure a workload identity pool and provider that trusts GitHub’s OIDC issuer, maps relevant claims, and restricts access according to attributes such as the GitHub organization, repository, branch, or deployment environment. The trusted GitHub identity can then receive the Workload Identity User role on a dedicated deployment service account and impersonate that account during an authorized workflow. The deployment service account should have only the permissions required to deploy and manage the approved Cloud Run, Pub/Sub, Cloud SQL, and supporting resources. This design avoids long-lived keys, limits the deployment pipeline’s privileges, improves attribution, and satisfies the security requirement.

**D is incorrect** because storing a service account key in every repository creates long-lived credentials that can be copied, leaked, or used outside the intended GitHub Actions workflow. Even when the key is stored as an encrypted repository secret, anyone or any compromised workflow with access to that secret might authenticate as the service account until the key is revoked. Replicating the same key across repositories also increases credential sprawl, complicates rotation, reduces the ability to identify which pipeline used the credential, and expands the potential impact of a compromise. Most importantly, this option directly violates the stated prohibition against service account keys. Workload Identity Federation provides short-lived credentials without requiring a stored private key.

**E is incorrect** because manual console deployments and email approvals do not satisfy the self-service or automated delivery requirements. Manual deployment is slower, more error-prone, and harder to reproduce consistently across environments. It can also cause configuration drift because developers might select different settings during separate console deployments. Email approval records are disconnected from the deployment process and do not provide the same enforceable controls, identity restrictions, or repeatability as approved templates and an authenticated CI/CD pipeline. Application Design Center templates combined with GitHub Actions and Workload Identity Federation provide controlled automation while preserving governance and auditability.

**Reference links**

- [docs.cloud.google.com/application-design-center/docs/overview](https://docs.cloud.google.com/application-design-center/docs/overview)
- [docs.cloud.google.com/application-design-center/docs/design-application-templates](https://docs.cloud.google.com/application-design-center/docs/design-application-templates)
- [docs.cloud.google.com/iam/docs/workload-identity-federation-with-deployment-pipelines](https://docs.cloud.google.com/iam/docs/workload-identity-federation-with-deployment-pipelines)

**Related notes:** [Application Design Center](../08-iac-platform-ai/products/application-design-center.md) · [Workload Identity Federation and Workforce Identity Federation](../02-identity-security/products/workload-identity-federation-and-workforce-identity-federati.md)

</details>

[Back to index](#index)

---

### Q7

> FitMeal Labs has packaged its meal-planning web service as Docker container images. The company expects traffic to increase rapidly after a public launch. Its developers want Google Cloud to manage the underlying servers, operating systems, and capacity while automatically adjusting the number of application instances according to demand. What should the company do?  

- **A.** Create an instance template that runs the container image, and deploy an autoscaled Managed Instance Group.
- **B.** Store the container images in Artifact Registry, and deploy them to a Google Kubernetes Engine cluster in Standard mode.
- **C.** Store the container images as objects in a Cloud Storage bucket, and deploy them to a Google Kubernetes Engine cluster in Standard mode.
- **D.** Store the container images in Artifact Registry, and deploy them as a Cloud Run service.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because an autoscaled Managed Instance Group can increase or decrease the number of Compute Engine virtual machines according to signals such as CPU utilization, load-balancing capacity, schedules, or Cloud Monitoring metrics. Therefore, this option can provide automatic scaling. However, it does not satisfy the requirement to avoid managing infrastructure. The team would still be responsible for creating and maintaining the instance template, selecting machine types, configuring startup behavior, managing operating-system updates, defining autoscaling policies, and handling other VM-related operational tasks. A Managed Instance Group reduces the effort required to manage multiple identical VMs, but it remains an infrastructure-oriented Compute Engine solution rather than a fully managed serverless container platform.

**B is incorrect** because Artifact Registry is the appropriate Google Cloud service for securely storing and managing Docker and other OCI-compatible container images. Google Kubernetes Engine can also run containerized applications and provide workload and cluster autoscaling. However, GKE Standard mode gives the customer control over the cluster’s worker-node infrastructure. The team must make decisions about node pools, machine types, node capacity, upgrades, maintenance, networking, security, and cluster scaling. Google manages the Kubernetes control plane, but the customer retains substantial responsibility for the nodes and cluster configuration. This conflicts with the stated goal of avoiding infrastructure management. GKE Standard is more appropriate when a team requires detailed control over Kubernetes and its underlying compute resources.

**C is incorrect** because Cloud Storage is designed to store objects such as files, backups, media, archives, and datasets. It is not a Docker or OCI container registry and does not provide the container-image repository features required for normal GKE image deployment, such as image manifests, layers, tags, digests, repository permissions, and container-runtime integration. Artifact Registry should be used to store Docker images. In addition, deploying the application on GKE Standard mode would still require the team to manage worker nodes and other Kubernetes infrastructure, so this option fails both the image-storage and infrastructure-management requirements.

**D is correct** because Artifact Registry is Google Cloud’s recommended service for storing and managing Docker container images, and Cloud Run is a fully managed serverless platform for running containerized applications. Cloud Run manages the underlying compute infrastructure, including server provisioning, operating-system maintenance, capacity allocation, load balancing, and instance lifecycle. A Cloud Run service automatically creates additional container instances as incoming demand increases and can reduce the number of instances when demand falls. Subject to the service’s scaling configuration, it can also scale to zero when it receives no requests. The development team can therefore concentrate on building and updating the container image instead of administering virtual machines or Kubernetes clusters. This combination directly satisfies both requirements: minimal infrastructure management and automatic scaling as the application becomes more popular.

**Reference links**

- [docs.cloud.google.com/run/docs/deploying](https://docs.cloud.google.com/run/docs/deploying)
- [docs.cloud.google.com/run/docs/about-instance-autoscaling](https://docs.cloud.google.com/run/docs/about-instance-autoscaling)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/choose-cluster-mode](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/choose-cluster-mode)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md) · [Artifact Registry](../03-compute-containers/products/artifact-registry.md)

</details>

[Back to index](#index)

---

### Q8

> CineVault Studios stores completed video footage on an on-premises file server. The company wants to archive the footage in Cloud Storage and automatically copy newly created files at regular intervals. You need to implement a simple solution. What should you do?  

- **A.** Create a Pub/Sub topic, configure a Cloud Storage trigger for the topic, and develop an application that publishes the video files to Pub/Sub.
- **B.** Deploy the Dataflow Datastore to Cloud Storage batch template and schedule the pipeline to run every 30 minutes.
- **C.** Create a script that uses the Google Cloud CLI gcloud storage rsync command to synchronize the on-premises directory with a Cloud Storage bucket, and schedule the script as a cron job.
- **D.** Periodically open the Google Cloud console and manually upload the latest video files to the Cloud Storage bucket.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Pub/Sub is a messaging service intended to transport messages and event notifications between applications, not to synchronize directories or transfer large binary files into Cloud Storage. A Cloud Storage notification can publish information about object changes that have already occurred in a bucket, but it does not monitor an on-premises directory for new files. Publishing complete video files as Pub/Sub messages would also be inappropriate because Pub/Sub messages have size limits and are not intended to function as archival object storage. This design would require unnecessary custom application development without providing a native directory-synchronization mechanism.

**B is incorrect** because the Datastore to Cloud Storage Dataflow template exports entities from Firestore in Datastore mode to Cloud Storage. It does not read files from an on-premises file system, detect newly created media files, or synchronize a local directory with a Cloud Storage bucket. Scheduling this template would repeatedly export database entities rather than upload the required video footage. Dataflow is useful for large-scale data processing pipelines, but it is unnecessary and technically unsuitable for this file-synchronization requirement.

**C is correct** because gcloud storage rsync compares the source directory with the destination and copies new or changed files to the Cloud Storage bucket. Running the command from an on-premises machine that has access to the footage directory enables the company to transfer files directly to Cloud Storage. Scheduling the script with cron automates the process so that newly created footage is uploaded at the selected interval without manual intervention. The script should authenticate with a dedicated service account that has only the necessary Cloud Storage permissions. Although older implementations commonly used gsutil rsync, Google Cloud currently recommends the gcloud storage commands in the Google Cloud CLI for Cloud Storage operations. For very large enterprise transfers or advanced managed scheduling requirements, Storage Transfer Service could also be considered, but among the listed options, a scheduled synchronization script is the appropriate solution.

**D is incorrect** because manually uploading files through the Google Cloud console does not satisfy the requirement for an automated process. An administrator would need to identify and upload each new file, which introduces operational effort, delays, and the possibility of missing or duplicating files. Manual uploads can be appropriate for occasional one-time transfers, but they are not a reliable solution for continuously archiving newly generated files.

**Reference links**

- [docs.cloud.google.com/sdk/gcloud/reference/storage/rsync](https://docs.cloud.google.com/sdk/gcloud/reference/storage/rsync)
- [docs.cloud.google.com/storage/docs/gsutil-transition-to-gcloud](https://docs.cloud.google.com/storage/docs/gsutil-transition-to-gcloud)
- [docs.cloud.google.com/storage-transfer/docs/overview](https://docs.cloud.google.com/storage-transfer/docs/overview)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q9

> Northstar Retail hosts its order-processing frontend on Cloud Run and runs a pricing API on Google Kubernetes Engine (GKE). The frontend must access the pricing API by using a private network path, and the API must not be exposed to the public internet. Which architecture should Northstar Retail implement?  

- **A.** -Create an external Ingress for the GKE pricing API.  
  -Configure Cloud Armor to allow only the public IP address detected by each Cloud Run instance, and update the Cloud Armor security policy whenever a new instance starts.
- **B.** Create a VPC ingress firewall rule that permits traffic from 0.0.0.0/0 to the GKE workloads on ports 8080 and 8443.
- **C.** Create a VPC egress firewall rule that permits traffic to 0.0.0.0/0 on ports 8080 and 8443.
- **D.** -Deploy an internal Application Load Balancer for the GKE pricing API.  
  -Create a private Cloud DNS record that resolves the API’s FQDN to the internal load balancer address.  
  -Configure Direct VPC egress for the Cloud Run service so that it can reach the API through the VPC network.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because an external Ingress makes the GKE API reachable through a public load balancer, which conflicts with the requirement to keep communication private. Cloud Armor can protect an external Application Load Balancer by evaluating incoming requests, but it does not convert a public endpoint into a private endpoint. The design is also unreliable because Cloud Run instances do not each provide a stable public egress IP address that an application should discover and dynamically add to a Cloud Armor policy. Cloud Run instances can be created and terminated automatically, so continuously changing security policies during application startup would introduce race conditions, operational complexity, and possible service interruptions. Static internet egress could be implemented with VPC networking and Cloud NAT, but that would still send requests to a publicly exposed API and would be unnecessary when private VPC connectivity is available.

**B is incorrect** because an ingress firewall rule allowing 0.0.0.0/0 permits traffic from every IPv4 address that has a network path to the target. This is excessively broad and violates the principle of least privilege. More importantly, a firewall rule only permits or denies traffic; it does not create the private network path required for Cloud Run to reach resources in a VPC network. The Cloud Run service would still need Direct VPC egress or a Serverless VPC Access connector. This option also does not provide a private load-balanced endpoint or private DNS name for the GKE API.

**C is incorrect** because an egress firewall rule permitting traffic to 0.0.0.0/0 merely allows outbound connections to any IPv4 destination. It does not attach the Cloud Run service to the VPC network, expose the GKE API through an internal endpoint, or provide DNS resolution for the API. VPC firewall rules control traffic after an appropriate network path exists. Cloud Run must first be configured with Direct VPC egress or, where appropriate, a Serverless VPC Access connector. Allowing all outbound destinations is also broader than necessary and does not follow least-privilege security practices.

**D is correct** because an internal Application Load Balancer gives the GKE API a private frontend that is reachable from authorized clients in the VPC network without exposing the API to the internet. A private Cloud DNS zone can map an internal FQDN, such as pricing.northstar.internal, to the load balancer’s internal IP address, allowing the Cloud Run application to use a stable service name rather than a hard-coded address. Direct VPC egress enables the Cloud Run service to send traffic directly into the VPC network and is currently Google’s recommended general-purpose method for Cloud Run VPC connectivity because it avoids managing a Serverless VPC Access connector, provides lower latency and higher throughput, and supports more granular network controls. Appropriate firewall rules should allow only the required traffic between the Cloud Run resources and the internal load balancer. A Serverless VPC Access connector remains supported, but Direct VPC egress is the preferred choice for the reframed architecture.

**Reference links**

- [cloud.google.com/run/docs/configuring/connecting-vpc](https://cloud.google.com/run/docs/configuring/connecting-vpc)
- [cloud.google.com/kubernetes-engine/docs/how-to/internal-load-balance-ingress](https://cloud.google.com/kubernetes-engine/docs/how-to/internal-load-balance-ingress)
- [cloud.google.com/dns/docs/zones](https://cloud.google.com/dns/docs/zones)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md)

</details>

[Back to index](#index)

---

### Q10

> BluePeak Media operates workloads across Google Cloud and other cloud providers. The company uses an external SaaS observability platform as the central location for application logs. BluePeak Media needs to continuously forward log entries from Cloud Logging to the SaaS platform with the lowest practical delivery delay. What should the company do?  

- **A.** -Create a Cloud Logging sink that routes log entries to a BigQuery dataset.  
  -Configure the SaaS platform to periodically query the dataset for new log entries.
- **B.** -Create a Cloud Logging sink that routes log entries to a Pub/Sub topic.  
  -Create a subscription and configure the SaaS platform to consume messages from the subscription.
- **C.** -Create a Cloud Logging sink that routes log entries to a Cloud Storage bucket.  
  -Configure the SaaS platform to scan the bucket for newly created log files.
- **D.** -Create a Cloud Scheduler job that periodically invokes a Cloud Run function.  
  -Configure the function to query Cloud Logging and send the returned entries to the SaaS platform.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because routing logs to BigQuery is primarily appropriate when the company needs long-term analytical storage, SQL-based investigation, reporting, or correlation of log data with other structured datasets. Cloud Logging writes log entries to BigQuery in small batches, and the SaaS platform would also need to run recurring queries to identify records that have arrived since its previous query. The total delay would therefore depend on both the delivery of the logs to BigQuery and the SaaS platform’s polling interval. The integration would also require checkpointing logic to prevent duplicate or missing records, query-cost management, schema handling, and permissions for the SaaS platform to access BigQuery. Although BigQuery can receive and analyze exported logs, it is not the Google-recommended destination for streaming logs to an external application with the least possible delay.

**B is correct** because Pub/Sub is designed for asynchronous, near-real-time message delivery between producers and consumers. A Cloud Logging sink can route matching log entries directly to a Pub/Sub topic as they become available. The SaaS platform can then consume the entries through a pull subscription, StreamingPull, or a supported push or vendor-managed integration. This event-driven architecture avoids periodically querying a storage system and therefore minimizes delivery delay. Pub/Sub also provides message retention, acknowledgment handling, retry delivery, flow control, and scalable subscriber processing. The company must grant the Cloud Logging sink’s writer identity permission to publish to the topic and grant the SaaS integration only the permissions required to consume messages from its subscription. Google Cloud specifically recommends Pub/Sub when Cloud Logging data must be streamed to third-party platforms such as external observability, security analytics, or log-management services.

**C is incorrect** because Cloud Storage is intended for durable object storage, archival, compliance retention, and batch-oriented log processing rather than low-latency streaming. Log entries routed from Cloud Logging to Cloud Storage are grouped into files and written in hourly batches. The first exported entries can take approximately two to three hours to appear in the destination bucket. The SaaS platform would then need to discover new objects, download them, decompress or parse their contents, track which objects have already been processed, and handle delayed or late-arriving files. This architecture is useful for inexpensive long-term retention or offline processing, but its batching behavior makes it unsuitable when the primary requirement is to export logs with the least amount of delay.

**D is incorrect** because a scheduled function creates a polling-based integration instead of using Cloud Logging’s native routing capabilities. The delivery delay would be at least as long as the Cloud Scheduler execution interval, plus the time required for the Cloud Run function to start, query the Logging API, process the results, and transmit them to the SaaS platform. The company would also need to implement pagination, timestamps or cursor management, retries, deduplication, rate-limit handling, failure recovery, secure credential storage, and logic for overlapping executions. A query failure or incorrect checkpoint could cause logs to be duplicated or skipped. This custom solution introduces more operational overhead and is less scalable and reliable than creating a Cloud Logging sink with Pub/Sub, which provides a managed, event-driven route for near-real-time third-party integration.

**Reference links**

- [docs.cloud.google.com/logging/docs/export/pubsub](https://docs.cloud.google.com/logging/docs/export/pubsub)
- [docs.cloud.google.com/logging/docs/export/third_party](https://docs.cloud.google.com/logging/docs/export/third_party)
- [docs.cloud.google.com/pubsub/docs/subscription-overview](https://docs.cloud.google.com/pubsub/docs/subscription-overview)

**Related notes:** [Pub/Sub](../04-events-integration/products/pub-sub.md) · [Cloud Logging](../07-operations-cost/products/cloud-logging.md)

</details>

[Back to index](#index)

---

### Q11

> NeuralVista Labs runs distributed machine learning jobs on Google Kubernetes Engine. Multiple training Pods need persistent, shared, high-throughput file storage for datasets and checkpoints. The platform team wants Kubernetes to provision and remove the storage automatically when developers create and delete standard PersistentVolumeClaims, without maintaining custom storage lifecycle or mount scripts. Which solution should NeuralVista Labs use?  

- **A.** Configure the Managed Lustre CSI driver and create an appropriate StorageClass
- **B.** Store the machine learning dataset in a Kubernetes ConfigMap
- **C.** Configure Cloud NAT separately for every training Pod
- **D.** Store a Persistent Disk device path in a Kubernetes Secret

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the Managed Lustre CSI driver integrates Google Cloud Managed Lustre with GKE through standard Kubernetes storage resources. The platform team can define a StorageClass that specifies the Managed Lustre CSI provisioner and the required file-system configuration. Developers can then submit PersistentVolumeClaims that reference this StorageClass. Kubernetes and the CSI driver dynamically create the corresponding PersistentVolume and Managed Lustre instance, make the volume available to the workload, mount it on eligible GKE nodes, and manage its lifecycle according to the configured reclaim policy. Managed Lustre provides persistent, scalable, high-throughput parallel file storage suitable for distributed AI, machine learning, and high-performance computing workloads. It also supports shared access modes such as ReadWriteMany, allowing multiple training Pods to access the same file system concurrently. This approach satisfies both the performance requirement and the operational requirement to avoid custom provisioning, mounting, and deletion scripts.

**B is incorrect** because a ConfigMap is a Kubernetes API object intended to store non-confidential configuration values, such as application settings, command-line arguments, environment variables, and small configuration files. It is not a persistent file-storage system and cannot provide a high-throughput shared file-system interface for large training datasets or checkpoints. ConfigMap data is stored through the Kubernetes control plane, so placing large datasets in ConfigMaps would create control-plane overhead and encounter Kubernetes object-size constraints. A ConfigMap also provides none of the capacity, throughput, persistence, scalability, or parallel file-access characteristics required by distributed AI training.

**C is incorrect** because Cloud NAT is a networking service that allows resources without external IP addresses to establish outbound connections to the internet or other external destinations. It does not create storage, provide PersistentVolumes, implement a shared file system, or manage file-system lifecycle operations. Cloud NAT is generally configured for a VPC network and region rather than being attached separately to each Pod. Although training Pods might use Cloud NAT to download external packages or reach public APIs, it cannot satisfy the requirement for dynamically provisioned, persistent, shared, high-throughput storage.

**D is incorrect** because a Kubernetes Secret stores sensitive values such as passwords, tokens, certificates, and credentials. Placing a Persistent Disk device path in a Secret does not provision a disk, create a PersistentVolume, attach the disk to GKE nodes, mount a file system, or delete the underlying storage. Compute Engine Persistent Disk integration should be performed through a CSI driver, StorageClass, PersistentVolume, and PersistentVolumeClaim rather than by exposing a device path to Pods. In addition, a standard Persistent Disk is generally not the best choice for a distributed workload that requires high-throughput shared file access across many training Pods. The Secret would merely contain a string and would not provide any storage lifecycle automation.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/managed-lustre](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/managed-lustre)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/persistent-volumes/lustre-csi-driver-new-volume](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/persistent-volumes/lustre-csi-driver-new-volume)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/storage-overview](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/storage-overview)

**Related notes:** [Google Cloud Managed Lustre](../05-storage-databases-data/products/google-cloud-managed-lustre.md)

</details>

[Back to index](#index)

---

### Q12

> WaveCast provides an online audio-transcoding service on Compute Engine. Demand changes throughout the day, and customers must be able to process audio files without service interruptions or insufficient CPU capacity. You need a highly available solution that automatically adjusts capacity by following Google-recommended operational practices. What should you do?  

- **A.** Run the application on several standalone Compute Engine instances and manually add instances when Cloud Monitoring reports high CPU utilization.
- **B.** Run the application on several standalone Compute Engine instances and replace them with compute-optimized instances when Cloud Monitoring reports high CPU utilization.
- **C.** Run the application in a managed instance group and manually increase the group size whenever Cloud Monitoring reports high CPU utilization.
- **D.** Run the application in a managed instance group and configure autoscaling based on CPU utilization.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because deploying multiple standalone Compute Engine instances can provide some redundancy, but the instances must be provisioned, configured, updated, monitored, and replaced individually. Manually checking Cloud Monitoring and adding instances after CPU utilization crosses a threshold is a reactive process that can leave users with insufficient processing capacity while administrators create new VMs. It also introduces unnecessary operational work and increases the risk of configuration differences between instances. A managed instance group provides centralized lifecycle management and can automatically create identically configured instances from an instance template.

**B is incorrect** because replacing existing VMs with compute-optimized or high-CPU VMs is vertical scaling rather than automatic horizontal scaling. Replacing instances can cause disruption, requires administrative intervention, and does not dynamically adapt to continuous changes in demand. Larger machines can also reach their limits as the workload continues to grow. This option does not provide the automated operations requested, and managing the VMs as standalone instances makes consistent deployment, repair, and scaling more complex.

**C is incorrect** because a managed instance group is appropriate for running identical Compute Engine instances and can improve availability through features such as autohealing and regional distribution. However, manually increasing the group size whenever high CPU utilization appears does not automate scaling. Administrators might respond too slowly to sudden demand, and they would also need to reduce the group size manually when demand declines. This approach does not fully use the managed instance group’s built-in autoscaling capabilities.

**D is correct** because a managed instance group can automatically add or remove Compute Engine instances according to an autoscaling policy. When autoscaling is based on average CPU utilization, the autoscaler increases the number of instances when CPU demand rises and decreases the number when demand falls. This allows the transcoding service to maintain sufficient processing capacity without requiring administrators to monitor metrics and resize the group manually. A managed instance group also supports automated operations such as creating consistent VMs from an instance template, autohealing unhealthy instances, performing controlled updates, and distributing instances across multiple zones when configured as a regional managed instance group. These capabilities make the solution scalable, highly available, and aligned with Google-recommended practices.

**Reference links**

- [docs.cloud.google.com/compute/docs/autoscaler](https://docs.cloud.google.com/compute/docs/autoscaler)
- [docs.cloud.google.com/compute/docs/autoscaler/scaling-cpu](https://docs.cloud.google.com/compute/docs/autoscaler/scaling-cpu)
- [docs.cloud.google.com/compute/docs/instance-groups](https://docs.cloud.google.com/compute/docs/instance-groups)

**Related notes:** [Managed Instance Group (MIG)](../03-compute-containers/products/managed-instance-group.md)

</details>

[Back to index](#index)

---

### Q13

> AsterFit, a mobile fitness platform, is migrating its containerized API services to Google Kubernetes Engine (GKE). The production environment must remain available during zonal failures and platform maintenance. The team wants Google Cloud to manage node provisioning, scaling, security patching, and upgrades. It also wants billing to be based on the compute resources requested by its workloads instead of paying for provisioned virtual machines that might remain underutilized. The company wants to follow Google-recommended practices while minimizing infrastructure administration and operational costs. What should the team do?  

- **A.** Create a Standard regional GKE cluster.
- **B.** Create a Standard single-zone GKE cluster.
- **C.** Create a Standard zonal GKE cluster with node pools distributed across multiple zones.
- **D.** Create an Autopilot GKE cluster.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a Standard regional GKE cluster provides strong availability but does not satisfy all the operational and billing requirements. Its control plane is replicated across multiple zones, which keeps the Kubernetes API available during a single-zone failure and generally reduces control-plane disruption during upgrades. However, in Standard mode, the organization remains responsible for selecting machine types, configuring and sizing node pools, monitoring node capacity, managing scaling behavior, and making node-management decisions. Although GKE can automatically upgrade Standard nodes, the team still owns more of the node lifecycle and must plan upgrade strategies, maintenance policies, capacity, and workload disruption controls. Standard clusters are also generally billed for the underlying Compute Engine virtual machines provisioned as nodes, including unused capacity. Therefore, this option offers high availability but does not meet the requirements to avoid node management and pay according to workload-level compute requests.

**B is incorrect** because a Standard single-zone GKE cluster has lower availability and still requires node administration. A zonal cluster normally has a single control-plane instance in one zone, so a zonal outage can make the control plane unavailable. Control-plane maintenance or upgrades can also temporarily prevent cluster-management operations, even when existing workloads continue running. If the worker nodes are located in the same single zone, an outage in that zone can make the applications unavailable as well. In addition, Standard mode requires the team to manage node pools, capacity, scaling configuration, machine types, and upgrade settings. The company would pay for the provisioned Compute Engine nodes rather than only the workload-level resources requested by its Pods. This option therefore fails the high-availability, minimal-administration, and workload-based billing requirements.

**C is incorrect** because distributing the nodes of a Standard zonal cluster across multiple zones improves workload availability but does not make the control plane regional. Application replicas running in unaffected zones can continue serving traffic during a failure in one node zone, but the zonal control plane remains a potential availability limitation. During control-plane upgrades or an outage affecting the control-plane zone, the Kubernetes API can become temporarily unavailable, preventing deployments and cluster configuration changes. This configuration also remains a Standard cluster, so the team must manage node pools, node capacity, machine types, autoscaling settings, upgrade behavior, and the available capacity in each zone. Charges are based primarily on the provisioned Compute Engine nodes, and spreading node pools across zones can increase the amount of capacity and quota consumed. It consequently does not satisfy the requirement for fully managed nodes or workload-oriented compute billing.

**D is correct** because an Autopilot GKE cluster most directly satisfies all the stated requirements. Autopilot clusters are regional, so the control plane is replicated across multiple zones for high availability. Google Cloud manages the worker-node infrastructure, including node provisioning, placement, scaling, operating-system configuration, security hardening, patching, repair, and upgrades. This allows security and stability updates to be applied without requiring the team to maintain individual nodes or manually operate node pools. Autopilot also uses managed upgrade processes intended to minimize workload disruption, although applications should still use multiple replicas, readiness probes, appropriate PodDisruptionBudgets, and topology-spread settings to achieve application-level availability. For general-purpose Autopilot workloads, billing is based primarily on the CPU, memory, and ephemeral-storage resources requested by the Pods rather than on entire pre-provisioned virtual machines. Specialized hardware and certain ComputeClasses can use different billing models, but Autopilot remains the option that best matches the requirement to avoid paying for idle node capacity. By combining a regional architecture, automated node management, managed security updates, automatic infrastructure scaling, and workload-oriented pricing, Autopilot follows Google-recommended operational practices and minimizes ongoing administrative effort.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-upgrades-autopilot](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-upgrades-autopilot)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/configuration-overview](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/configuration-overview)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q14

> TradePulse, an online investment platform, is moving its trading APIs and testing systems to Google Cloud. Its production services communicate with customers and financial data providers in multiple geographic locations and require the lowest practical network latency and highest network performance. Its development systems are used only for internal testing, and reducing their networking costs is more important than achieving premium network performance. What should the company do?  

- **A.** Use Standard Tier for the production environment and Premium Tier for the development environment.
- **B.** Use Standard Tier for the development environment and Premium Tier for the production environment.
- **C.** Use Premium Tier for both the production and development environments.
- **D.** Use Standard Tier for both the production and development environments.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because the two Network Service Tiers are assigned to the wrong environments. Standard Tier routes applicable external traffic primarily through regular internet service provider networks. Traffic generally enters or leaves Google’s network in the Google Cloud region where the workload is located, which can result in a longer public-internet path, greater latency variability, and lower overall network performance. Although Standard Tier is more economical, it is not the best choice for latency-sensitive production trading services. Premium Tier uses Google’s high-performance global backbone and is therefore the more appropriate choice for production. Assigning Premium Tier to development would also increase networking costs for an environment that does not require premium performance.

**B is correct** because it aligns each environment with its principal requirement. Premium Tier should be used for the production environment because it carries applicable external traffic across Google’s low-latency, highly reliable global network. Incoming traffic can enter Google’s network at an edge point close to the user and remain on Google’s backbone for most of its journey to the workload. This reduces reliance on the public internet and generally provides better latency, reliability, and network performance for geographically distributed production users and connected financial systems. Standard Tier should be used for the development environment because it uses regular ISP networks for a larger portion of the traffic path and is designed to optimize networking costs. The development systems can therefore use the lower-cost tier because they do not require the same performance characteristics as production. Technically, Network Service Tiers are not inherent properties of an entire VPC network. They can be selected through supported regional external IP addresses and associated resources, or configured as a project-level default. Separate VPC networks can still be used to isolate production and development, while the appropriate tier is configured for the external networking resources in each environment.

**C is incorrect** because Premium Tier would provide the required network performance for production but would unnecessarily apply the same premium networking characteristics to development. Premium Tier routes applicable external traffic through Google’s global backbone and is suitable for latency-sensitive, geographically distributed production services. However, the development environment prioritizes cost savings and does not require the highest network performance. Configuring Premium Tier for development would therefore create avoidable networking expenses. This option fulfills the production latency requirement but does not fulfill the requirement to minimize development costs.

**D is incorrect** because Standard Tier would reduce networking costs for both environments but would not provide the best available network performance for production. Standard Tier routes traffic through ISP networks and generally keeps traffic on Google’s network only within the region containing the workload. This approach is economical and appropriate for development, testing, or other cost-sensitive workloads that can tolerate ordinary internet routing. However, production trading services require minimal latency and predictable performance when communicating with users and external systems in multiple locations. Premium Tier is more appropriate for those production connections because it uses Google’s global backbone for a larger portion of the traffic path. Using Standard Tier for production therefore conflicts with the primary production requirement.

**Reference links**

- [docs.cloud.google.com/network-tiers/docs/overview](https://docs.cloud.google.com/network-tiers/docs/overview)
- [docs.cloud.google.com/network-tiers/docs/set-network-tier](https://docs.cloud.google.com/network-tiers/docs/set-network-tier)
- [cloud.google.com/vpc/network-pricing](https://cloud.google.com/vpc/network-pricing)

**Related notes:** [Network Service Tiers](../06-networking/products/network-service-tiers.md)

</details>

[Back to index](#index)

---

### Q15

> BrightTrail, an online travel-planning company, stores destination photographs in a Cloud Storage bucket named brighttrail-approved-media. An external design agency needs to list and download objects from only this bucket. The agency must not upload, modify, or delete objects and must not access other resources in the Google Cloud project. What should you do?  

- **A.** Create a custom IAM role containing storage.objects.get, and grant the role to the agency at the project level.
- **B.** Grant the agency the Storage Object User role at the project level.
- **C.** Grant the agency the Storage Object User role on the brighttrail-approved-media bucket.
- **D.** Grant the agency the Storage Object Viewer role on the brighttrail-approved-media bucket.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a role granted at the project level is inherited by applicable resources throughout the project. Therefore, storage.objects.get would potentially allow the agency to read objects from every Cloud Storage bucket in the project rather than only brighttrail-approved-media. The custom role also contains only storage.objects.get, so the agency could retrieve an object when its exact name is known but could not list the bucket’s objects because storage.objects.list is absent. Creating a custom role is unnecessary because Google Cloud already provides a predefined read-only role that includes the appropriate object permissions.

**B is incorrect** because the Storage Object User role provides more than read-only access. It includes permissions to create, read, update, move, restore, list, and delete objects, along with permissions for folders and multipart uploads. Granting this role at the project level would allow the agency to perform these operations across applicable Cloud Storage resources throughout the project. This violates both the read-only requirement and the requirement to restrict access to one bucket.

**C is incorrect** because granting the role at the bucket level correctly limits its scope to brighttrail-approved-media, but the Storage Object User role still grants excessive permissions. The agency could create new objects and update, move, restore, or delete existing objects in the bucket. IAM should follow the principle of least privilege, so a role containing write and delete permissions should not be granted when the agency only needs to list and download objects.

**D is correct** because the Storage Object Viewer role provides read-only access to objects and their metadata and includes storage.objects.get and storage.objects.list. Granting this role on the specific bucket limits the agency’s permissions to objects within brighttrail-approved-media instead of applying them to every bucket in the project. The role does not grant object creation, modification, or deletion permissions, making this combination of the appropriate role and the narrowest required resource scope consistent with the principle of least privilege.

**Reference links**

- [docs.cloud.google.com/storage/docs/access-control/iam-roles](https://docs.cloud.google.com/storage/docs/access-control/iam-roles)
- [docs.cloud.google.com/storage/docs/access-control/using-iam-permissions](https://docs.cloud.google.com/storage/docs/access-control/using-iam-permissions)
- [docs.cloud.google.com/iam/docs/resource-hierarchy-access-control](https://docs.cloud.google.com/iam/docs/resource-hierarchy-access-control)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q16

> Northwind Media runs a video-processing service on several existing Compute Engine VM instances in a Google Cloud project. Its support engineers must be able to start, stop, and reset these VMs during incident recovery. They must not delete VMs or change machine types, disks, metadata, service accounts, or network interfaces. What should you do?  

- **A.** Grant the support engineers the Editor role with an IAM condition that applies only when resource.type == 'compute.googleapis.com/Instance'.
- **B.** Grant the support engineers the Compute Instance Admin (v1) role on the project and use an IAM condition to remove compute.instances.delete.
- **C.** Create a custom IAM role containing only compute.instances.start, compute.instances.stop, and compute.instances.reset, and grant it to the support engineers on the project.
- **D.** Grant the support engineers the Compute Viewer role and ask them to perform start, stop, and reset operations from the Google Cloud console.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the Editor role grants broad permissions to create and modify resources across many Google Cloud services. An IAM condition can determine when an entire role binding applies based on supported attributes, such as the resource type, name, or tags, but it does not remove unwanted permissions from the role. Even when the condition limits the binding to Compute Engine instances, the Editor role still contains permissions that can modify instance settings and may include other actions beyond starting, stopping, and resetting. Basic roles are also intentionally broad and are unsuitable when strict least-privilege access is required.

**B is incorrect** because the Compute Instance Admin (v1) role contains extensive permissions for administering VM instances. In addition to starting, stopping, and resetting instances, it includes permissions to create and delete instances, attach or detach disks, change metadata, modify machine types, update network interfaces, change service accounts, and alter other instance properties. IAM Conditions control whether a role binding is effective in a particular context; they cannot subtract compute.instances.delete or any other individual permission from a predefined role. Removing permissions from a predefined role requires replacing it with a suitably designed custom role rather than attaching a condition.

**C is correct** because a custom IAM role can contain the exact Compute Engine permissions required for the approved operational tasks. The compute.instances.start permission allows engineers to power on stopped instances, compute.instances.stop allows them to shut down running instances, and compute.instances.reset allows them to perform a hard reset. Because the role excludes compute.instances.delete and configuration-changing permissions such as compute.instances.setMachineType, compute.instances.setMetadata, compute.instances.setServiceAccount, and compute.instances.updateNetworkInterface, the engineers cannot perform the prohibited administrative operations. Granting this narrowly defined role follows the principle of least privilege. In an implementation where engineers must locate and inspect instances through the Google Cloud console, minimal read permissions such as compute.instances.get and compute.instances.list might also be required, but the three lifecycle permissions are the permissions that authorize the requested actions.

**D is incorrect** because the Compute Viewer role provides read-only access to Compute Engine resources. It allows users to inspect VM instances and their configuration, but it does not include compute.instances.start, compute.instances.stop, or compute.instances.reset. The Google Cloud console does not bypass IAM authorization; its buttons invoke Compute Engine API operations and those operations fail when the signed-in principal lacks the required permissions. Merely instructing the engineers to use the console therefore does not grant the necessary operational access.

**Reference links**

- [docs.cloud.google.com/compute/docs/access/iam](https://docs.cloud.google.com/compute/docs/access/iam)
- [docs.cloud.google.com/iam/docs/creating-custom-roles](https://docs.cloud.google.com/iam/docs/creating-custom-roles)
- [docs.cloud.google.com/iam/docs/conditions-overview](https://docs.cloud.google.com/iam/docs/conditions-overview)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q17

> ParcelPulse runs its shipment-tracking web application as a Cloud Run for Anthos service. The team wants to release an updated container image and direct 15% of production traffic to it while the existing version continues serving the remaining traffic. What should the team do?  

- **A.** Deploy the updated application as a separate service and divide traffic between the new service and the existing service.
- **B.** Deploy the updated application as a new revision of the existing service and configure a traffic split between the new revision and the current revision.
- **C.** Deploy the updated application as a separate service and place an external Application Load Balancer in front of both services.
- **D.** Deploy the updated application as a new revision and place an external Application Load Balancer in front of the two revisions.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because creating a separate service produces an independently managed Cloud Run for Anthos resource with its own endpoint, configuration, revisions, and lifecycle. Native percentage-based canary deployment is designed to distribute a service’s traffic among different revisions of that same service. A separate service could be incorporated into a custom routing architecture, but it would add unnecessary configuration and would not use the built-in revision traffic-splitting capability intended for gradual rollouts.

**B is correct** because deploying the updated container image to the existing Cloud Run for Anthos service creates a new immutable revision. The service can then be configured to send 15% of incoming traffic to the new revision and 85% to the currently stable revision. Both versions remain behind the same service endpoint, so clients do not need to change their URLs. The team can monitor the canary revision and gradually increase its traffic allocation if it performs successfully. If problems occur, the team can quickly route all traffic back to the previous revision without redeploying the application.

**C is incorrect** because a separate service and an external Application Load Balancer are not required for a standard canary deployment. Although a load balancer can distribute requests among multiple backends in more complex architectures, Cloud Run for Anthos already supports traffic distribution among revisions of a service. Creating another service and adding a load balancer increases operational complexity, introduces additional routing configuration, and separates the two versions from the service’s native revision history.

**D is incorrect** because revisions are versions managed within a Cloud Run for Anthos service rather than independent services that normally need to be placed directly behind an external Application Load Balancer. The service itself performs revision selection according to its configured traffic percentages. Adding a load balancer in front of individual revisions bypasses the simpler native rollout mechanism and creates unnecessary infrastructure. The correct approach is to configure the traffic split on the existing service.

**Reference links**

- [docs.cloud.google.com/run/docs/managing/revisions](https://docs.cloud.google.com/run/docs/managing/revisions)
- [docs.cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration](https://docs.cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration)
- [docs.cloud.google.com/sdk/gcloud/reference/run/services/update-traffic](https://docs.cloud.google.com/sdk/gcloud/reference/run/services/update-traffic)

**Related notes:** [Anthos / Cloud Run for Anthos](../03-compute-containers/products/anthos-cloud-run-for-anthos.md)

</details>

[Back to index](#index)

---

### Q18

> BlueHarbor Logistics operates virtual machines across several Google Cloud projects in its organization. During a security review, the infrastructure team must find every Compute Engine instance that has an external IP address. The team wants a centralized solution that requires minimal custom code and is maintained by Google Cloud. What should the team do?  

- **A.** Enforce the compute.vmExternalIpAccess organization policy constraint at the organization level.
- **B.** Open Cloud Shell and use Gemini CLI to retrieve instances with external IP addresses from the Compute Engine API.
- **C.** Use Cloud Asset Inventory to query Compute Engine instances across the organization for external IP addresses.
- **D.** Develop a shell script that runs gcloud CLI commands against every project and filters instances containing external IP addresses.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the compute.vmExternalIpAccess organization policy constraint controls whether Compute Engine VM instances can be created or updated with external IPv4 addresses. It is a preventive governance control rather than an asset-discovery or reporting service. Enforcing the constraint does not generate an inventory of all instances that currently have public IP addresses, and existing instances can continue to retain their external IP addresses until a relevant configuration change occurs. Although the constraint could be useful after the audit to prevent unauthorized external IP assignments, it does not satisfy the immediate requirement to identify affected instances.

**B is incorrect** because Cloud Shell and Gemini CLI could help an administrator construct and execute Compute Engine API queries, but this would be an interactive, command-driven approach rather than a centralized inventory solution. The administrator would need to account for every project, aggregate results, handle pagination, maintain the query logic, and repeat the process whenever an updated report is required. Gemini CLI can assist with command generation and analysis, but it does not replace a purpose-built organization-wide asset inventory service. This approach therefore introduces more operational effort and is less maintainable than using Cloud Asset Inventory.

**C is correct** because Cloud Asset Inventory is a fully managed Google Cloud service designed to inventory, search, export, monitor, and analyze resource metadata across projects, folders, and organizations. Compute Engine instances are supported asset types, and their asset metadata includes network configuration information that can be examined to determine whether an external IP address is assigned. An organization-level Cloud Asset Inventory query provides a centralized view without requiring administrators to iterate manually through every project or maintain custom collection scripts. Cloud Asset Inventory also supports SQL-compatible asset queries and exports to services such as BigQuery for more advanced or recurring analysis, making it the simplest managed and maintainable solution.

**D is incorrect** because a shell script using the gcloud CLI could retrieve instances and filter their network interface information for external IP addresses, but it would be a custom solution that the organization must develop and maintain. The script would need to discover projects, use the correct credentials and permissions, process multiple zones or aggregated instance results, handle pagination and errors, and adapt to future command or output changes. It would also provide only a point-in-time result unless additional scheduling, storage, and monitoring components were created. Cloud Asset Inventory already provides these centralized inventory capabilities as a managed service, so maintaining a custom script is unnecessary.

**Reference links**

- [docs.cloud.google.com/asset-inventory/docs/asset-inventory-overview](https://docs.cloud.google.com/asset-inventory/docs/asset-inventory-overview)
- [docs.cloud.google.com/asset-inventory/docs/query-assets-with-sql](https://docs.cloud.google.com/asset-inventory/docs/query-assets-with-sql)
- [docs.cloud.google.com/compute/docs/access/organization-policies](https://docs.cloud.google.com/compute/docs/access/organization-policies)

**Related notes:** [Cloud Asset Inventory](../02-identity-security/products/cloud-asset-inventory.md)

</details>

[Back to index](#index)

---

### Q19

> GlobeSeat operates an international airline reservation platform that runs in several Google Cloud regions. The platform stores flight schedules, passenger reservations, and seat assignments using relational tables. Customers worldwide must always see the same current seat availability so that the same seat cannot be sold twice. You need to choose a database that provides low-latency access for global users while maintaining a single, strongly consistent state. What should you do?  

- **A.** Use Bigtable for application data storage.
- **B.** Use Cloud SQL for application data storage.
- **C.** Use Spanner for application data storage.
- **D.** Use Firestore for application data storage.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Bigtable is a scalable, low-latency NoSQL wide-column database rather than a relational database. It is well suited for workloads such as time-series data, telemetry, personalization, financial market data, and high-throughput key-based access. However, it does not provide the traditional relational model required by the application. Bigtable does not support relational joins, and its transactions are limited primarily to operations within a single row. Although Bigtable can replicate data across clusters and regions, some multi-cluster routing configurations can return data before all replicas have received the latest update. The application requires relational tables, multi-row transactions, and an identical current state for users worldwide, so Bigtable is not the best choice.

**B is incorrect** because Cloud SQL is a managed relational database service that supports MySQL, PostgreSQL, and SQL Server, but a Cloud SQL instance is hosted primarily in one selected region. High availability protects an instance across zones within a region, rather than creating a globally distributed writable relational database. Cross-region read replicas can place read-only copies closer to users, but replication to those replicas is asynchronous. Consequently, a replica can temporarily return older data than the primary instance. All writes must also be sent to the primary writable instance, which can create significant latency for users located far from that region. Cloud SQL meets the relational requirement but does not optimally satisfy the combined requirements for globally distributed deployment, low latency, and one strongly consistent global state.

**C is correct** because Spanner is a distributed relational database designed for globally available, mission-critical transactional applications. It supports relational schemas, SQL queries, secondary indexes, ACID transactions, and horizontal scaling. A multi-region Spanner instance synchronously replicates data across geographically separated locations and provides strong transactional consistency. This means committed transactions are observed in a globally consistent order, allowing clients in different locations to operate against one authoritative database state. The application can therefore prevent conflicting seat reservations and ensure that customers worldwide receive a consistent view of availability. Spanner also provides regional, dual-region, and multi-region instance configurations, allowing the organization to place replicas closer to users and select leader regions based on application traffic patterns. This combination of relational capabilities, global distribution, strong consistency, high availability, and location-aware configuration makes Spanner the most appropriate choice.

**D is incorrect** because Firestore is a scalable NoSQL document database rather than a relational database. It stores information as documents organized into collections and supports transactions and strongly consistent queries. Firestore can also use multi-region locations to provide high availability. However, it does not natively represent data through conventional relational tables, foreign keys, or SQL joins. Implementing relationships among flights, passengers, reservations, payments, and seat assignments would require denormalized documents, duplicated data, and application-managed relationship logic. Although Firestore is effective for mobile applications, web applications, user profiles, content systems, and document-oriented workloads, the explicit requirement for a globally distributed relational structure makes Spanner the better fit.

**Reference links**

- [cloud.google.com/spanner](https://cloud.google.com/spanner)
- [docs.cloud.google.com/spanner/docs/instance-configurations](https://docs.cloud.google.com/spanner/docs/instance-configurations)
- [docs.cloud.google.com/bigtable/docs/schema-design](https://docs.cloud.google.com/bigtable/docs/schema-design)

**Related notes:** [Spanner](../05-storage-databases-data/products/spanner.md)

</details>

[Back to index](#index)

---

### Q20

> AsterWave Health recently introduced an automated workflow for creating Google Cloud projects. During a governance review, the cloud administration team discovers several older projects that employees created outside this workflow. The team needs to determine who originally created these projects so that those employees can be notified about the approved process. What should the team do?  

- **A.** Examine each project for a creator label and use its value to identify the employee who created the project.
- **B.** Use Resource Manager to determine the business unit from each project’s position in the resource hierarchy.
- **C.** Identify the Cloud Billing account associated with each project and contact the billing account owner.
- **D.** Review each project’s IAM policy in the Google Cloud console and identify the user who was granted the Owner role.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Google Cloud does not automatically add a creator label containing the identity of the person who created a project. Project labels are user-defined key-value pairs used to categorize resources, filter projects, and organize billing data. A creator label would be useful only if the organization’s earlier provisioning process explicitly applied and maintained such a label. Because these projects were created manually before the standardized process existed, there is no guarantee that a creator label is present or accurate.

**B is incorrect** because the Resource Manager hierarchy shows how an organization, folders, projects, and supported resources are structurally related. A project’s parent folder might indicate the department, environment, or business unit responsible for the project, but it does not identify the individual who originally created it. Projects can also be moved between folders after creation, so their current location might not represent the person or team that initially provisioned them.

**C is incorrect** because a project’s linked Cloud Billing account determines which billing account pays for the project’s billable usage. The billing account owner administers billing-related access and might support many projects created by different employees or teams. Linking a project to a billing account does not establish that the billing account owner created the project, so contacting that person would not reliably identify the original creator.

**D is correct** because the initial IAM policy of a newly created Google Cloud project automatically grants the Owner role, roles/owner, to the project’s creator. Reviewing the project’s IAM policy and identifying the user with the directly assigned Owner role is therefore the most appropriate choice among the available options for locating the likely creator of each older project. This method is most reliable when the original Owner binding has not subsequently been removed or when additional owners have not been added. For a definitive historical investigation, Resource Manager Admin Activity audit logs can record who performed the project-creation operation, subject to the organization’s log-retention period; however, reviewing audit logs is not one of the listed choices.

**Reference links**

- [docs.cloud.google.com/resource-manager/docs/access-control-proj](https://docs.cloud.google.com/resource-manager/docs/access-control-proj)
- [docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy](https://docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)
- [docs.cloud.google.com/resource-manager/docs/audit-logging](https://docs.cloud.google.com/resource-manager/docs/audit-logging)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q21

> OrionVista Analytics is establishing a sandbox environment for a new research team. The researchers will run experiments in temporary Google Cloud projects and need complete administrative control over those projects. All researchers are members of one Google group. The company must ensure that resources are created only in europe-west4 and that the environment can use only BigQuery and Cloud Storage. What should you do?  

- **A.** -Create a dedicated folder.  
  -Apply organization policies to the folder that restrict resource locations to europe-west4 and restrict service usage to BigQuery and Cloud Storage.  
  -Grant the group the Owner role on the folder.
- **B.** -Create a dedicated folder.  
  -Apply organization policies to the folder that restrict resource locations to europe-west4 and restrict service usage to BigQuery and Cloud Storage.  
  -Grant the group the BigQuery Admin and Storage Admin roles on the folder.
- **C.** -Create a dedicated folder.  
  -Apply an organization policy to the folder that restricts resource locations to europe-west4.  
  -Grant the group the Owner role on the folder.
- **D.** -Create a dedicated folder.  
  -Apply an organization policy to the folder that restricts resource locations to europe-west4.  
  -Grant the group the BigQuery Admin and Storage Admin roles on the folder.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a dedicated folder provides a common governance and access-control boundary for all temporary projects created for the research team. An organization policy using the gcp.resourceLocations constraint can restrict supported resources in the folder’s descendant projects to europe-west4. A second organization policy using the gcp.restrictServiceUsage constraint can limit supported Google Cloud resource services to BigQuery and Cloud Storage. Organization policies applied at the folder level are inherited by projects beneath that folder, so newly provisioned projects automatically receive the same restrictions. Granting the Owner role to the Google group at the folder level gives its members broad administrative access inherited by the projects while the organization policies continue to enforce the location and service boundaries. IAM grants permissions, but organization policies impose constraints that remain effective even for project owners, providing the required combination of administrative freedom and centralized governance.

**B is incorrect** because the location and service organization policies correctly enforce the required environmental restrictions, but the BigQuery Admin and Storage Admin roles do not provide full administrative access to the projects. These roles grant extensive permissions within BigQuery and Cloud Storage, respectively, but they do not provide general project administration capabilities such as managing all project-level IAM policies, configuring other project settings, or performing broader Resource Manager administration. Because the requirement explicitly states that the team needs complete administrative access within the controlled sandbox projects, service-specific administrator roles are insufficient. The broader Owner role should be granted while organization policies independently prevent the use of unauthorized services and locations.

**C is incorrect** because granting the Owner role at the folder level provides the required broad administrative access, and the resource-location organization policy restricts supported resource creation to europe-west4. However, this design does not restrict the projects to BigQuery and Cloud Storage. Members with the Owner role could enable and use other Google Cloud services because no service-usage organization policy prevents them from doing so. IAM cannot be used by itself to create a reliable allowlist of services for a principal with broad administrative permissions. The folder also needs the gcp.restrictServiceUsage organization policy constraint configured to allow only the approved services.

**D is incorrect** because this option fails to satisfy two requirements. First, the BigQuery Admin and Storage Admin roles provide administrative control only over those individual services and do not provide full administrative access to the projects. Second, restricting resource locations does not prevent the team from enabling or using other Google Cloud services. Some additional services could still be used in europe-west4 or could create global resources that are not controlled in the intended manner by the location policy alone. A service-usage restriction is therefore required in addition to the resource-location restriction, and the Owner role is required to provide the requested project-level administrative access.

**Reference links**

- [docs.cloud.google.com/organization-policy/restrict-locations](https://docs.cloud.google.com/organization-policy/restrict-locations)
- [docs.cloud.google.com/organization-policy/restrict-services](https://docs.cloud.google.com/organization-policy/restrict-services)
- [docs.cloud.google.com/iam/docs/resource-hierarchy-access-control](https://docs.cloud.google.com/iam/docs/resource-hierarchy-access-control)

**Related notes:** [Organization Policy Service](../02-identity-security/products/organization-policy-service.md)

</details>

[Back to index](#index)

---

### Q22

> SilverLeaf Publishing stores digital publications and compliance records in Cloud Storage. An administrator must receive automated notifications whenever stored objects are created, replaced, have metadata updated, archived, or deleted. The company also needs to recover earlier object generations after accidental changes while minimizing custom administration. What should SilverLeaf Publishing do?  

- **A.** Review Cloud Audit Logs for the Cloud Storage buckets in Logs Explorer and filter only for Admin Activity audit logs.
- **B.** Enable Object Versioning on the Cloud Storage buckets and configure Pub/Sub notifications for all supported object-change event types.
- **C.** Enable Object Versioning on the Cloud Storage buckets and deploy a custom program that periodically compares object generations and sends alerts when it detects changes.
- **D.** Configure legacy Object change notifications on the Cloud Storage buckets and forward the events to Pub/Sub.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Admin Activity audit logs primarily record administrative actions that modify resource configuration or metadata, such as changing bucket settings or IAM policies. Modifications to the user-provided data stored inside Cloud Storage objects are generally recorded as Data Access audit logs rather than Admin Activity logs, and Data Access audit logs usually must be explicitly enabled. In addition, manually viewing logs in Logs Explorer does not provide an automated notification whenever an object changes. This approach could therefore miss relevant object operations and would require ongoing manual monitoring, which does not satisfy the requirement to minimize management overhead.

**B is correct** because Pub/Sub notifications for Cloud Storage provide a managed, event-driven mechanism for sending messages when supported object events occur. The company can configure notifications for events such as OBJECT_FINALIZE when an object is created or overwritten, OBJECT_METADATA_UPDATE when object metadata changes, OBJECT_DELETE when an object is deleted, and OBJECT_ARCHIVE when a live object becomes noncurrent in a versioned bucket. A Pub/Sub subscription can deliver these events to an alerting service, Cloud Run service, Cloud Run function, or another subscriber without requiring periodic bucket scans. Enabling Object Versioning preserves noncurrent object generations when live objects are replaced or deleted, allowing administrators to recover an earlier generation after an accidental modification. Together, Object Versioning and Pub/Sub notifications address both recovery and automated notification requirements while relying on managed Google Cloud features. Because Pub/Sub provides at-least-once delivery, the subscriber should use the bucket name, object name, generation number, and event identifiers to process duplicate notifications safely.

**C is incorrect** because Object Versioning can retain previous object generations, but a custom scanning script adds unnecessary operational complexity. The company would need to schedule and host the script, maintain object-generation checkpoints, handle pagination, secure its credentials, detect failures, retry unsuccessful alerts, and prevent duplicate or missed notifications. Its notification delay would also depend on how frequently the script scans the buckets. Pub/Sub notifications already provide a native event-driven mechanism for reporting object changes, so building and maintaining a polling solution does not follow the requirement to minimize management overhead.

**D is incorrect** because legacy Object change notifications are deprecated and should not be used for a new implementation. The legacy mechanism was designed around sending change notifications to an HTTPS webhook endpoint rather than directly publishing events to Pub/Sub. Google recommends Pub/Sub notifications for Cloud Storage as the replacement for generating notifications about object changes. Therefore, the company should create Pub/Sub notification configurations directly on its buckets instead of deploying a deprecated notification mechanism.

**Reference links**

- [docs.cloud.google.com/storage/docs/pubsub-notifications](https://docs.cloud.google.com/storage/docs/pubsub-notifications)
- [docs.cloud.google.com/storage/docs/object-versioning](https://docs.cloud.google.com/storage/docs/object-versioning)
- [docs.cloud.google.com/logging/docs/audit](https://docs.cloud.google.com/logging/docs/audit)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q23

> PixelForge Studios operates a large rendering farm with 4,500 Compute Engine workers. The workers must simultaneously read and write files in a shared 3-petabyte asset repository using standard POSIX file operations. The rendering pipeline requires low latency and extremely high aggregate throughput. The source assets are currently stored in Cloud Storage and must be imported before rendering begins. Which storage service should PixelForge Studios use?  

- **A.** Cloud Storage Standard accessed directly through the JSON API
- **B.** One Persistent Disk attached to every worker in read-write mode
- **C.** Google Cloud Managed Lustre
- **D.** Cloud SQL for PostgreSQL

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Cloud Storage is object storage rather than a POSIX-compliant parallel file system. Applications accessing Cloud Storage through the JSON API interact with buckets and immutable objects by using HTTP-based operations instead of normal file-system operations such as opening files by path, seeking within files, locking files, or updating arbitrary file blocks. Cloud Storage is highly scalable and is suitable for holding the source assets, backups, and final rendering outputs, but direct JSON API access does not provide the shared low-latency POSIX namespace required by thousands of tightly coupled rendering workers. In this architecture, Cloud Storage is better used as the source from which data is staged into the high-performance file system.

**B is incorrect** because Persistent Disk is block storage intended to be attached to a limited number of Compute Engine instances, not a fully managed distributed parallel file system for thousands of workers. A single disk cannot be attached read-write to thousands of Compute Engine instances in the manner described. Supported multi-writer Persistent Disk configurations have strict instance, machine-type, and file-system limitations, and the participating instances must use cluster-aware software to coordinate writes. A single disk would also impose centralized capacity, IOPS, and throughput limits rather than distributing file operations across a scalable parallel storage architecture.

**C is correct** because Google Cloud Managed Lustre is a fully managed parallel file system designed for high-performance computing, artificial intelligence, rendering, and other data-intensive workloads. Compute Engine workers can mount the same Managed Lustre file system and access a shared namespace through standard POSIX file operations. Lustre distributes data and I/O across multiple storage resources, allowing many workers to access files concurrently while delivering high aggregate throughput and low latency. Managed Lustre supports multi-petabyte-scale file systems and is therefore appropriate for the 3-petabyte asset repository. It can also import data from Cloud Storage and export data back to Cloud Storage, which supports the company’s requirement to stage source assets before processing and preserve outputs afterward.

**D is incorrect** because Cloud SQL for PostgreSQL is a managed relational database service, not a shared parallel file system. It is intended for structured data represented through databases, tables, rows, indexes, and SQL transactions. Storing several petabytes of rendering assets as database objects would not provide POSIX file access and would create unnecessary database overhead. Cloud SQL also does not supply the distributed file-level throughput required by thousands of Compute Engine workers performing concurrent reads and writes.

**Reference links**

- [docs.cloud.google.com/managed-lustre/docs/overview](https://docs.cloud.google.com/managed-lustre/docs/overview)
- [docs.cloud.google.com/managed-lustre/docs/transfer-data](https://docs.cloud.google.com/managed-lustre/docs/transfer-data)
- [docs.cloud.google.com/compute/docs/disks/sharing-disks-between-vms](https://docs.cloud.google.com/compute/docs/disks/sharing-disks-between-vms)

**Related notes:** [Google Cloud Managed Lustre](../05-storage-databases-data/products/google-cloud-managed-lustre.md)

</details>

[Back to index](#index)

---

### Q24

> StreamCart runs its order-processing service on one Compute Engine VM. The service writes error and transaction logs to /var/log/streamcart/orders.log. Customers report that checkout requests are failing, but the application logs are not currently available in Cloud Logging. What should the operations team do to investigate the failures?  

- **A.** Open Logs Explorer in Cloud Logging and search for the application’s file-based logs.
- **B.** Create a health check for the VM and configure the Healthy threshold to require three consecutive successful probes.
- **C.** Enable the VM’s interactive serial console and use the serial-port output to review the application logs.
- **D.** Install the Ops Agent, configure it to collect the application log file, and examine the collected entries in Cloud Logging.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Cloud Logging can display only the log entries that have been sent or ingested into it. Compute Engine automatically produces certain platform logs, audit logs, and serial-port output, but a custom application log written to an arbitrary file such as /var/log/streamcart/orders.log is not automatically collected. Because the scenario states that the file-based application logs are not currently available in Cloud Logging, opening Logs Explorer alone will not make those logs appear. A log collection mechanism must first read the file and forward its entries to Cloud Logging.

**B is incorrect** because a health check determines whether a backend responds successfully to periodic probes; it does not collect, parse, or display application log files. The Healthy threshold controls how many consecutive successful probes are required before an unhealthy backend is considered healthy again. Changing this threshold might affect backend health-state transitions in a load-balancing configuration, but it would not reveal the cause of checkout errors or transfer the contents of the application’s disk-based log file to Cloud Logging. Additionally, a health check is primarily an availability-detection mechanism rather than a diagnostic logging solution.

**C is incorrect** because the serial console is primarily intended for troubleshooting boot failures, operating-system problems, networking issues, or instances that cannot be reached through normal remote-access methods. Serial-port output contains information explicitly written to the serial device by the operating system or an application. A custom application log stored in a regular disk file does not automatically appear in serial-port output. Although an administrator might enable interactive serial-console access, authenticate to the VM, obtain a shell, and manually inspect the file, this is not the appropriate log-management solution and requires additional access configuration. It also does not provide centralized querying, filtering, retention, or ongoing collection through Cloud Logging.

**D is correct** because the Ops Agent is Google Cloud’s supported agent for collecting logs and metrics from Compute Engine instances. The team can install the agent and configure a file receiver that monitors /var/log/streamcart/orders.log. The receiver reads newly written records from the file, and a logging pipeline sends those records to Cloud Logging. The operations team can then use Logs Explorer to search the entries, filter them by VM resource, severity, timestamp, or application-specific fields, and correlate customer checkout failures with recorded errors. This approach solves the underlying problem that the application writes logs only to local disk and also establishes centralized, continuous log collection for future troubleshooting.

**Reference links**

- [docs.cloud.google.com/logging/docs/agent/ops-agent/installation](https://docs.cloud.google.com/logging/docs/agent/ops-agent/installation)
- [docs.cloud.google.com/logging/docs/agent/ops-agent/configuration](https://docs.cloud.google.com/logging/docs/agent/ops-agent/configuration)
- [docs.cloud.google.com/compute/docs/troubleshooting/troubleshooting-using-serial-console](https://docs.cloud.google.com/compute/docs/troubleshooting/troubleshooting-using-serial-console)

**Related notes:** [Ops Agent](../07-operations-cost/products/ops-agent.md)

</details>

[Back to index](#index)

---

### Q25

> BrightCart, an online retail company, is deploying a package-processing service on a Compute Engine VM. Security policies require the VM to have no external IP address, but the service must initiate outbound internet connections to retrieve operating system patches and software dependencies. Which configuration should BrightCart use?  

- **A.** Peer the VM’s VPC network with another VPC network that has internet connectivity.
- **B.** Deploy a bastion host with an external IP address and access the private VM through SSH.
- **C.** Reserve and assign a static internal IP address to the VM.
- **D.** Configure Cloud NAT for the subnet containing the VM.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because VPC Network Peering provides private connectivity between resources in two VPC networks, but it does not automatically allow a VM to use the peered network’s internet gateway or external IP addresses. VPC Network Peering is non-transitive, and internet gateway routes are not shared between peered networks. Therefore, connecting the application’s VPC network to another VPC network with internet connectivity would not provide the required outbound internet access.

**B is incorrect** because a bastion host is primarily an administrative access solution. It provides an externally reachable entry point from which administrators can connect to private VMs through SSH. It does not automatically function as a NAT gateway for the application VM’s outbound internet traffic. Although a bastion host could theoretically be configured as a custom proxy or NAT instance, that would require additional routing, forwarding, security, availability, and maintenance configurations. It is unnecessary when Cloud NAT provides a managed solution specifically for this requirement.

**C is incorrect** because a static internal IP address only gives the VM a persistent private address within its VPC network. An internal IP address can be used for communication with other privately reachable resources, but it is not publicly routable and cannot independently provide access to destinations on the internet. Whether the internal IP address is static or ephemeral does not change the VM’s outbound internet connectivity.

**D is correct** because Cloud NAT allows Compute Engine VMs without external IP addresses to initiate outbound connections to the internet. Cloud NAT translates the VM’s internal source IP address and port into an external NAT IP address and port for outbound traffic, while preventing unsolicited inbound internet connections from reaching the VM. Configuring Public NAT for the subnet therefore enables the application to download updates and packages without assigning an external IP address directly to the VM. The configuration must also permit the required outbound traffic through applicable firewall rules.

**Reference links**

- [docs.cloud.google.com/nat/docs/overview](https://docs.cloud.google.com/nat/docs/overview)
- [docs.cloud.google.com/nat/docs/gce-example](https://docs.cloud.google.com/nat/docs/gce-example)
- [docs.cloud.google.com/vpc/docs/vpc-peering](https://docs.cloud.google.com/vpc/docs/vpc-peering)

**Related notes:** [Cloud NAT](../06-networking/products/cloud-nat.md)

</details>

[Back to index](#index)

---

### Q26

> PixelHarbor is preparing a containerized analytics service in a newly created Google Cloud project. An administrator runs the gcloud container clusters create metrics-cluster command, but the operation returns this below mentioned message. The administrator must create the GKE cluster successfully. What should the administrator do?  
> ERROR: (gcloud.container.clusters.create) ResponseError: code=403, message=Kubernetes Engine API has not been used in the project before or it is disabled.  

- **A.** Run the command again with the --enable-autoprovisioning flag.
- **B.** Turn off the “Require enabling Workload Identity Federation for GKE” organization policy, and retry the cluster creation command.
- **C.** Grant the Kubernetes Engine Admin IAM role to the administrator, and retry the cluster creation command.
- **D.** Run gcloud services enable container.googleapis.com, and retry the cluster creation command.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because the --enable-autoprovisioning flag enables GKE node auto-provisioning, which allows GKE to create and manage node pools according to workload resource requirements. This setting affects how an existing GKE cluster provisions worker nodes; it does not activate the Kubernetes Engine API in the Google Cloud project. Because the cluster creation request must be processed through container.googleapis.com, adding this flag cannot resolve an error explicitly stating that the API has not been used or is disabled.

**B is incorrect** because the Workload Identity Federation for GKE organization policy controls whether GKE clusters must use Workload Identity Federation for GKE. Workload Identity Federation enables Kubernetes workloads to authenticate to Google Cloud APIs without relying on service account key files. Although an enforced organization policy can affect permitted cluster configurations, disabling this policy does not enable the Kubernetes Engine API. The error occurs before GKE can process the cluster’s identity configuration, so changing this organization policy would not address the stated problem.

**C is incorrect** because the Kubernetes Engine Admin role grants broad permissions to manage GKE resources, including clusters. IAM permissions and API activation are separate requirements. Granting this role might be necessary when a user lacks authorization to create clusters, but the displayed error specifically reports that the Kubernetes Engine API is disabled or has never been used in the project. Adding an IAM role does not change the API’s activation status. The user must also possess permission to enable services, such as the serviceusage.services.enable permission, but granting the Kubernetes Engine Admin role alone does not enable container.googleapis.com.

**D is correct** because container.googleapis.com is the service name for the Kubernetes Engine API. The gcloud services enable container.googleapis.com command activates this API in the currently selected Google Cloud project. Once activation is complete, GKE cluster creation requests can be submitted through the API. The administrator should confirm that the gcloud CLI is configured for the intended project and that the account has permission to enable services. After enabling the API, rerunning gcloud container clusters create metrics-cluster resolves the cause identified in the error message.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/deploy-app-cluster](https://docs.cloud.google.com/kubernetes-engine/docs/deploy-app-cluster)
- [docs.cloud.google.com/sdk/gcloud/reference/services/enable](https://docs.cloud.google.com/sdk/gcloud/reference/services/enable)
- [docs.cloud.google.com/service-usage/docs/enable-disable](https://docs.cloud.google.com/service-usage/docs/enable-disable)

</details>

[Back to index](#index)

---

### Q27

> BluePeak Analytics is adding 48 software engineers from a recently acquired company for an eight-month product consolidation program. The engineers’ identities will remain in the acquired company’s SAML-compatible identity provider. They need consistent browser-accessible development environments with organization-approved IDEs and tools, persistent home directories, and automatic shutdown after periods of inactivity. BluePeak Analytics does not want to create new Google-managed user accounts or configure and maintain each engineer’s physical workstation. What should the company implement?  

- **A.** Configure Workforce Identity Federation for the acquired company’s users and provide Cloud Workstations based on shared workstation configurations with persistent home directories and idle timeouts
- **B.** Configure Workload Identity Federation for each engineer and provide a shared root password for a Compute Engine VM
- **C.** Distribute one service account key to all engineers and assign each engineer a permanently running VM
- **D.** Make Cloud Shell publicly accessible by granting the allUsers principal the Editor role

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Workforce Identity Federation is designed to authenticate human users, including employees, partners, and contractors, through an external identity provider without requiring corresponding Google-managed user accounts. BluePeak Analytics can create a workforce identity pool, configure a SAML provider that trusts the acquired company’s identity provider, map user and group attributes, and use IAM policies to grant the federated engineers only the access they require. The engineers can continue using their existing corporate credentials and receive short-lived Google Cloud credentials through single sign-on. Cloud Workstations complements this identity architecture by providing managed, reproducible development environments that developers can access through a browser-based IDE or supported local editors. Administrators can create a common workstation configuration containing approved container images, IDEs, command-line tools, libraries, machine types, network settings, and security controls. Each engineer receives an individual workstation based on that shared configuration rather than sharing one development session. A persistent disk can be mounted as the user’s home directory so source code, settings, and other permitted files remain available when the temporary workstation VM stops. An idle timeout can automatically stop unused workstations, reducing cost and limiting the exposure of unattended environments. This combination satisfies the identity, standardization, persistence, automatic shutdown, and low workstation-administration requirements.

**B is incorrect** because Workload Identity Federation is intended for non-human workloads, such as applications running outside Google Cloud, CI/CD pipelines, external cloud workloads, and automated services. It is not the appropriate identity federation mechanism for employees interactively signing in to development environments. Human developers whose identities remain in an external SAML provider should use Workforce Identity Federation. A shared Compute Engine root password is also a serious security and operational problem because it removes individual accountability, prevents meaningful attribution in audit records, complicates revocation when a developer leaves the project, and gives every user the same privileged credentials. Operating a shared VM would additionally require the platform team to install tools, patch the operating system, manage user isolation, resolve configuration drift, maintain storage, and implement its own idle shutdown automation. This conflicts with the requirement for standardized managed environments and minimal workstation administration.

**C is incorrect** because service accounts represent applications and other non-human identities rather than individual employees. A single service account key shared by all engineers would provide no reliable way to determine which person performed an action. Long-lived service account keys can be copied, leaked, retained after the project ends, or used from unmanaged systems until they are explicitly rotated or revoked. Sharing one key magnifies the impact of a compromise and prevents access from being independently disabled for one developer. Permanently running VMs would also increase costs and fail the automatic idle-shutdown requirement. The parent company would need to provision, patch, secure, monitor, and maintain these VMs and their development tools, resulting in substantially more administration than using centrally managed Cloud Workstations configurations.

**D is incorrect** because Cloud Shell is a convenience environment associated with an authenticated user and is not a replacement for centrally governed development workstations for a temporary enterprise engineering team. It cannot be converted into an anonymous shared development service simply by granting the allUsers principal an IAM role. Granting Editor to allUsers would attempt to provide broad resource-modification permissions to unauthenticated users, violating least privilege and exposing the Google Cloud environment to severe security risk. Cloud Shell also does not provide the same level of administrator-controlled workstation configuration, machine sizing, network placement, custom development images, persistent storage management, and lifecycle policies available through Cloud Workstations. Workforce Identity Federation should authenticate each developer individually, while IAM and Cloud Workstations should provide controlled access to individually assigned managed environments.

**Reference links**

- [docs.cloud.google.com/iam/docs/workforce-identity-federation](https://docs.cloud.google.com/iam/docs/workforce-identity-federation)
- [docs.cloud.google.com/workstations/docs/overview](https://docs.cloud.google.com/workstations/docs/overview)
- [docs.cloud.google.com/workstations/docs/architecture](https://docs.cloud.google.com/workstations/docs/architecture)

**Related notes:** [Cloud Workstations](../08-iac-platform-ai/products/cloud-workstations.md)

</details>

[Back to index](#index)

---

### Q28

> BrightLedger Solutions received a JSON key file for a service account that has permission to manage resources in the finance-prod-47 Google Cloud project. An administrator installed the Google Cloud CLI on a secured workstation and needs gcloud commands to run as that service account. What should the administrator do?  

- **A.** Run gcloud auth login without a credential-file option and select the JSON private key during the user sign-in process.
- **B.** Run gcloud auth activate-service-account with the --key-file option referencing the JSON private key.
- **C.** Copy the JSON private key into the Google Cloud CLI installation directory and rename it credentials.json.
- **D.** Copy the JSON private key into the administrator’s home directory and rename the file GOOGLE_APPLICATION_CREDENTIALS.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because gcloud auth login normally starts an interactive authorization flow for Google user credentials, whereas the requirement is to authenticate the Google Cloud CLI as a service account by using its private key. The dedicated command for importing and activating service account credentials is gcloud auth activate-service-account. Modern versions of the Google Cloud CLI also support gcloud auth login --cred-file for certain credential files, including service account JSON keys, but the option as written does not specify --cred-file and the direct, purpose-built answer among these choices is gcloud auth activate-service-account.

**B is correct** because gcloud auth activate-service-account imports credentials from a service account private key file and activates that service account as the account used by subsequent gcloud commands. The administrator can run a command such as: 

gcloud auth activate-service-account service-account-name@finance-prod-47.iam.gserviceaccount.com --key-file=/secure/path/key.json --project=finance-prod-47

The --key-file argument identifies the downloaded JSON key, and the optional --project argument sets the active project in the current Google Cloud CLI configuration. After activation, gcloud commands are authenticated as the service account and authorized according to the IAM roles granted to that service account. Because service account keys are long-lived credentials, the file should be stored securely, restricted with operating-system permissions, and deleted or rotated when it is no longer required.

**C is incorrect** because the Google Cloud CLI does not automatically discover a service account key merely because it is stored in the installation directory or named credentials.json. Credential activation requires an authentication command or another explicitly supported credential configuration. Placing a private key in the installation directory also creates an unnecessary security risk because application installation directories might be readable by other users, included in backups, or modified during software upgrades.

**D is incorrect** because GOOGLE_APPLICATION_CREDENTIALS is the name of an environment variable, not the required filename for a credential file. When Application Default Credentials are used, the environment variable must contain the full path to the credential file, for example GOOGLE_APPLICATION_CREDENTIALS=/secure/path/key.json. Application Default Credentials are primarily used by Cloud Client Libraries and other application code, and they are separate from the credential configuration normally used by gcloud commands. Renaming the key file to GOOGLE_APPLICATION_CREDENTIALS does not activate the service account in the Google Cloud CLI.

**Reference links**

- [docs.cloud.google.com/sdk/gcloud/reference/auth/activate-service-account](https://docs.cloud.google.com/sdk/gcloud/reference/auth/activate-service-account)
- [docs.cloud.google.com/sdk/docs/authenticate](https://docs.cloud.google.com/sdk/docs/authenticate)
- [docs.cloud.google.com/docs/authentication/application-default-credentials](https://docs.cloud.google.com/docs/authentication/application-default-credentials)

</details>

[Back to index](#index)

---

### Q29

> Finora Health operates several patient-scheduling applications across multiple Google Cloud projects. The finance department wants every project charged to one central Cloud Billing account and requires billing information to be available each day in a shared BigQuery dataset. Analysts must be able to examine both summarized costs and costs associated with individual resources. The solution should require minimal maintenance and avoid unnecessary processing components. What should the cloud administrator do?  

- **A.** Link every project to the central Cloud Billing account, configure a billing budget with Pub/Sub notifications, and deploy a Cloud Run function that stores each notification in BigQuery.
- **B.** Link every project to the central Cloud Billing account, and enable both standard usage cost export and detailed usage cost export to the central BigQuery dataset.
- **C.** Link every project to the central Cloud Billing account, and enable only standard usage cost export to the central BigQuery dataset.
- **D.** Link every project to the central Cloud Billing account, create a separate budget for each project by using gcloud billing budgets create, and manually download cost information from the Google Cloud console each day.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Cloud Billing budget notifications are designed to report a budget’s status when configured thresholds are evaluated. A Pub/Sub notification can contain information such as the budget amount, current cost, and threshold status, but it does not contain the complete billing usage records, SKU-level charges, credits, labels, or resource-level cost details required for comprehensive financial analysis. A Cloud Run function would also introduce custom code, operational monitoring, permissions, and processing costs. Therefore, this design would neither provide the required billing dataset nor minimize administrative impact.

**B is correct** because projects linked to the same Cloud Billing account can have their billing information exported centrally at the billing-account level. Standard usage cost export provides general billing records such as services, SKUs, projects, locations, usage, costs, credits, and labels. Detailed usage cost export includes the standard information and additional resource-level fields for supported services, allowing analysts to associate costs with individual resources such as Compute Engine instances. Cloud Billing writes the exported records automatically to the selected BigQuery dataset, eliminating the need for custom functions or daily manual exports. Enabling both export types meets the requirements for centralized analysis, comprehensive billing data, and resource-level cost visibility with minimal maintenance.

**C is incorrect** because standard usage cost export provides detailed billing-account, project, service, SKU, usage, and cost information, but it does not provide the expanded resource-level data available through detailed usage cost export. The finance team specifically needs to analyze costs for individual resources. Although standard export would centralize much of the billing data in BigQuery, it would not fully satisfy that requirement. Detailed usage cost export must also be enabled to obtain supported resource identifiers and resource-specific cost information.

**D is incorrect** because Cloud Billing budgets monitor spending against specified amounts; they are not a replacement for exporting complete billing data. Creating a separate budget for every project also increases configuration and maintenance work instead of centralizing cost management at the billing-account level. In addition, manually downloading reports every day is error-prone, does not provide a continuously managed data pipeline, and creates unnecessary administrative overhead. The Google Cloud console’s cost reports are useful for interactive analysis, but automatic Cloud Billing export to BigQuery is the appropriate solution for recurring centralized analysis.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery)
- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-setup](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-setup)
- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-tables/detailed-usage](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-tables/detailed-usage)

**Related notes:** [Cloud Billing](../07-operations-cost/products/cloud-billing.md)

</details>

[Back to index](#index)

---

### Q30

> NorthStar Tickets operates an event-booking application on Google Cloud. Users report a sudden increase in failed reservation requests, and the operations team determines that the application’s service account lacks a required IAM permission. After assigning the minimum required role and restoring the service, the team wants to receive a notification whenever the same permission-related error begins occurring again. What should the team do?  

- **A.** In Logs Explorer, create a query that filters log entries by ERROR severity and the service account name.
- **B.** Create a log sink that exports all application logs to BigQuery, and build a Looker Studio dashboard to display the exported errors.
- **C.** Create a custom log-based metric that matches the specific permission-related error, and use the metric in a Cloud Monitoring alerting policy.
- **D.** Grant the service account the Project Owner role so that it cannot encounter permission-related errors again.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because filtering entries in Logs Explorer helps the operations team investigate existing log data, identify the affected service account, and confirm that the permission error has occurred. However, a saved or manually executed Logs Explorer query does not by itself continuously evaluate the error frequency or send a notification when the problem returns. The team would still need to open Logs Explorer and examine the results manually. Because the requirement is proactive notification when the specific error recurs, merely filtering the logs does not provide the required alerting capability.

**B is incorrect** because exporting all logs to BigQuery and visualizing them in Looker Studio is unnecessarily complex for detecting one known error. A log sink can continuously route matching log entries to BigQuery, and Looker Studio can provide historical analysis and dashboards, but a dashboard is primarily a visualization mechanism rather than the most direct method for generating an operational alert. This approach also introduces additional components, storage costs, query costs, permissions, and maintenance. Cloud Logging and Cloud Monitoring already provide native integration for converting matching log entries into metric data and triggering notifications, so exporting every log entry is not required.

**C is correct** because a custom log-based metric can use a Cloud Logging filter that matches the exact permission-related error, such as the relevant error message, status code, service account identity, resource type, and severity. A counter-type log-based metric increments whenever a matching log entry is received. The team can then create a Cloud Monitoring alerting policy that evaluates the metric and opens an incident when the count exceeds a selected threshold during a defined time window. Notification channels such as email, SMS, PagerDuty, Slack, or Pub/Sub can be associated with the alerting policy. This solution provides continuous, automated detection of the known error and notifies the operations team when the condition recurs without requiring manual log inspection.

**D is incorrect** because the Project Owner role is a highly privileged basic IAM role that grants extensive permissions across the project, including permissions unrelated to the application’s requirements. Granting it to the service account would violate the principle of least privilege and could significantly increase the impact of compromised application credentials. It would also attempt to hide the immediate permission problem by overprivileging the service account instead of monitoring for recurrence. The service account should receive only the predefined or custom IAM role containing the specific permissions required by the application, while Cloud Logging and Cloud Monitoring should be used to detect and alert on future failures.

**Reference links**

- [cloud.google.com/logging/docs/logs-based-metrics](https://cloud.google.com/logging/docs/logs-based-metrics)
- [cloud.google.com/logging/docs/logs-based-metrics/charts-and-alerts](https://cloud.google.com/logging/docs/logs-based-metrics/charts-and-alerts)
- [cloud.google.com/iam/docs/using-iam-securely](https://cloud.google.com/iam/docs/using-iam-securely)

**Related notes:** [Cloud Logging](../07-operations-cost/products/cloud-logging.md)

</details>

[Back to index](#index)

---

### Q31

> BlueHarbor Retail runs its order-processing system on a Cloud SQL for MySQL instance. After financial records close each month, the compliance team requires an independent copy of the database to be retained for four years and accessed only during an audit. What should the cloud team do?  

- **A.** Schedule a Cloud SQL export for 1:30 a.m. on the first day of every month, and write the exported SQL dump file to an Archive storage class Cloud Storage bucket.
- **B.** Retain the automated backup created on the first day of every month for four years, and copy its backup file to an Archive storage class Cloud Storage bucket.
- **C.** Schedule an on-demand Cloud SQL backup for 1:30 a.m. on the first day of every month, and write the backup directly to an Archive storage class Cloud Storage bucket.
- **D.** Convert the automated backup created on the first day of every month into an export file, and write the resulting file to a Coldline storage class Cloud Storage bucket.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a Cloud SQL export creates a portable logical copy of the MySQL database, typically as a compressed or uncompressed SQL dump file, and writes that file directly to Cloud Storage. Scheduling the export shortly after the monthly accounting period closes provides a consistent month-end copy. Because the audit copy must be retained for four years and is expected to be accessed very rarely, the Archive storage class is the most appropriate storage class among the choices. Archive storage is designed for long-term data preservation with infrequent access and has a 365-day minimum storage duration. The organization can also configure a Cloud Storage retention policy and appropriate IAM permissions to prevent the exported audit files from being deleted or modified before their required retention periods expire.

**B is incorrect** because Cloud SQL automated backups are service-managed recovery resources rather than ordinary backup files that customers can copy into their own Cloud Storage buckets. Depending on the selected Cloud SQL backup option, automated backups can support different retention periods, including extended retention with enhanced backups, but they remain managed within the Cloud SQL backup system. An automated backup cannot simply be selected and stored as a backup file in an Archive storage class bucket. Automated backups are primarily intended to restore a Cloud SQL instance, whereas a scheduled export produces an independently stored database copy that can be governed using Cloud Storage retention and access controls.

**C is incorrect** because an on-demand backup is also stored and managed by the Cloud SQL backup service. Standard on-demand backups can remain available until they are manually deleted or until other applicable lifecycle conditions occur, and enhanced on-demand backups can use a configured retention period. However, an on-demand backup cannot be written directly to a customer-selected Cloud Storage bucket as a backup object. To create a file in Cloud Storage, the team must perform a Cloud SQL export rather than create an on-demand backup. Therefore, this option uses the wrong Cloud SQL operation even though Archive storage would otherwise be appropriate for rarely accessed, long-term audit data.

**D is incorrect** because Cloud SQL does not provide an operation that directly converts an existing automated backup into an export file. A database export is a separate operation that runs against a Cloud SQL instance and creates a SQL dump or CSV file in Cloud Storage. Additionally, Coldline storage is intended for data that is expected to be accessed less than approximately once per quarter and has a 90-day minimum storage duration. Archive storage is better aligned with audit records retained for several years and expected to be accessed less than once per year. Therefore, this option proposes both an unsupported backup-conversion process and a less suitable storage class than the one used in option A.

**Reference links**

- [cloud.google.com/sql/docs/mysql/import-export/import-export-sql](https://cloud.google.com/sql/docs/mysql/import-export/import-export-sql)
- [cloud.google.com/sql/docs/mysql/backup-recovery/backups](https://cloud.google.com/sql/docs/mysql/backup-recovery/backups)
- [cloud.google.com/storage/docs/storage-classes](https://cloud.google.com/storage/docs/storage-classes)

**Related notes:** [Cloud SQL](../05-storage-databases-data/products/cloud-sql.md)

</details>

[Back to index](#index)

---

### Q32

> Northstar Retail is moving its analytics and commerce workloads to Google Cloud. The company wants only employees using Northstar-managed Google accounts to receive access. Each business unit, such as Finance, Marketing, and Logistics, must be restricted to its own Google Cloud resources. Northstar wants centralized access management with minimal administrative effort. What should Northstar do?  

- **A.** Add employees to business-unit Google Groups, grant the groups appropriate Identity and Access Management (IAM) roles on their resources, and periodically remove personal Google accounts through manual reviews.
- **B.** Add employees to business-unit Google Groups, grant each group appropriate Identity and Access Management (IAM) roles only on its resources, and enforce a domain-restricted sharing organization policy.
- **C.** Create a Resource Manager folder for every business unit and grant each unit’s employees the Folder Admin role on their corresponding folder.
- **D.** Create a Resource Manager folder for every business unit and grant every Northstar employee the Folder Admin role at the organization level.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because using Google Groups and assigning IAM roles to those groups is a recommended and operationally efficient way to manage access. Group membership can represent each department, and IAM roles can be granted at the appropriate folder, project, or resource scope. However, periodic manual reviews do not prevent an administrator from granting access to an employee’s personal Google account or another external identity between reviews. This reactive approach creates recurring administrative work, increases operational costs, and leaves periods during which unauthorized external accounts might retain access. An organization policy should enforce the identity restriction automatically.

**B is correct** because Google recommends granting IAM roles to groups instead of granting roles separately to individual users. Northstar can create a Google Group for each business unit, manage employees through group membership, and grant each group only the roles required on that unit’s folder, projects, or individual resources. IAM policy inheritance then applies those permissions to resources beneath the selected hierarchy level, reducing repetitive configuration. A domain-restricted sharing organization policy, preferably implemented with the iam.managed.allowedPolicyMembers constraint, can restrict IAM policy members to identities associated with Northstar’s Google Workspace or Cloud Identity organization. This prevents personal Google accounts and identities belonging to unauthorized organizations from being added to IAM allow policies. Combining department-specific groups, least-privilege IAM grants, and centrally enforced domain restrictions satisfies both access requirements while minimizing ongoing administration.

**C is incorrect** because creating folders for departments is a useful resource hierarchy design, but granting all department users the Folder Admin role is excessive. The Folder Admin role permits significant administrative control over the folder hierarchy and its IAM policies. Users with permission to modify a folder’s IAM policy could grant themselves or others additional access to resources inherited beneath that folder. Most employees need workload-specific roles, such as viewer, developer, or service-specific roles, rather than permission to administer the department’s folder and access policies. This option also does not enforce a restriction against personal or external Google accounts, so it fails the company-account requirement.

**D is incorrect** because granting the Folder Admin role at the organization level gives every company user extensive administrative authority across the organization’s folder hierarchy. Permissions granted at the organization level are inherited by descendant folders and resources, so users from one department could administer folders associated with other departments. This violates department isolation, least privilege, and separation of duties. It also increases the risk of accidental or unauthorized IAM changes and does not prevent external identities from being added. Administrative roles should be limited to dedicated administrator groups and granted only at the smallest necessary scope.

**Reference links**

- [docs.cloud.google.com/organization-policy/restrict-domains](https://docs.cloud.google.com/organization-policy/restrict-domains)
- [docs.cloud.google.com/iam/docs/groups-best-practices](https://docs.cloud.google.com/iam/docs/groups-best-practices)
- [docs.cloud.google.com/iam/docs/resource-hierarchy-access-control](https://docs.cloud.google.com/iam/docs/resource-hierarchy-access-control)

</details>

[Back to index](#index)

---

### Q33

> ParcelPilot, a package-tracking website, has containerized its stateless API as a Docker image. The engineering team wants to run and manage the API as a workload on Google Kubernetes Engine. What should the team do?  

- **A.** Upload the Docker image to Cloud Storage and create a Kubernetes Service that references the image.
- **B.** Upload the Docker image to Cloud Storage and create a Kubernetes Deployment that references the image.
- **C.** Push the Docker image to Artifact Registry and create a Kubernetes Service that references the image.
- **D.** Push the Docker image to Artifact Registry and create a Kubernetes Deployment that references the image.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Cloud Storage is designed for storing objects such as documents, media files, archives, and backups. It is not a container image registry that GKE normally uses to pull versioned Docker images. In addition, a Kubernetes Service does not create or run application containers and does not contain a container image field. A Service provides a stable network endpoint for an existing group of Pods, usually by selecting them through labels. Therefore, neither the storage location nor the Kubernetes resource is appropriate for deploying the workload.

**B is incorrect** because a Kubernetes Deployment is the appropriate resource for running a stateless application workload, but Cloud Storage is not the appropriate repository for the Docker image. A Deployment creates and manages ReplicaSets and Pods, and its Pod template specifies the container image that the GKE nodes must pull. That image should be stored in a supported container registry such as Artifact Registry. Placing the Docker image as an ordinary Cloud Storage object does not provide the standard container registry API, image manifests, layer management, tagging, and authentication workflow expected by Kubernetes container runtimes.

**C is incorrect** because Artifact Registry is the correct Google Cloud service for securely storing, versioning, and distributing Docker container images, but a Kubernetes Service cannot deploy the image. A Service only exposes existing Pods over the network and directs traffic to Pods that match its label selector. It does not define a Pod template, specify a container image, maintain replicas, restart failed application instances, or perform rolling updates. The team could create a Service after deploying the application when network access is required, but the Service cannot replace the workload resource.

**D is correct** because Artifact Registry is the recommended Google Cloud repository for storing Docker images that will be deployed to GKE. The team should create an Artifact Registry Docker repository, tag the local image with the repository path, authenticate Docker, and push the image to the repository. The team should then create a Kubernetes Deployment whose Pod template references the complete Artifact Registry image path. The Deployment instructs Kubernetes to create and manage the application Pods, maintain the requested number of replicas, replace failed Pods, and support controlled updates when a new image version is released. A separate Kubernetes Service can subsequently be created if the Pods must be reachable through a stable internal or external network endpoint.

**Reference links**

- [docs.cloud.google.com/artifact-registry/docs/docker/store-docker-container-images](https://docs.cloud.google.com/artifact-registry/docs/docker/store-docker-container-images)
- [docs.cloud.google.com/artifact-registry/docs/integrate-gke](https://docs.cloud.google.com/artifact-registry/docs/integrate-gke)
- [kubernetes.io/docs/concepts/workloads/controllers/deployment/](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)

**Related notes:** [Artifact Registry](../03-compute-containers/products/artifact-registry.md)

</details>

[Back to index](#index)

---

### Q34

> TerraTrack, an agricultural monitoring platform, collects information from farms across several regions. The company needs to store the following data as mentioned below. You need to select the most cost-effective Google Cloud storage services that meet these requirements. What should you do?  
> -Structured farmer account and billing records that require transactions and complex SQL queries  
> -Several petabytes of old equipment logs that are retained for compliance and retrieved less than once per year  
> -Continuous soil and weather telemetry that generates high-throughput writes and must remain available for large-scale analysis, although losing a small amount of telemetry is acceptable  

- **A.** Store farmer account data in Firestore, historical equipment logs in Cloud Storage Nearline storage, and telemetry data in Bigtable.
- **B.** Store farmer account data in Cloud SQL, historical equipment logs in Cloud Storage Coldline storage, and telemetry data in BigQuery.
- **C.** Store farmer account data in Cloud SQL, historical equipment logs in Cloud Storage Archive storage, and telemetry data in Bigtable.
- **D.** Store all three data types in Spanner.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Firestore is a scalable document database rather than a traditional relational database. It supports indexed queries and transactions, but it does not provide the same relational modeling, join operations, and broad SQL capabilities as Cloud SQL. Structured customer, account, and billing data that requires complex relational queries is therefore better suited to Cloud SQL. Cloud Storage Nearline storage is intended for data accessed approximately once per month or less, so it would cost more to store historical logs that are expected to be retrieved less than once per year than Archive storage. Bigtable is appropriate for the telemetry component because it supports massive datasets and high-throughput, low-latency writes, but the other two service selections prevent this option from being the most cost-effective complete solution.

**B is incorrect** because Cloud SQL is an appropriate service for structured customer data that requires relational schemas, transactions, and complex SQL queries. However, Cloud Storage Coldline storage is generally intended for data accessed no more than approximately once per quarter. Although it can store historical logs economically, Archive storage has a lower storage price and is more appropriate when the logs are expected to be accessed less than once per year. BigQuery can ingest streaming data and is highly effective for serverless analytical queries, but it is primarily an analytical data platform rather than a low-latency operational database optimized for sustained, high-velocity sensor writes. Bigtable is better suited to continuously receiving large volumes of time-series or telemetry records. The combination in this option is therefore not the most cost-effective match for all three requirements.

**C is correct** because each service is matched to the access pattern and technical requirements of its data. Cloud SQL is a fully managed relational database service that supports MySQL, PostgreSQL, and SQL Server. It is suitable for structured customer and billing records that require relational constraints, transactions, indexes, and complex SQL queries. Cloud Storage Archive storage provides the lowest-cost Cloud Storage class for data that is retained for long periods and accessed less than once per year. Archive storage has a 365-day minimum storage duration and higher retrieval and operation charges, but those trade-offs are acceptable for historical logs that are rarely read. Bigtable is a wide-column database designed for terabyte-to-petabyte datasets, low-latency access, and high read and write throughput. It is commonly used for time-series data, Internet of Things telemetry, monitoring information, and other workloads that continuously generate large numbers of records. Sensor data can also be exported or processed by analytical services when deeper analysis is required. This combination meets every storage requirement without paying for capabilities that the individual datasets do not need.

**D is incorrect** because Spanner is designed for mission-critical applications that need relational semantics, horizontal scalability, strong transactional consistency, synchronous replication, and high availability. It could technically hold structured customer records and large quantities of telemetry, but using it for infrequently accessed historical logs would be significantly less economical than Cloud Storage Archive storage. The historical logs do not require relational transactions, strong consistency, or continuously provisioned database compute capacity. Spanner would also provide stronger consistency and availability capabilities than the sensor data requirement demands, especially because the workload can tolerate some telemetry loss. Selecting one premium distributed relational database for every data type ignores the different access patterns and would increase storage and operational costs unnecessarily.

**Reference links**

- [docs.cloud.google.com/sql/docs/introduction](https://docs.cloud.google.com/sql/docs/introduction)
- [docs.cloud.google.com/storage/docs/storage-classes](https://docs.cloud.google.com/storage/docs/storage-classes)
- [docs.cloud.google.com/bigtable/docs/overview](https://docs.cloud.google.com/bigtable/docs/overview)

**Related notes:** [Bigtable](../05-storage-databases-data/products/bigtable.md)

</details>

[Back to index](#index)

---

### Q35

> ClearLedger Services plans to store customer statements and tax documents in Google Cloud for four years. Financial analysts frequently retrieve documents during the first eight months, but older documents are retained only for audits and are rarely accessed. The company wants a Google-managed solution that minimizes storage costs and administrative work. What should ClearLedger Services do?  

- **A.** Store the documents in Cloud Storage and use Object Lifecycle Management to change their storage class to Coldline after eight months.
- **B.** Store the documents in Cloud Storage and use Object Lifecycle Management to change their storage class to Standard after eight months.
- **C.** Initially store the documents in Filestore and manually transfer them to Cloud Storage with the Coldline storage class after eight months.
- **D.** Initially store the documents in Filestore and manually transfer them to Cloud Storage with the Standard storage class after eight months.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Cloud Storage is a fully managed, durable object-storage service that is appropriate for documents such as invoices, statements, and financial records. The documents can initially use Standard storage while analysts access them frequently. Object Lifecycle Management can then automatically change each object to Coldline storage when it reaches the specified age, eliminating the need for administrators to identify and move older documents manually. Coldline is designed for infrequently accessed data that must remain available online, making it more cost-effective than Standard storage for documents retained primarily for audits. Coldline has retrieval charges and a 90-day minimum storage duration, but those conditions are suitable when the documents will remain archived for several years and will rarely be read. To strictly prevent deletion or replacement before the required four-year period expires, ClearLedger Services should also configure and, when appropriate, lock a four-year bucket retention policy. The lifecycle rule controls cost-efficient storage-class transitions, while the retention policy enforces the compliance retention period.

**B is incorrect** because Standard storage is intended for frequently accessed data and has a higher ongoing storage cost than Coldline storage. The documents are already most appropriately stored in Standard storage during the initial period in which analysts retrieve them regularly. Changing them to Standard after eight months would not provide an archival cost benefit and could result in no meaningful storage-class transition at all if they were already stored as Standard objects. Once the documents become rarely accessed and are retained primarily for audits, changing them to a colder storage class is more economical. Object Lifecycle Management is the correct automation mechanism, but Standard is the wrong destination storage class for the stated access pattern.

**C is incorrect** because Filestore is a managed network-attached storage service that provides shared file systems through NFS. It is useful for applications that require file-system semantics, directory structures, shared mounts, and low-latency file access, but those capabilities are unnecessary for storing independent financial documents as archival objects. Starting with Filestore would add file-system capacity planning, instance costs, data-transfer procedures, and operational complexity. The company would also need to create and maintain a process that copies the documents from Filestore to Cloud Storage after eight months and verifies that each transfer completed successfully. Although Coldline is suitable for the older documents, Cloud Storage can store them from the beginning and automatically transition them through Object Lifecycle Management, making Filestore and the manual transfer unnecessary.

**D is incorrect** because it combines an unsuitable initial storage service with an unsuitable archival storage class. Filestore introduces unnecessary expense and management overhead when the documents can be stored directly as objects in Cloud Storage. Moving the documents manually also requires custom scheduling, transfer validation, retry handling, access-control management, and cleanup of the original files. In addition, Standard storage is optimized for frequently accessed objects and does not minimize the cost of retaining documents that are rarely accessed after eight months. Cloud Storage with an automated transition to Coldline provides a simpler and more cost-effective design.

**Reference links**

- [docs.cloud.google.com/storage/docs/lifecycle](https://docs.cloud.google.com/storage/docs/lifecycle)
- [docs.cloud.google.com/storage/docs/storage-classes](https://docs.cloud.google.com/storage/docs/storage-classes)
- [docs.cloud.google.com/storage/docs/bucket-lock](https://docs.cloud.google.com/storage/docs/bucket-lock)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q36

> PixelRaid Studios operates a real-time multiplayer battle game on Google Cloud. Players connect from mobile devices over the public internet, and the game transmits player-position updates to a backend fleet of Compute Engine VMs using UDP on port 32000. The company wants to distribute this UDP traffic across the VMs through one public IP address. What should PixelRaid Studios configure?  

- **A.** Configure an external proxy Network Load Balancer with an SSL proxy in front of the backend VMs.
- **B.** Configure an internal passthrough Network Load Balancer in front of the backend VMs.
- **C.** Configure an external Application Load Balancer in front of the backend VMs.
- **D.** Configure a regional external passthrough Network Load Balancer in front of the backend VMs.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because an external proxy Network Load Balancer using an SSL proxy is intended for TCP traffic protected with SSL or TLS. It terminates the client’s SSL connection at the load-balancing layer and establishes another connection to a selected backend. UDP is a connectionless transport protocol and does not use TCP-based SSL proxy connections, so this load balancer cannot accept and distribute the game’s UDP packets. Although this option provides a single public IP address, its protocol support does not match the application’s requirements.

**B is incorrect** because an internal passthrough Network Load Balancer can distribute UDP traffic, but its frontend uses an internal IP address. It is intended for clients in the same VPC network or clients that can reach the VPC through supported private connectivity, such as Cloud VPN, Cloud Interconnect, or VPC Network Peering under applicable routing conditions. The players are connecting from personal phones over the public internet, so they require a publicly reachable external IP address. An internal load balancer would therefore not expose the game backend directly to those internet clients.

**C is incorrect** because an external Application Load Balancer is a Layer 7 proxy-based load balancer designed for HTTP and HTTPS application traffic. It can route requests by hostname, URL path, headers, and other HTTP-level attributes, but it does not provide a general UDP frontend for arbitrary game packets. Because the mobile game communicates with its backend using UDP rather than HTTP or HTTPS, an external Application Load Balancer cannot handle the required protocol.

**D is correct** because a regional external passthrough Network Load Balancer is a public-facing Layer 4 load balancer that supports UDP traffic. It provides a single external IP address and distributes incoming UDP packets across healthy backend VMs, such as VMs contained in managed or unmanaged instance groups. Because it is a passthrough load balancer, packets are forwarded to the selected backend without terminating a proxy connection, and the original client source IP address is preserved. This makes it suitable for real-time multiplayer game traffic arriving from mobile devices over the internet. PixelRaid Studios should configure an external forwarding rule for the required UDP port, associate it with a regional backend service, add the VM instance groups as backends, and configure an appropriate health check.

**Reference links**

- [docs.cloud.google.com/load-balancing/docs/network/udp-with-network-load-balancing](https://docs.cloud.google.com/load-balancing/docs/network/udp-with-network-load-balancing)
- [docs.cloud.google.com/load-balancing/docs/passthrough-network-load-balancer](https://docs.cloud.google.com/load-balancing/docs/passthrough-network-load-balancer)
- [docs.cloud.google.com/load-balancing/docs/choosing-load-balancer](https://docs.cloud.google.com/load-balancing/docs/choosing-load-balancer)

**Related notes:** [Cloud Load Balancing](../06-networking/products/cloud-load-balancing.md)

</details>

[Back to index](#index)

---

### Q37

> AsterLink operates a customer portal and an order-processing service in separate Google Cloud projects named portal-prod and orders-prod. Logs from both projects are routed to a centralized log bucket in the observability-hub project. The portal development team must be able to view every log entry originating from portal-prod and only entries with ERROR severity originating from orders-prod. The developers must not be able to access any other logs, and AsterLink wants a least-privilege, cost-efficient solution. What should AsterLink do?  

- **A.** In observability-hub, create and share a Logs Explorer query that returns all portal-prod logs and ERROR logs from orders-prod, grant the team the logging.viewer role, and instruct the developers not to modify the query.
- **B.** In observability-hub, create two log sinks that export all portal-prod logs and ERROR logs from orders-prod to the same dedicated Cloud Storage bucket, and grant the team read-only access to that bucket.
- **C.** Grant the portal development team the logging.viewer role on both portal-prod and orders-prod, and instruct the developers to apply a Logs Explorer filter that displays only the required entries.
- **D.** Create a custom log view on the centralized log bucket that includes all entries from portal-prod and only ERROR-severity entries from orders-prod, and grant the team the logging.viewAccessor role only for that log view.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a saved or shared Logs Explorer query controls which logs are displayed by that particular query, but it is not an authorization boundary. Granting the logging.viewer role gives the developers permission to read the logs covered by that role. Team members could modify the shared query, clear its filters, or create a different query and potentially view additional log entries. Asking users not to run another query is an administrative instruction rather than a technical security control, so it does not satisfy the principle of least privilege. Access restrictions must be enforced by IAM and Cloud Logging resources, not merely by the query entered in Logs Explorer.

**B is incorrect** because exporting the selected logs to Cloud Storage could create a separately secured copy, but it introduces an additional destination, duplicate log storage, bucket administration, and potential storage and retrieval charges. Exported Cloud Storage log files are intended primarily for archival or external processing and do not provide the same interactive search and analysis experience as Logs Explorer. Log sinks also route matching entries after the sink is created and do not act as a granular access-control mechanism for the logs already stored in the centralized Cloud Logging bucket. This approach can technically isolate exported data, but it is unnecessarily complex and less cost-efficient than controlling access directly through a log view.

**C is incorrect** because granting logging.viewer on both source projects gives the frontend team broad read access to logs in both projects, subject to the role’s normal limitations. The team would therefore be able to query backend logs that have severities other than ERROR, which directly violates the requirement that no other backend logs be visible. A Logs Explorer filter only narrows the displayed query results; it does not prevent an authorized user from changing or removing that filter. IAM permissions must limit what the developers are authorized to retrieve, rather than relying on instructions about which query to use.

**D is correct** because a log view provides granular access to a defined subset of log entries stored in a Cloud Logging bucket. The custom view can be configured so that its visible dataset consists of all permitted frontend entries and only the permitted backend error entries. The frontend team can then receive roles/logging.viewAccessor specifically on that view, either through the view’s IAM policy or through a conditional IAM binding that restricts access to the view. The developers can run different queries within the authorized view, but they cannot use those queries to retrieve entries excluded by the view. This enforces least privilege at the access-control layer and avoids exporting or duplicating the logs in another storage service, making it the most secure and cost-efficient option.

**Reference links**

- [docs.cloud.google.com/logging/docs/logs-views](https://docs.cloud.google.com/logging/docs/logs-views)
- [docs.cloud.google.com/logging/docs/access-control](https://docs.cloud.google.com/logging/docs/access-control)
- [docs.cloud.google.com/logging/docs/central-log-storage](https://docs.cloud.google.com/logging/docs/central-log-storage)

**Related notes:** [Cloud Logging](../07-operations-cost/products/cloud-logging.md)

</details>

[Back to index](#index)

---

### Q38

> ClipStream Labs operates a video-processing platform that converts thousands of uploaded recordings into multiple formats each night. The conversion pipeline runs across many Compute Engine VMs, saves progress in checkpoints, and continues successfully even when several workers stop unexpectedly. The company wants to reduce the compute cost of this nightly workload. Which action should ClipStream Labs take?  

- **A.** Validate the pipeline by simulating maintenance events, and if it handles VM shutdowns correctly, run future processing jobs on Spot VMs using N2 standard machine types.
- **B.** Validate the pipeline by simulating maintenance events, and if it succeeds, continue running future processing jobs on standard N2 VMs.
- **C.** Validate the pipeline in a managed instance group, and if it succeeds, run future processing jobs on standard N2 VMs in that managed instance group.
- **D.** Validate the pipeline on N1 standard machine types, and if it succeeds, replace the N2 VMs with standard N1 VMs for future processing jobs.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Spot VMs are designed for fault-tolerant workloads that can withstand unexpected VM termination. Compute Engine offers Spot VMs at substantially lower prices than equivalent standard VMs because Google Cloud can reclaim their capacity at any time. A distributed nightly batch-processing pipeline that checkpoints its progress and continues when individual workers disappear is an ideal Spot VM use case. N2 remains the selected machine series, so the application can retain an appropriate CPU and memory configuration while changing the provisioning model from standard to Spot. Simulating maintenance events before migration verifies that the application correctly responds to shutdown signals, preserves intermediate results, reschedules unfinished tasks, and avoids depending on any individual VM. After successful testing, using Spot N2 VMs directly addresses the cost problem while accepting an interruption risk that the workload is already designed to tolerate.

**B is incorrect** because standard N2 VMs do not provide the substantial Spot pricing discount needed to address the primary requirement. Simulating maintenance events is useful for verifying application resilience, but the result of that test is not used effectively in this option. Standard N2 VMs normally provide regular on-demand capacity and are not subject to the same Spot preemption model. Continuing to use standard N2 VMs would therefore leave the workload on the more expensive provisioning model even after proving that the application can tolerate interruptions. The company should take advantage of that fault tolerance by selecting Spot VMs rather than merely validating the workload and retaining its existing standard VMs.

**C is incorrect** because a managed instance group can improve VM management, scalability, automatic repair, and instance recreation, but placing standard N2 VMs in the group does not produce the major cost reduction available from Spot VMs. A managed instance group might be useful as an additional architectural improvement, particularly for automatically recreating terminated Spot VMs or distributing workers across locations and machine types. However, it is not the central cost-saving decision presented in this option because the proposed instances still use standard provisioning. Testing only that the workload functions inside a managed instance group also does not specifically validate how it reacts to preemption and shutdown. The better solution is to test interruption handling and then use the Spot provisioning model; a managed instance group could subsequently be combined with Spot VMs if automated recreation or capacity management is required.

**D is incorrect** because moving from N2 to N1 standard VMs changes the machine series but does not address the workload’s most important cost-optimization opportunity. N1 is an older general-purpose machine series, and changing to it does not automatically make the workload cheaper or more efficient. Actual cost and performance would depend on the selected machine type, resource requirements, execution time, and applicable pricing. More importantly, both choices in this option are standard VMs, so the solution fails to use the workload’s ability to tolerate termination. Spot VMs provide a purpose-built pricing model for interruptible batch jobs and can offer much larger savings than simply switching between standard machine generations.

**Reference links**

- [docs.cloud.google.com/compute/docs/instances/spot](https://docs.cloud.google.com/compute/docs/instances/spot)
- [docs.cloud.google.com/compute/docs/instances/create-use-spot](https://docs.cloud.google.com/compute/docs/instances/create-use-spot)
- [docs.cloud.google.com/compute/docs/instances/simulating-host-maintenance](https://docs.cloud.google.com/compute/docs/instances/simulating-host-maintenance)

**Related notes:** [Spot VMs](../03-compute-containers/products/spot-vms.md)

</details>

[Back to index](#index)

---

### Q39

> PixelForge Media stores a large collection of images, audio recordings, text files, JSON documents, and application logs in an on-premises file system. The company wants to upload these files to Google Cloud and use a Dataflow pipeline to clean, transform, and standardize the data. Where should PixelForge Media upload the files?  

- **A.** Load the files into BigQuery by using the bq command-line tool.
- **B.** Copy the files into Cloud Storage by using the gcloud storage command.
- **C.** Import the files into Cloud SQL by using the import feature in the Google Cloud console.
- **D.** Import the files into Cloud Spanner by using the import feature in the Google Cloud console.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because BigQuery is an analytics data platform designed primarily for structured and semi-structured data that can be represented in tables with defined columns and data types. The bq command-line tool can load supported formats such as CSV, newline-delimited JSON, Avro, ORC, and Parquet into BigQuery tables, but it is not a general-purpose destination for a large collection of arbitrary unstructured files such as images, audio recordings, archives, and miscellaneous documents. Loading data into BigQuery would also require the source data to conform to supported formats and, in many cases, an appropriate table schema. In this scenario, the files must first be made available to a Dataflow ETL pipeline, which can then parse and transform each format as required. Cloud Storage is a more suitable staging and source location for these files.

**B is correct** because Cloud Storage is scalable object storage that can retain large quantities of structured, semi-structured, and unstructured data without requiring the files to be converted into database rows or assigned a relational schema before upload. The company can use commands such as gcloud storage cp, including recursive and parallel copy capabilities, to transfer individual files, directories, or large collections of files into a Cloud Storage bucket. A Dataflow job can then access the objects by using gs:// paths and appropriate Apache Beam I/O connectors. For example, TextIO can read text-based files, AvroIO can read Avro files, and custom pipeline logic or other connectors can process additional formats. Cloud Storage also supports durable storage, high availability, access control through Identity and Access Management, and parallel access by Dataflow workers. This makes it the appropriate landing area for heterogeneous source files that must undergo ETL processing.

**C is incorrect** because Cloud SQL is a managed relational database service for MySQL, PostgreSQL, and SQL Server workloads. Its import functionality is intended for supported database exports or structured files that can be loaded into relational tables. Cloud SQL requires data to fit a database structure consisting of tables, columns, keys, and supported data types. It is not designed to serve as a general repository for a large collection of unrelated unstructured files. Attempting to store these files in database columns or binary fields would add unnecessary schema design, database capacity, operational complexity, and cost. Although Dataflow can interact with relational databases through supported connectors, using Cloud SQL only as a temporary file-staging location would be inefficient compared with placing the original files directly in Cloud Storage.

**D is incorrect** because Cloud Spanner is a distributed relational database intended for transactional applications that require relational consistency, horizontal scalability, and high availability. Data stored in Cloud Spanner must conform to a defined database schema containing tables, columns, primary keys, and supported data types. Its data import mechanisms are intended for structured database records, not arbitrary collections of images, audio files, logs, documents, and other unstructured file formats. Using Cloud Spanner as a staging repository would require unnecessary data modeling and would introduce significantly more complexity than the workload requires. Cloud Spanner is appropriate when an application needs a globally scalable relational database, whereas Cloud Storage is the appropriate service for retaining source files that Dataflow workers need to read and transform.

**Reference links**

- [docs.cloud.google.com/storage/docs/uploading-objects](https://docs.cloud.google.com/storage/docs/uploading-objects)
- [docs.cloud.google.com/storage/docs/working-with-big-data](https://docs.cloud.google.com/storage/docs/working-with-big-data)
- [docs.cloud.google.com/dataflow/docs/guides/read-from-cloud-storage](https://docs.cloud.google.com/dataflow/docs/guides/read-from-cloud-storage)

</details>

[Back to index](#index)

---

### Q40

> BlueHarbor Media operates a release pipeline on Amazon EC2 in an AWS account. The pipeline must push newly built container images to a private Artifact Registry repository in Google Cloud. BlueHarbor Media is prohibited from creating or storing service account keys. The pipeline must use its existing AWS IAM role to obtain temporary Google Cloud credentials and then act as a service account that has permission only to upload images. What should the company configure?  

- **A.** Configure Workforce Identity Federation by using a SAML identity provider
- **B.** Generate a service account key and store it in AWS Secrets Manager
- **C.** Configure Workload Identity Federation with an AWS provider and service account impersonation
- **D.** Allow unauthenticated uploads by making the Artifact Registry repository public

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Workforce Identity Federation is intended for human users, such as employees, administrators, contractors, and partners, who authenticate through an external identity provider. SAML is commonly used to provide these workforce users with single sign-on access to Google Cloud. In this scenario, the identity requesting access is an automated deployment pipeline running in AWS rather than a human user. Therefore, a workforce identity pool and SAML provider would use the wrong federation model. The pipeline requires Workload Identity Federation, which is specifically designed for applications and automated workloads operating outside Google Cloud.

**B is incorrect** because generating a service account key directly violates the stated security policy. A service account key is a long-lived credential that must be stored, distributed, protected, monitored, and periodically rotated. Storing the key in AWS Secrets Manager would provide better protection than embedding it in pipeline code, but it would not eliminate the risks associated with possessing a persistent credential. Anyone who retrieves the key could use it until the key is disabled or deleted. Workload Identity Federation avoids this problem by exchanging the workload’s AWS identity for short-lived Google Cloud credentials, so no service account private key needs to be created or stored.

**C is correct** because Workload Identity Federation supports workloads running in external environments, including AWS. BlueHarbor Media can create a workload identity pool, add an AWS provider, and configure attribute mappings and conditions that recognize only the approved AWS account, IAM role, or other AWS identity attributes. When the deployment pipeline runs, it uses its existing AWS IAM role credentials to prove its identity to Google Cloud’s Security Token Service. Google Cloud then exchanges that external identity for short-lived federated credentials. The federated principal can be granted the Workload Identity User role on a narrowly scoped Google Cloud service account, allowing the pipeline to impersonate that service account without possessing its private key. The service account should receive only the Artifact Registry permissions required to push images, such as the Artifact Registry Writer role on the specific repository. This design provides temporary credentials, avoids long-lived keys, restricts access through both federation conditions and IAM roles, and supports auditing of the external principal and impersonated service account.

**D is incorrect** because making an Artifact Registry repository public does not create a secure mechanism for publishing images. Public access is normally associated with allowing unauthenticated users to download artifacts, not granting unrestricted unauthenticated permission to upload or modify repository contents. Allowing anonymous write access would create a serious supply-chain security risk because unauthorized parties could add, replace, or poison container images. It would also fail to satisfy the requirement to exchange the AWS identity for short-lived Google Cloud credentials and impersonate a narrowly scoped service account. The repository should remain private, and uploads should be authorized through IAM.

**Reference links**

- [docs.cloud.google.com/iam/docs/workload-identity-federation-with-other-clouds](https://docs.cloud.google.com/iam/docs/workload-identity-federation-with-other-clouds)
- [docs.cloud.google.com/iam/docs/workload-identity-federation](https://docs.cloud.google.com/iam/docs/workload-identity-federation)
- [docs.cloud.google.com/artifact-registry/docs/access-control](https://docs.cloud.google.com/artifact-registry/docs/access-control)

**Related notes:** [Workload Identity Federation and Workforce Identity Federation](../02-identity-security/products/workload-identity-federation-and-workforce-identity-federati.md)

</details>

[Back to index](#index)

---

### Q41

> Northbridge Advisory needs to provide 32 independent compliance reviewers with temporary, read-only access to several Google Cloud projects. The reviewers already have individual identities in Northbridge Advisory’s external identity provider. The Google Cloud organization does not want to provision Cloud Identity accounts, and every reviewer’s activity must be individually attributable in audit logs. What should the organization configure?  

- **A.** Grant the Viewer role to one shared service account used by all reviewers
- **B.** Configure Workforce Identity Federation with Northbridge Advisory’s external identity provider
- **C.** Configure Workload Identity Federation separately on every reviewer’s computer
- **D.** Create one Google account and share its credentials among all reviewers

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because a service account represents a non-human workload or application rather than an individual workforce user. Although granting the Viewer role to a service account could technically provide read-only access, allowing all reviewers to use the same service account would cause their actions to appear under a common identity. This would make it difficult to determine which individual performed a specific action and would weaken accountability. Sharing service account credentials also creates credential-management and security risks. Service accounts should normally be used by applications and automated workloads, not as shared login identities for human users.

**B is correct** because Workforce Identity Federation is designed to provide employees, contractors, partners, auditors, and other human users with access to Google Cloud by using identities from an external identity provider. The organization can create a workforce identity pool, configure an OIDC or SAML provider, map identity-provider claims to Google Cloud attributes, and grant the required IAM role to selected federated users or groups. Each reviewer continues to authenticate through the company’s existing identity provider, so Cloud Identity accounts do not need to be created. Because each reviewer signs in with an individual federated identity, Google Cloud can associate access and audit-log entries with that reviewer. The organization can grant the Viewer role only on the selected projects and remove the IAM bindings, disable the provider, or change external group membership when the temporary audit engagement ends.

**C is incorrect** because Workload Identity Federation is intended primarily for non-human workloads running outside Google Cloud, such as applications operating in AWS, Azure, on-premises environments, or deployment pipelines. It allows those workloads to obtain short-lived Google Cloud credentials without storing service account keys. An auditor using a workstation is a human workforce identity, so Workforce Identity Federation is the appropriate service. Configuring Workload Identity Federation separately on each workstation would incorrectly treat the computers or their applications as the principals and would add unnecessary administrative complexity without providing the intended user sign-in experience.

**D is incorrect** because sharing one Google account prevents reliable attribution of actions to individual reviewers. Google Cloud audit records would identify the shared account rather than the person who used it, which would not satisfy the traceability requirement. Shared credentials also make password management, multifactor authentication, access revocation, and incident investigation more difficult. When one reviewer leaves the engagement, the organization would need to rotate the shared credentials for everyone. Individual federated identities provide stronger accountability and allow access to be revoked for one reviewer without disrupting the rest of the audit team.

**Reference links**

- [docs.cloud.google.com/iam/docs/workforce-identity-federation](https://docs.cloud.google.com/iam/docs/workforce-identity-federation)
- [docs.cloud.google.com/iam/docs/configuring-workforce-identity-federation](https://docs.cloud.google.com/iam/docs/configuring-workforce-identity-federation)
- [docs.cloud.google.com/iam/docs/workload-identity-federation](https://docs.cloud.google.com/iam/docs/workload-identity-federation)

**Related notes:** [Workload Identity Federation and Workforce Identity Federation](../02-identity-security/products/workload-identity-federation-and-workforce-identity-federati.md)

</details>

[Back to index](#index)

---

### Q42

> AuroraMart stores customer purchase and product data in a BigQuery dataset within its Google Cloud project. InsightForge, an external analytics partner, operates a product-personalization service using resources in its own Google Cloud project. The service needs read access to AuroraMart’s BigQuery dataset. AuroraMart wants the partner to manage its own workload identity while granting access only to the required dataset. What should AuroraMart do?  

- **A.** Create a service account in AuroraMart’s project and grant it access to the BigQuery dataset in AuroraMart’s project.
- **B.** Create a service account in AuroraMart’s project and ask InsightForge to grant it access to BigQuery resources in InsightForge’s project.
- **C.** Ask InsightForge to create a service account in its project and grant that service account access to BigQuery resources in InsightForge’s project.
- **D.** Ask InsightForge to create a service account in its project and grant that service account access to the BigQuery dataset in AuroraMart’s project.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because although a service account created in AuroraMart’s project can be granted access to AuroraMart’s BigQuery dataset, the service account would be owned and managed by AuroraMart rather than by the partner operating the workload. InsightForge’s application could not automatically use that service account merely because it has dataset access. AuroraMart would also need to configure cross-project service account usage, grant the partner permission to impersonate the service account, or distribute service account credentials, which introduces unnecessary administrative and security complexity. It is preferable for a workload identity to be managed by the organization that owns and operates the workload. The partner should therefore create and control the service account used by its recommendation application.

**B is incorrect** because this option grants the service account permissions in InsightForge’s project but does not grant it access to AuroraMart’s BigQuery dataset. BigQuery access is determined by the IAM policy applied to the project, dataset, table, view, or other relevant resource that contains the data. Permissions in the partner’s project do not automatically provide access to data stored in AuroraMart’s project. The service account would still receive an access-denied response when attempting to read the dataset unless AuroraMart explicitly grants it the required dataset-level role.

**C is incorrect** because creating the service account in InsightForge’s project is the correct ownership model, but granting it access only to BigQuery resources in that same project does not authorize access to AuroraMart’s dataset. InsightForge might grant the service account the BigQuery Job User role in its own project so that it can create and run query jobs billed to that project. However, this permission does not include permission to read data from a dataset in another project. AuroraMart must separately add the partner’s service account as a principal on the relevant dataset and grant an appropriate role, such as BigQuery Data Viewer.

**D is correct** because InsightForge should create and manage the service account used by its own recommendation application. AuroraMart can then add that service account’s email address as a principal on the required BigQuery dataset and grant the least-privileged dataset-level role needed by the application. For read-only access, AuroraMart would typically grant the BigQuery Data Viewer role on the dataset. This allows the service account to read tables and views in that dataset without granting access to unrelated datasets or broader resources in AuroraMart’s project. InsightForge should normally grant the service account the BigQuery Job User role in its own project so that the application can create query jobs and charge query-processing costs to the partner’s project. This design separates responsibilities correctly: InsightForge manages the workload identity and query execution environment, while AuroraMart controls access to its own data.

**Reference links**

- [docs.cloud.google.com/iam/docs/service-account-overview](https://docs.cloud.google.com/iam/docs/service-account-overview)
- [docs.cloud.google.com/bigquery/docs/control-access-to-resources-iam](https://docs.cloud.google.com/bigquery/docs/control-access-to-resources-iam)
- [docs.cloud.google.com/bigquery/docs/access-control](https://docs.cloud.google.com/bigquery/docs/access-control)

</details>

[Back to index](#index)

---

### Q43

> NovaCast, a video-streaming company, notices a sharp increase in network charges between workloads running in asia-south1 and europe-west4. The network operations team must analyze the highest-volume senders and receivers, determine the source and destination regions, and review traffic trends from the previous six weeks. The team needs connection metadata and transferred-byte counts, but it does not need packet contents. What should the team configure?  

- **A.** Run continuous packet captures on every Compute Engine VM and store the capture files on each VM’s local disk.
- **B.** Rely exclusively on Cloud Audit Logs that record Compute Engine API operations.
- **C.** Enable VPC Flow Logs with appropriate sampling and metadata settings, and retain or route the logs to a suitable destination for analysis.
- **D.** Configure Cloud DNS response policies for the application domains.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because continuous packet capture is substantially more detailed, operationally complex, and storage-intensive than the requirement demands. Packet captures can include packet headers and payload data, potentially exposing sensitive application information and creating significant storage, security, and processing overhead. Saving captures to VM local disks also makes centralized analysis difficult and risks losing evidence when a VM is deleted, recreated, or becomes unavailable. Packet capture can be useful for short-term, low-level protocol troubleshooting, but it is not the appropriate default solution for identifying top talkers and analyzing regional traffic volumes over several weeks when packet payloads are unnecessary.

**B is incorrect** because Cloud Audit Logs for Compute Engine primarily record administrative and API activity, such as creating a VM, changing a firewall rule, or modifying a network resource. They do not provide a continuous record of the network connections between workloads or the number of bytes and packets exchanged by source and destination. Consequently, Compute Engine audit logs cannot reliably identify high-volume network talkers, calculate inter-region traffic patterns, or explain sustained data-transfer charges.

**C is correct** because VPC Flow Logs generate sampled and aggregated network-flow records without capturing complete packet payloads. The records describe connections by characteristics such as source and destination IP addresses, source and destination ports, protocol, byte counts, packet counts, timestamps, and available resource metadata. Metadata can help associate traffic with resources and locations, enabling the team to group flows by source region, destination region, VM, subnet, project, or other relevant dimensions. The team can tune the aggregation interval, secondary flow-sampling rate, metadata inclusion, and filtering settings to balance visibility, log volume, and cost. It can retain the records in a Cloud Logging log bucket for the required investigation period or route them through a Cloud Logging sink to a destination such as BigQuery for long-term aggregation and trend analysis. Flow Analyzer or Log Analytics can also analyze retained VPC Flow Logs to identify top senders, top receivers, traffic volumes, and communication patterns. This directly supports investigating inter-region data-transfer charges without collecting packet contents.

**D is incorrect** because Cloud DNS response policies control how selected DNS queries are answered. They can override DNS responses, block domain resolution, or direct clients toward designated endpoints, but they do not collect network-flow telemetry. A DNS response policy cannot report how many bytes were transferred between regions, identify the highest-volume source and destination resources, or show traffic trends over several weeks. DNS query information might provide limited insight into hostname lookups, but it is not a substitute for VPC Flow Logs.

**Reference links**

- [docs.cloud.google.com/vpc/docs/flow-logs](https://docs.cloud.google.com/vpc/docs/flow-logs)
- [docs.cloud.google.com/vpc/docs/using-flow-logs](https://docs.cloud.google.com/vpc/docs/using-flow-logs)
- [docs.cloud.google.com/network-intelligence-center/docs/flow-analyzer/overview](https://docs.cloud.google.com/network-intelligence-center/docs/flow-analyzer/overview)

**Related notes:** [Firewall Rules Logging and VPC Flow Logs](../06-networking/products/firewall-rules-logging-and-vpc-flow-logs.md)

</details>

[Back to index](#index)

---

### Q44

> NovaCart Analytics is building an application that will run on Google Cloud and use a dedicated service account to read sales data from BigQuery. Before deploying the application, a developer needs to verify from a local workstation that the service account has the required BigQuery permissions. NovaCart wants to avoid long-lived credentials and follow Google-recommended security practices. What should the developer do?  

- **A.** Create and download a service account key, activate the key with the gcloud CLI, and run a relevant BigQuery command.
- **B.** Grant the service account the BigQuery Administrator IAM role so that it can perform any BigQuery operation.
- **C.** Configure the gcloud CLI to impersonate the service account, and run a relevant BigQuery command using the impersonated identity.
- **D.** Configure Application Default Credentials with the developer’s user account, and run a relevant BigQuery command through the gcloud CLI.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because downloading a service account key creates a long-lived credential that must be securely stored, protected, rotated, and eventually deleted. Anyone who obtains the key can authenticate as the service account without first proving another identity, and the key remains usable until it expires, is disabled, or is deleted. Google recommends avoiding service account keys whenever a more secure alternative such as service account impersonation is available. Although activating the key in the gcloud CLI would allow the developer to test the service account’s BigQuery permissions, it introduces an unnecessary persistent credential and therefore is not the most secure approach.

**B is incorrect** because the BigQuery Administrator role grants extensive permissions to manage BigQuery resources and data. Granting this broad role merely to ensure that a read operation succeeds violates the principle of least privilege and can give the application permissions that it does not need. The service account should instead receive only the roles required for its workload, such as an appropriate BigQuery data access role on the relevant dataset and any additional permission required to create query jobs. Furthermore, granting a role does not test whether local authentication as the service account works; the developer must execute a representative request using the service account’s identity.

**C is correct** because service account impersonation allows the developer to run gcloud CLI commands using short-lived credentials generated for the service account without creating or downloading a service account key. The developer first authenticates with an authorized user identity and must have permission to impersonate the target service account, typically through the Service Account Token Creator role or another role containing the iam.serviceAccounts.getAccessToken permission. The developer can configure the auth/impersonate_service_account property or use the --impersonate-service-account flag on the relevant command. The gcloud CLI then obtains temporary credentials and submits the BigQuery request as the service account, accurately testing the permissions that the deployed application will have. This approach reduces credential exposure, supports auditing of the initiating user and impersonated service account, and follows Google-recommended practices.

**D is incorrect** because configuring Application Default Credentials with the developer’s user account causes supported applications and client libraries to authenticate as that user, not as the application’s service account. A successful BigQuery request would therefore confirm the developer’s permissions rather than the service account’s permissions and would not prove that the deployed application can retrieve the required data. Application Default Credentials are also separate from the credentials normally used directly by gcloud CLI commands. ADC can be configured to use service account impersonation, but the option explicitly uses the user account, so it does not satisfy the requirement to test the target service account.

**Reference links**

- [docs.cloud.google.com/docs/authentication/use-service-account-impersonation](https://docs.cloud.google.com/docs/authentication/use-service-account-impersonation)
- [docs.cloud.google.com/iam/docs/service-account-impersonation](https://docs.cloud.google.com/iam/docs/service-account-impersonation)
- [docs.cloud.google.com/bigquery/docs/access-control](https://docs.cloud.google.com/bigquery/docs/access-control)

**Related notes:** [Service account impersonation](../02-identity-security/products/service-account-impersonation.md)

</details>

[Back to index](#index)

---

### Q45

> Evergreen Tickets is moving its reservation database and stateless booking service to a Standard Google Kubernetes Engine (GKE) cluster. The database must retain its data when Pods are restarted or rescheduled, and the cluster must automatically add or remove nodes as the booking workload changes. The company wants to minimize manual administration and follow Google-recommended practices. What should Evergreen Tickets do?  

- **A.** -Run the database as a StatefulSet with persistent storage.  
  -Enable cluster autoscaling to adjust the number of nodes according to workload demand.
- **B.** -Run the database as an individual Pod.  
  -Manually resize the cluster whenever the workload demand changes.
- **C.** -Run the database as a DaemonSet.  
  -Manually resize the cluster whenever the workload demand changes.
- **D.** -Run the database as a Deployment with persistent storage.  
  -Enable cluster autoscaling to adjust the number of nodes according to workload demand.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a StatefulSet is designed for applications that maintain state, such as databases. It provides each database Pod with a stable identity, predictable naming, ordered deployment behavior, and a consistent association with its PersistentVolumeClaim. Data stored in a PersistentVolume has a lifecycle independent of an individual Pod, so the data can remain available when a database Pod is restarted, replaced, or scheduled onto another node. The database must still be correctly configured for replication, backups, recovery, and application-level consistency because a StatefulSet alone does not guarantee protection from every cause of data loss. Enabling GKE cluster autoscaling addresses the backend capacity requirement by automatically increasing the number of nodes when Pods cannot be scheduled because of insufficient resources and reducing the number of nodes when capacity is no longer required. This combination provides the appropriate Kubernetes controller for the stateful database and managed node scaling for changing workload demand, minimizing manual work.

**B is incorrect** because a standalone Pod does not provide the workload-management guarantees needed for a database. If the Pod is deleted, fails, or is disrupted during maintenance, Kubernetes does not have a higher-level controller responsible for restoring it to a declared desired state. Persistent storage could technically be attached to an individual Pod, but the design would still lack StatefulSet features such as stable Pod identities, ordered operations, and consistent per-replica storage associations. Manually running a resize command after noticing demand changes is also reactive and operationally inefficient. It can leave backend Pods pending while administrators detect the shortage and add nodes, and it can waste resources when demand falls. GKE cluster autoscaling should be used to automate these node-capacity adjustments.

**C is incorrect** because a DaemonSet is intended to run one copy of a Pod on every selected node, or on every node that matches specified scheduling constraints. It is commonly used for node-level components such as log collectors, monitoring agents, networking components, and storage agents. A database normally should not create an independent replica automatically on every cluster node because adding or removing nodes would also add or remove database Pods without regard to the database’s replication topology, quorum requirements, or storage relationships. A DaemonSet also does not provide the stable per-replica identities and ordered lifecycle management offered by a StatefulSet. Manually resizing the cluster further increases administrative effort and does not respond promptly to workload changes.

**D is incorrect** because a Deployment is primarily designed for stateless workloads whose Pods are interchangeable. Deployments are appropriate for the booking backend because backend replicas can usually be replaced or distributed across nodes without retaining unique identities. However, a database often requires stable network identities, persistent storage consistently associated with specific replicas, and controlled ordering during deployment, scaling, and updates. A StatefulSet provides these capabilities, whereas a Deployment treats replacement Pods as equivalent and does not maintain StatefulSet-style identity and storage guarantees. Cluster autoscaling is the correct method for automatically adjusting node capacity, but pairing it with an inappropriate controller for the database makes this option incorrect.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/how-to/stateful-apps](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/stateful-apps)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler)
- [kubernetes.io/docs/concepts/workloads/controllers/statefulset](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q46

> Northwind Analytics stores confidential customer reports in several Cloud Storage buckets. A compliance reviewer needs to determine which identities have read, created, updated, or deleted objects in selected buckets. You need to provide the reviewer with the required audit information. What should you do?  

- **A.** Enable Data Access audit logs for Cloud Storage, and create a Logs Explorer query that filters the audit logs for the relevant Cloud Storage buckets.
- **B.** Grant the reviewer reporting permissions, and create a Looker Studio report based only on Admin Activity audit logs.
- **C.** Grant the reviewer access to Cloud Monitoring, and ask them to examine Cloud Storage usage metrics.
- **D.** Export Admin Activity audit logs through the Cloud Logging API in the reviewer’s preferred file format.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Cloud Storage Data Access audit logs record operations that access or modify user-provided data, including object reads, object creation, updates, deletions, and applicable metadata reads. These records contain useful audit fields such as the authenticated principal, operation performed, resource name, timestamp, source information, and status. Data Access audit logs are generally disabled by default for most Google Cloud services, so the organization must explicitly enable the relevant DATA_READ, DATA_WRITE, and, when required, ADMIN_READ categories for Cloud Storage. The auditor can then use Logs Explorer to filter entries by the Cloud Storage service name, audit-log type, bucket resource name, principal, method, or time range. Because Data Access audit logs are treated as private logs, the auditor also needs an appropriate role, such as Private Logs Viewer, or equivalent custom permissions to read them.

**B is incorrect** because Admin Activity audit logs primarily record administrative operations that change the configuration or metadata of Google Cloud resources. For example, they can show activities such as changing a bucket’s IAM policy or modifying certain bucket settings, but they are not the correct source for determining who downloaded, viewed, uploaded, or deleted stored objects. Looker Studio can visualize data from supported data sources, but creating a report from Admin Activity audit logs does not compensate for the absence of the required Data Access events. The organization must first enable and query Cloud Storage Data Access audit logs.

**C is incorrect** because Cloud Monitoring provides aggregated metrics that describe system behavior, resource utilization, request rates, error counts, latency, storage consumption, and similar operational measurements. Metrics can indicate that Cloud Storage requests occurred, but they do not normally provide the detailed, identity-specific audit trail needed to determine who accessed a particular object. Cloud Monitoring is useful for performance and availability monitoring, whereas Cloud Audit Logs and Logs Explorer are the appropriate services for access auditing.

**D is incorrect** because Admin Activity audit logs do not contain the complete object-level data-access history required by the reviewer. Exporting those logs in a different format would only change how the existing records are delivered; it would not add missing DATA_READ or DATA_WRITE events. Cloud Logging can route logs to destinations such as BigQuery, Cloud Storage, or Pub/Sub, but the relevant Data Access audit logs must first be enabled and collected. Exporting logs can support long-term retention or external analysis, but it is not a substitute for enabling the correct audit-log category.

**Reference links**

- [docs.cloud.google.com/storage/docs/audit-logging](https://docs.cloud.google.com/storage/docs/audit-logging)
- [docs.cloud.google.com/logging/docs/audit/configure-data-access](https://docs.cloud.google.com/logging/docs/audit/configure-data-access)
- [docs.cloud.google.com/logging/docs/view/logs-explorer-interface](https://docs.cloud.google.com/logging/docs/view/logs-explorer-interface)

**Related notes:** [Cloud Audit Logs](../02-identity-security/products/cloud-audit-logs.md)

</details>

[Back to index](#index)

---

### Q47

> BrightCart, an online retail platform, experiences simultaneous failures across multiple resources in its production project. Cloud Monitoring metrics did not show increasing latency, resource exhaustion, or another gradual application-level problem before the failures began. The site reliability engineering team suspects an underlying Google Cloud service disruption and needs the primary project-specific source for the incident’s status, affected Google Cloud products and locations, ongoing updates, and any available workarounds. What should the team review?  

- **A.** Status pages for unrelated third-party SaaS providers
- **B.** IAM role recommendations for project members
- **C.** Cloud Storage inventory reports for the production project
- **D.** Personalized Service Health for the production project

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because status pages for unrelated third-party SaaS providers describe incidents affecting those providers, not Google Cloud services used by the production project. They cannot determine whether a Google Cloud disruption is relevant to BrightCart’s resources, identify affected Google Cloud products or locations, or provide authoritative updates and workarounds from Google Cloud. External status pages might be useful when an application depends directly on those vendors, but they are not the primary source for investigating a suspected Google Cloud service disruption.

**B is incorrect** because IAM role recommendations help administrators reduce excessive permissions and improve least-privilege access. They analyze permission usage and may suggest removing or replacing IAM roles, but they do not report Google Cloud service outages, degradation, incident relevance, affected locations, estimated recovery information, or published workarounds. Reviewing IAM recommendations would be appropriate for an access-governance task, not for determining whether multiple resource failures were caused by a Google Cloud service incident.

**C is incorrect** because Cloud Storage inventory reports provide periodic metadata about objects in Cloud Storage buckets, such as object names, sizes, storage classes, creation times, and other object attributes. They are useful for storage analysis, compliance, and lifecycle planning, but they do not provide operational status for Google Cloud products. An inventory report cannot show whether a service disruption is affecting the project, which regions are involved, how an incident is progressing, or what mitigation guidance Google Cloud has published.

**D is correct** because Personalized Service Health is the primary source for service disruptions relevant to a specific Google Cloud project. It provides a personalized view of incidents that might be related to or verified as impacting the project instead of showing only broad public incident information. The team can review the incident state, affected Google Cloud products and locations, descriptions of the impact, chronological updates, relevance to the selected project, and available workarounds or mitigation guidance. This is especially useful when failures begin suddenly without a preceding deterioration in application metrics, because the underlying cause might be a platform-level outage or degradation rather than a capacity or application problem. The public Google Cloud Service Health dashboard can serve as a broader or fallback source, but Personalized Service Health is the appropriate primary project-specific source.

**Reference links**

- [docs.cloud.google.com/service-health/docs/overview](https://docs.cloud.google.com/service-health/docs/overview)
- [docs.cloud.google.com/service-health/docs/view-events](https://docs.cloud.google.com/service-health/docs/view-events)
- [docs.cloud.google.com/service-health/docs/incident-communication](https://docs.cloud.google.com/service-health/docs/incident-communication)

**Related notes:** [Personalized Service Health](../07-operations-cost/products/personalized-service-health.md)

</details>

[Back to index](#index)

---

### Q48

> NimbusRetail operates a private order-processing API on Cloud Run. A newly created service account will be used by another workload to invoke this API. You need permissions to manage the IAM policy attached to the service account, and you must follow the principle of least privilege. Which role should you request for your user account?  

- **A.** Request the roles/iam.serviceAccountAdmin role for your user account.
- **B.** Request the roles/run.invoker role for your user account.
- **C.** Request the Editor basic role for your user account.
- **D.** Request the Owner basic role for your user account.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the Service Account Admin role, roles/iam.serviceAccountAdmin, is specifically intended for creating and managing service accounts and managing access to them. It includes permissions such as iam.serviceAccounts.getIamPolicy and iam.serviceAccounts.setIamPolicy, which allow a user to retrieve and modify the IAM policy attached to a service account. Because this role is focused on service-account administration, it is narrower and better aligned with the stated requirement than broad project-level basic roles. After the necessary identities and permissions are configured, the calling service account must be granted roles/run.invoker on the receiving Cloud Run service so that it can send authenticated requests. It is important to distinguish between managing access to the service account itself and granting the service account access to another resource: a service account IAM policy controls who can use or administer that service account, while the Cloud Run service’s IAM policy controls who can invoke the Cloud Run service.

**B is incorrect** because roles/run.invoker grants its principal permission to invoke Cloud Run services and, depending on the applicable Cloud Run resource type, perform supported invocation operations. Assigning this role to your user account would allow your user identity to invoke the service, but it would not grant permissions such as iam.serviceAccounts.setIamPolicy for modifying a service account’s IAM policy. The Cloud Run Invoker role should instead be granted to the new service account on the target Cloud Run service when that service account is the identity that needs to make requests. It is a runtime access role, not an IAM administration role.

**C is incorrect** because Editor is a broad basic role that provides permissions to create and modify many Google Cloud resources across a project. It grants substantially more access than is required for the narrow task of administering service accounts and therefore does not follow the principle of least privilege. Basic roles are not recommended when a more targeted predefined role satisfies the requirement. Additionally, the Editor role does not generally provide unrestricted permission to change IAM allow policies, because access-policy management is intentionally separated from ordinary resource editing. Requesting Service Account Admin is more precise and avoids unnecessary access to unrelated services and resources.

**D is incorrect** because Owner is one of the most privileged basic roles in Google Cloud. It provides broad administrative control over project resources and IAM policies and can be used to manage access for many unrelated identities and services. Although an Owner could perform many of the required administrative operations, granting Owner solely to manage service-account policies would create excessive privileges and a much larger security impact if the user account were compromised or misused. The principle of least privilege requires selecting the narrowest role that supplies the necessary service-account management permissions, which is roles/iam.serviceAccountAdmin among the available choices.

**Reference links**

- [docs.cloud.google.com/iam/docs/manage-access-service-accounts](https://docs.cloud.google.com/iam/docs/manage-access-service-accounts)
- [docs.cloud.google.com/iam/docs/roles-permissions/iam](https://docs.cloud.google.com/iam/docs/roles-permissions/iam)
- [docs.cloud.google.com/run/docs/authenticating/service-to-service](https://docs.cloud.google.com/run/docs/authenticating/service-to-service)

</details>

[Back to index](#index)

---

### Q49

> Northbridge Design Group is moving its Windows-based CAD document repository to Google Cloud. Employees and engineering applications must continue accessing shared files over SMB, and the storage platform must provide enterprise features such as snapshots, replication, backup, and access controls. The workload requires reliable managed file storage but not the massive parallel throughput used for large AI or HPC workloads. Which storage option should Northbridge Design Group choose?  

- **A.** Google Cloud NetApp Volumes
- **B.** Google Cloud Managed Lustre
- **C.** Bigtable
- **D.** Local SSD attached to a single Compute Engine VM

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Google Cloud NetApp Volumes is a fully managed enterprise file-storage service designed for workloads that need familiar network-attached storage capabilities. It supports SMB for Windows applications and can integrate with Microsoft Active Directory for domain-based authentication and authorization. It also provides mature data-management capabilities such as snapshots, backups, volume replication, cloning, configurable performance levels, and centralized volume administration. These capabilities allow the company to migrate its Windows engineering file share without redesigning the application around an object-storage or database interface. Because the workload needs managed SMB storage and enterprise file-management features rather than extreme parallel I/O, Google Cloud NetApp Volumes is the most appropriate option.

**B is incorrect** because Google Cloud Managed Lustre is a fully managed, high-performance parallel file system primarily optimized for tightly coupled AI, machine learning, high-performance computing, and technical computing workloads. It is designed to provide very high aggregate throughput and low-latency POSIX file access to large numbers of Linux-based compute clients. Selecting it solely because it offers higher throughput would ignore the application’s actual protocol and management requirements. The engineering application requires SMB for Windows file sharing, while Managed Lustre is based on the Lustre parallel file-system architecture and is not the appropriate replacement for an enterprise SMB share. Higher maximum throughput does not make a storage service suitable when it lacks the required client protocol and file-management model.

**C is incorrect** because Bigtable is a managed wide-column NoSQL database rather than a network file-storage service. Applications interact with Bigtable through database APIs and organize information as rows, column families, and cells. Bigtable does not expose an SMB file share, provide a conventional hierarchical file-system namespace, or allow Windows applications to open engineering files through standard shared-folder paths. Migrating the files into Bigtable would require substantial application redesign and would not preserve the file-sharing behavior required by the existing application.

**D is incorrect** because Local SSD provides temporary block storage physically attached to an individual Compute Engine host. It does not offer a managed SMB file service, shared access across multiple client systems, enterprise snapshots, cross-region replication, or durable network-attached storage. Data on Local SSD can be lost when the VM is stopped or when certain host events occur, making it unsuitable as the authoritative repository for business-critical engineering documents. Hosting an SMB server manually on one VM would also create administrative overhead and a potential single point of failure, contrary to the requirement for a managed enterprise storage solution.

**Reference links**

- [docs.cloud.google.com/netapp/volumes/docs/discover/overview](https://docs.cloud.google.com/netapp/volumes/docs/discover/overview)
- [docs.cloud.google.com/netapp/volumes/docs/discover/features](https://docs.cloud.google.com/netapp/volumes/docs/discover/features)
- [docs.cloud.google.com/netapp/volumes/docs/connect-clients/connect-smb-clients](https://docs.cloud.google.com/netapp/volumes/docs/connect-clients/connect-smb-clients)

**Related notes:** [Google Cloud Managed Lustre](../05-storage-databases-data/products/google-cloud-managed-lustre.md) · [Google Cloud NetApp Volumes](../05-storage-databases-data/products/google-cloud-netapp-volumes.md)

</details>

[Back to index](#index)

---

### Q50

> BluePeak Analytics has several Google Cloud projects that an engineer originally linked to a personal Cloud Billing account backed by the engineer’s credit card. The company now has a corporate Cloud Billing account that is paid through a monthly invoice. BluePeak wants all future usage charges from these projects to appear on the company’s invoice instead of the engineer’s credit card. What should the engineer do?  

- **A.** Grant the finance team the Billing Account User IAM role on the engineer’s personal Cloud Billing account.
- **B.** Enable Cloud Billing export to BigQuery and allow the finance team to query the exported billing data.
- **C.** Contact Cloud Billing Support and request that the personal account’s charges be added to the company’s monthly invoice.
- **D.** Change the Cloud Billing account linked to each project from the personal Cloud Billing account to the company’s corporate Cloud Billing account.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because the Billing Account User role allows a principal to link projects to the Cloud Billing account on which the role is granted. Granting this role to the finance team on the engineer’s personal Cloud Billing account would not change which account pays for the existing projects. The projects would remain linked to the personal account, so future usage would continue to be charged through the personal account’s payment method. This role also does not convert a self-serve credit-card account into the company’s invoiced account or transfer project charges to another Cloud Billing account. Access should instead be granted as needed on the company’s target Cloud Billing account, and the projects should be linked to that account.

**B is incorrect** because Cloud Billing export sends detailed usage, cost, pricing, and related billing information to BigQuery for reporting and analysis. Giving the finance team access to this data would help them monitor expenditure, allocate costs, build dashboards, or reconcile charges. However, billing export does not change the Cloud Billing account linked to a project, the payment method used for the charges, or the invoice on which the charges appear. The engineer’s personal account would continue paying for project usage even though the company could analyze the exported data.

**C is incorrect** because contacting Cloud Billing Support does not replace the standard process for changing the Cloud Billing account associated with a project. Google Cloud determines who pays for project usage according to the active Cloud Billing account linked to that project. Support cannot simply redirect future project charges to an unrelated company invoice while the projects remain linked to the personal billing account. Charges already incurred before a billing-account change remain associated with the original account, while charges incurred after the change are assigned to the new account. The appropriate action is therefore to update the projects’ billing-account associations directly.

**D is correct** because a Cloud Billing account defines who pays for the usage generated by the projects linked to it. By changing each project’s billing association from the engineer’s personal account to the company’s corporate Cloud Billing account, future project usage will accrue on the corporate account and be included in its billing process, including its monthly invoice when invoiced billing is configured. The person performing the change must have sufficient permissions on the projects and relevant billing accounts. Typically, this includes permissions to unlink the projects from the current account and link them to the target company account. The Billing Account User role on the target account provides permission to link projects, while suitable project-level permissions, such as those provided by Project Billing Manager or Project Owner, are also required. Costs incurred before the change remain billed to the personal account; the new corporate account is responsible for eligible usage incurred after the association is changed.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/modify-project](https://docs.cloud.google.com/billing/docs/how-to/modify-project)
- [docs.cloud.google.com/billing/docs/how-to/billing-access](https://docs.cloud.google.com/billing/docs/how-to/billing-access)
- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery)

**Related notes:** [Cloud Billing](../07-operations-cost/products/cloud-billing.md)

</details>

[Back to index](#index)

---
