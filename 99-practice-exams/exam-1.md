# Practice Exam 1

[All exams](README.md) · [Next](exam-2.md)

50 questions in the original English. Open "Show answer" under each question to see the correct answer and the explanation.

## Index

| Q | Question |
|---|---|
| [Q1](#q1) | PixelHarbor Studios needs to launch a prepackaged content management system on Google Clou... |
| [Q2](#q2) | NovaTrail Analytics was incorporated nine months ago and is rapidly expanding its use of G... |
| [Q3](#q3) | CloudNest Retail operates several Linux virtual machines in Google Cloud for its internal ... |
| [Q4](#q4) | SkyRoute Analytics uses Compute Engine resources in the project skyroute-inventory-47. A c... |
| [Q5](#q5) | FitJourney operates a mobile wellness application. The application stores each customer’s ... |
| [Q6](#q6) | StreamWave runs three VPC-native Google Kubernetes Engine clusters that share the same sub... |
| [Q7](#q7) | MedNova Research needs a browser-based JupyterLab environment for a data scientist who ana... |
| [Q8](#q8) | FleetPulse Logistics rents refrigerated shipping containers equipped with sensors that rep... |
| [Q9](#q9) | Northstar Media operates multiple Google Cloud projects for its video-streaming platform. ... |
| [Q10](#q10) | PixelForge Media has installed the Google Cloud CLI on a new administrator workstation. An... |
| [Q11](#q11) | VistaStream Studios is moving several datasets to Google Cloud. The company has below ment... |
| [Q12](#q12) | BrightCart hosts its online ordering application on Compute Engine VMs in europe-west1-b. ... |
| [Q13](#q13) | NovaLens Analytics runs a PyTorch application that uses custom CUDA extensions for model p... |
| [Q14](#q14) | ParcelPilot is preparing to launch a containerized shipment-tracking service on Google Clo... |
| [Q15](#q15) | Northstar Clinic runs an appointment-processing application on a Compute Engine VM. Employ... |
| [Q16](#q16) | ArcadeWave operates an online gaming platform that receives match-result events from milli... |
| [Q17](#q17) | MediLedger is deploying a patient appointment application on Google Cloud. The application... |
| [Q18](#q18) | NightPulse Media processes video analytics every evening by running a batch job across man... |
| [Q19](#q19) | BluePeak Games has several software engineering teams based in the United States. Each tea... |
| [Q20](#q20) | BrightCart runs an order-processing service on a Compute Engine VM. The VM uses the Comput... |
| [Q21](#q21) | PixelForge Studio is preparing a Compute Engine batch-rendering service in asia-southeast1... |
| [Q22](#q22) | BrightCart, an online retail company, requires every Google Cloud resource to follow appro... |
| [Q23](#q23) | Northstar Health operates separate Google Cloud environments for its clinical, finance, an... |
| [Q24](#q24) | PulseGrid Energy receives continuous telemetry from thousands of smart meters deployed acr... |
| [Q25](#q25) | BrightForge Media uses a Jenkins deployment server that authenticates to Google Cloud with... |
| [Q26](#q26) | FreshBasket, an online grocery platform, runs PostgreSQL database VMs in data-subnet. Its ... |
| [Q27](#q27) | VistaMetrics runs a data-processing application in a Google Kubernetes Engine Standard clu... |
| [Q28](#q28) | GlobeTix is building a ticket-reservation platform for customers in several continents. Th... |
| [Q29](#q29) | HarborView Media hosts its public website behind a Google Cloud load balancer with a reser... |
| [Q30](#q30) | RideWave operates a fleet-management platform on Google Cloud. Its Compute Engine VM insta... |
| [Q31](#q31) | ParcelPilot is deploying an order-processing application in a new Google Cloud VPC network... |
| [Q32](#q32) | Northstar Media runs Linux-based build servers on Compute Engine. A new support vendor mus... |
| [Q33](#q33) | GlobeCart runs an online shopping website on Compute Engine. Its customer base is growing ... |
| [Q34](#q34) | TrailNest Travel operates a trip-planning website on Cloud Run for approximately 650 custo... |
| [Q35](#q35) | BrightCart operates several applications on Google Cloud, including an order-processing se... |
| [Q36](#q36) | CipherForge Labs wants to provide its engineers with standardized, browser-accessible deve... |
| [Q37](#q37) | CodeHarbor Labs manages Cloud Workstations for developers building its online payment plat... |
| [Q38](#q38) | ImageForge operates a media platform where customers upload images to a Cloud Storage buck... |
| [Q39](#q39) | BrightTrail Media is developing a local automation script that runs several gcloud CLI com... |
| [Q40](#q40) | MediRoute, a medical appointment mobile app, stores its scheduling database on a Persisten... |
| [Q41](#q41) | NovaLedger has assigned you responsibility for maintaining an existing Google Cloud projec... |
| [Q42](#q42) | TerraPulse Agriculture operates approximately 4 million connected field devices that conti... |
| [Q43](#q43) | NordicCare Analytics is migrating several healthcare reporting workloads to Google Cloud. ... |
| [Q44](#q44) | HarborLine Logistics grants its cloud engineering team the Compute Admin role on the Core-... |
| [Q45](#q45) | AsterBank routes security logs from Cloud Logging to a centralized destination. After an I... |
| [Q46](#q46) | ParcelPulse uses Pub/Sub to process shipment status events. A pull subscription named trac... |
| [Q47](#q47) | BrightCart operates an online retail platform across two Google Cloud projects. The web ap... |
| [Q48](#q48) | TensorPeak Labs is training a large language model with JAX. The workload relies heavily o... |
| [Q49](#q49) | FestivalNest has created a containerized website that publishes schedules and accepts regi... |
| [Q50](#q50) | Northwind Media uses a Cloud SQL instance to support an internal content-management applic... |

---

### Q1

> PixelHarbor Studios needs to launch a prepackaged content management system on Google Cloud for a new publishing website. The operations team wants the fastest deployment method and does not want to manually install or configure the CMS components. What should the team do?  

- **A.** Find the CMS package in Google Cloud Marketplace and use the gcloud CLI to deploy it.
- **B.** Find the CMS package in Google Cloud Marketplace and deploy it directly from its Marketplace listing.
- **C.** Find the CMS package in Google Cloud Marketplace and use Terraform with the product ID to build and configure the deployment.
- **D.** Download the vendor’s installation instructions and install the CMS by using the company’s configuration management system.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Google Cloud Marketplace does not provide a universal gcloud CLI command that can deploy every Marketplace product. Certain VM and Kubernetes products support command-line deployment, but the exact workflow depends on the product type and can require Terraform configuration, Kubernetes commands, downloaded deployment files, permissions, and additional setup. This approach is therefore not the quickest or easiest general solution. Because the team’s primary requirement is rapid deployment with minimal manual effort, using the deployment interface supplied directly on the product’s Marketplace listing is more appropriate.

**B is correct** because Google Cloud Marketplace is designed to help customers discover, purchase, configure, and deploy validated software packages on Google Cloud with minimal installation effort. After selecting the CMS product, the team can review its pricing and deployment requirements, choose the required project and configuration parameters, and initiate the deployment directly from the Marketplace listing. The Marketplace package typically includes the required software image or application package and its deployment configuration, reducing the need to manually create infrastructure or follow a lengthy vendor installation process. This option most directly satisfies the requirement for a quick and easy deployment.

**C is incorrect** because a Google Cloud Marketplace product ID does not provide a universal mechanism for deploying every Marketplace solution through a custom Terraform configuration. Some Marketplace VM products offer a supported command-line deployment workflow that uses Terraform, but this capability must be explicitly provided by the product listing. The team would also need to download or prepare the relevant Terraform configuration, supply variables, configure authentication, and manage the resulting infrastructure deployment. Terraform can be valuable when repeatable infrastructure-as-code deployments are required, but the question prioritizes speed and simplicity rather than automation or customization.

**D is incorrect** because manually following the CMS vendor’s installation guide and using a configuration management system requires the team to provision the infrastructure, install dependencies, configure the CMS, validate compatibility, and maintain its installation automation. This process can provide greater control and may be suitable when the Marketplace does not offer the required product or when extensive customization is necessary. However, it introduces significantly more administrative work than deploying a prepackaged and validated solution directly from Google Cloud Marketplace, so it does not meet the requirement for the quickest and easiest deployment method.

**Reference links**

- [cloud.google.com/marketplace/docs/get-products](https://cloud.google.com/marketplace/docs/get-products)
- [cloud.google.com/marketplace/docs/overview](https://cloud.google.com/marketplace/docs/overview)
- [cloud.google.com/marketplace/docs/deploy-through-CLI](https://cloud.google.com/marketplace/docs/deploy-through-CLI)

**Related notes:** [Cloud Marketplace](../08-iac-platform-ai/products/cloud-marketplace.md)

</details>

[Back to index](#index)

---

### Q2

> NovaTrail Analytics was incorporated nine months ago and is rapidly expanding its use of Google Cloud. The platform team wants every engineer to be able to create projects and attach them to a centrally managed payment arrangement without entering personal credit card information. What should the platform team do?  

- **A.** Create a central Cloud Billing account, add a company-controlled payment method, grant engineers the Project Creator role, and grant them the Billing Account User role on the Cloud Billing account.
- **B.** Grant every engineer permission to create a separate Cloud Billing account whenever they create a project.
- **C.** Request monthly invoiced billing so the finance department receives and pays one consolidated monthly invoice.
- **D.** Create a Cloud Billing account, assign a monthly purchase order to it, and submit the purchase order to Google Cloud as the payment method.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a Cloud Billing account can be linked to multiple Google Cloud projects and can use a centrally managed company payment method. Engineers do not need access to the payment method or the underlying Google payments profile. To create projects, they need a role containing the resourcemanager.projects.create permission, such as Project Creator. To associate those projects with the organization’s Cloud Billing account, they need the Billing Account User role on that billing account. The Billing Account User role has limited permissions and allows users to link projects to the billing account without giving them broad billing-administration privileges or access to modify payment details. This approach centralizes payment responsibility while allowing engineers to create billable projects independently.

**B is incorrect** because engineers do not need a separate Cloud Billing account for every project. A single Cloud Billing account can fund and track costs for many projects. Allowing every engineer to create billing accounts would unnecessarily decentralize financial management, potentially require engineers to configure payment profiles or payment methods, and make cost governance more difficult. It could also give engineers more billing-related access than they need. The principle of least privilege is better satisfied by granting engineers Project Creator and Billing Account User permissions for an existing centrally managed billing account.

**C is incorrect** because the startup does not meet the minimum business-age requirement for monthly invoiced billing. Organizations applying for monthly invoicing must generally have been registered as a business for at least one year, expect to spend at least USD 40,000 annually on Google Cloud, and operate in a country where invoiced billing is available. Because NovaTrail Analytics has existed for only nine months, it is not currently eligible based on the stated scenario. Monthly invoicing is also unnecessary for solving the engineers’ project-creation requirement because a self-serve Cloud Billing account with a company-controlled payment method can already be linked to multiple projects.

**D is incorrect** because a purchase order is not a payment method for a self-serve Cloud Billing account. A purchase order number is an identifier that can appear on invoices associated with an existing monthly invoiced Cloud Billing account. It does not establish invoiced billing, replace a credit card or bank account, or become valid merely by being sent to Google Cloud. Because the startup is not yet eligible for monthly invoiced billing, it cannot use a purchase order number in this way. The appropriate solution is to create a self-serve Cloud Billing account with a company payment method and grant engineers limited permission to link their projects to it.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/billing-access](https://docs.cloud.google.com/billing/docs/how-to/billing-access)
- [docs.cloud.google.com/billing/docs/how-to/invoiced-billing](https://docs.cloud.google.com/billing/docs/how-to/invoiced-billing)
- [docs.cloud.google.com/billing/docs/how-to/purchase-order](https://docs.cloud.google.com/billing/docs/how-to/purchase-order)

**Related notes:** [Cloud Billing](../07-operations-cost/products/cloud-billing.md)

</details>

[Back to index](#index)

---

### Q3

> CloudNest Retail operates several Linux virtual machines in Google Cloud for its internal inventory platform. Administrators need secure SSH access to these instances without exposing them directly to the internet or maintaining additional access infrastructure. The company also wants to minimize operational costs. What should the cloud administrator do?  

- **A.** Assign an external IP address to each instance and create an ingress firewall rule that permits internet traffic on TCP port 22.
- **B.** Connect by using the gcloud compute ssh command with the --tunnel-through-iap flag and create an ingress firewall rule that permits TCP port 22 from 35.235.240.0/20.
- **C.** Install a third-party remote-access agent on every instance and use the vendor’s service to establish administrative sessions.
- **D.** Deploy a publicly accessible bastion host and establish SSH tunnels from the bastion host to the private instances.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because assigning external IP addresses and allowing SSH traffic from the internet exposes the instances’ SSH services to internet-based scanning, brute-force attempts, and other attacks. Even when SSH keys and strong authentication are used, directly exposing TCP port 22 increases the attack surface and requires careful source IP restrictions and ongoing monitoring. External IP addresses can also create additional networking costs. This approach is neither the most secure nor the most cost-efficient option when Identity-Aware Proxy can provide access to instances through their internal IP addresses.

**B is correct** because Identity-Aware Proxy TCP forwarding lets administrators connect to Linux instances through an encrypted tunnel without assigning external IP addresses to the instances. The gcloud compute ssh command with the --tunnel-through-iap flag directs the SSH connection through Identity-Aware Proxy. Before establishing the tunnel, Identity-Aware Proxy verifies the user’s identity and checks whether the user has the required IAM permissions for the target instance. The firewall rule must allow ingress TCP traffic on port 22 from 35.235.240.0/20, which is the source range used by Identity-Aware Proxy TCP forwarding. The rule can also be limited to the appropriate instances by using target network tags or target service accounts. This design avoids exposing SSH directly to the internet and eliminates the need to deploy, secure, patch, and operate a separate bastion host. For stronger centralized SSH access management, the organization can combine this approach with OS Login and IAM roles.

**C is incorrect** because a third-party remote-access product introduces additional software, vendor dependencies, licensing expenses, and administrative overhead. The team might need to install and update agents, integrate identity management, monitor an additional service, and evaluate how the vendor protects administrative traffic. A third-party solution might be appropriate when specialized remote-support functionality is required, but no such requirement is stated. Identity-Aware Proxy already provides identity-aware, IAM-controlled TCP forwarding as a native Google Cloud capability, making a third-party product unnecessary for this scenario.

**D is incorrect** because a bastion host can provide controlled access to private instances, but the bastion host itself must be deployed, secured, monitored, patched, and made highly available when reliable administrative access is required. A publicly accessible bastion also remains exposed to internet traffic and can become a high-value attack target. The organization incurs Compute Engine and networking costs for the additional instance, even when administrators are not actively using it. Identity-Aware Proxy provides secure access without a public IP address on the target instances and without maintaining an additional jump server, making it more secure and cost-efficient for this requirement.

**Reference links**

- [docs.cloud.google.com/compute/docs/connect/ssh-using-iap](https://docs.cloud.google.com/compute/docs/connect/ssh-using-iap)
- [docs.cloud.google.com/iap/docs/using-tcp-forwarding](https://docs.cloud.google.com/iap/docs/using-tcp-forwarding)
- [docs.cloud.google.com/compute/docs/oslogin](https://docs.cloud.google.com/compute/docs/oslogin)

**Related notes:** [Identity-Aware Proxy (IAP)](../02-identity-security/products/identity-aware-proxy.md)

</details>

[Back to index](#index)

---

### Q4

> SkyRoute Analytics uses Compute Engine resources in the project skyroute-inventory-47. A contractor from a partner company needs permission only to view the lists of Compute Engine disks and images in this project. You must grant the access by following Google Cloud’s principle of least privilege. What should you do?  

- **A.** Create a project-level custom role containing only compute.disks.list and compute.images.list in the includedPermissions field, and grant the role to the contractor.
- **B.** Create a custom role from the Compute Image User role, add compute.disks.list to includedPermissions, and grant the role to the contractor at the project level.
- **C.** Create a custom role from the Compute Storage Admin role, remove selected administrative permissions, and grant the resulting role to the contractor at the project level.
- **D.** Grant the predefined Compute Storage Admin role to the contractor at the project level.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the contractor requires exactly two operations: listing the Compute Engine disks and listing the Compute Engine images in the project. The compute.disks.list permission authorizes listing disks, while compute.images.list authorizes listing images. A custom role whose includedPermissions field contains only these two permissions gives the contractor precisely the required access and no ability to retrieve detailed image information, use images, create resources, modify disks, delete images, resize disks, manage snapshots, or change IAM policies. Granting the role at the project level is appropriate because the contractor must list the collections of disks and images belonging to that project. This directly implements the principle of least privilege, which recommends granting only the permissions necessary for the stated task when no suitably limited predefined role exists.

**B is incorrect** because the Compute Image User role contains more than compute.images.list. It also includes permissions such as compute.images.get, compute.images.getFromFamily, and compute.images.useReadOnly. At the project level, these permissions can allow the principal to inspect images and use project images as sources for resources such as instances and persistent disks. Adding compute.disks.list would satisfy the disk-listing requirement, but the resulting custom role would still provide image-related capabilities beyond simple list access. Therefore, it is less restrictive than a custom role containing only compute.disks.list and compute.images.list.

**C is incorrect** because the Compute Storage Admin role is a broad administrative role containing extensive permissions for disks, images, snapshots, encryption-related resources, labels, IAM policies, creation, modification, and deletion. Starting with this large role and manually removing permissions is unnecessarily complex and creates a greater risk of accidentally retaining an excessive permission. Although a carefully pruned role could theoretically be reduced to the same two permissions, this option does not explicitly guarantee that the final role contains only compute.disks.list and compute.images.list. When the exact required permissions are already known, defining them directly is clearer, easier to audit, and more consistent with strict least privilege.

**D is incorrect** because the Compute Storage Admin role grants administrative control over Compute Engine storage resources. It includes permissions to create, modify, resize, use, and delete disks; create, update, deprecate, and delete images; manage snapshots; modify labels; and perform other storage administration tasks. The contractor needs only list access, so granting this role would provide substantially more authority than necessary and would violate the principle of least privilege, especially because the user is external to the organization.

**Reference links**

- [docs.cloud.google.com/iam/docs/choose-role-type](https://docs.cloud.google.com/iam/docs/choose-role-type)
- [docs.cloud.google.com/iam/docs/roles-overview](https://docs.cloud.google.com/iam/docs/roles-overview)
- [docs.cloud.google.com/compute/docs/access/iam](https://docs.cloud.google.com/compute/docs/access/iam)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q5

> FitJourney operates a mobile wellness application. The application stores each customer’s current profile and subscription status in Spanner, while Bigtable records all customer activity events. FitJourney also exports its Spanner database to Cloud Storage every night. A data analyst needs to combine the profile data and activity events for a small set of customers as a one-time analysis. You want to fulfill the request with the least operational effort. What should you do?  

- **A.** Create a Dataflow job that copies the required customer records from Bigtable and the Spanner export in Cloud Storage.
- **B.** Create a Dataflow job that reads the required customer records directly from Bigtable and Spanner.
- **C.** Create a Dataproc cluster and run a Spark job that extracts the required customer data from Bigtable and the Spanner export in Cloud Storage.
- **D.** -Create one BigQuery external table for the Spanner export in Cloud Storage and another BigQuery external table for Bigtable.  
  -Join the external tables by the customer identifier and filter for the required customers.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a Dataflow pipeline would require the company to develop or configure a batch-processing job, define schemas and transformations, specify an output destination, run the job, and monitor its execution. The option also states only that the data is copied; it does not clearly specify that the two datasets are joined to produce the analyst’s required result. Dataflow is valuable for repeatable, large-scale data movement and transformation pipelines, but creating a pipeline for a small, one-time analytical request introduces unnecessary implementation and operational work. Because the relevant Spanner export already exists in Cloud Storage, BigQuery can query that data without first copying it elsewhere.

**B is incorrect** because reading directly from the production Spanner database is unnecessary when a suitable exported copy already exists in Cloud Storage. A custom Dataflow job would need connectors for both Spanner and Bigtable, logic to filter and correlate the user records, and a destination for the joined results. It could also consume resources from the operational Spanner database that supports the application. Although Dataflow can process data from multiple sources, it is better suited to managed pipelines that must run repeatedly or perform complex transformations. For an ad hoc SQL-style join, this option adds development effort and touches the live transactional database without providing a meaningful advantage.

**C is incorrect** because Dataproc requires the creation and configuration of a cluster or an equivalent serverless Spark workload, along with Spark code, connectors, dependency management, permissions, and lifecycle management. Spark can read data from Bigtable and Cloud Storage and can perform the join, so this approach is technically possible. However, it is unnecessarily complex for a one-time request involving only selected customers. Starting a distributed processing environment is more operationally intensive than defining external tables and running a SQL query in BigQuery. Dataproc would be more appropriate for an existing Spark ecosystem, specialized Spark processing, or recurring large-scale jobs.

**D is correct** because BigQuery external tables allow the analyst to query supported data in Cloud Storage and Bigtable without first loading or copying that data into native BigQuery storage. The Spanner backup export in Cloud Storage can be exposed through a Cloud Storage external table when it uses a supported format such as Avro or CSV, and the Bigtable data can be exposed through a Bigtable external table with the required schema mapping. The analyst can then use GoogleSQL to join the two external tables on the shared customer identifier and apply filters so that only the requested customers are analyzed. This approach avoids building a custom Dataflow pipeline, avoids provisioning a Dataproc cluster, and avoids querying the production Spanner database directly. It therefore provides the lowest operational overhead and is the most efficient choice for an ad hoc analytical request.

**Reference links**

- [cloud.google.com/bigquery/docs/external-data-bigtable](https://cloud.google.com/bigquery/docs/external-data-bigtable)
- [cloud.google.com/bigquery/docs/external-data-cloud-storage](https://cloud.google.com/bigquery/docs/external-data-cloud-storage)
- [cloud.google.com/spanner/docs/import-export-overview](https://cloud.google.com/spanner/docs/import-export-overview)

**Related notes:** [BigQuery](../05-storage-databases-data/products/bigquery.md)

</details>

[Back to index](#index)

---

### Q6

> StreamWave runs three VPC-native Google Kubernetes Engine clusters that share the same subnet. The subnet’s available node IP addresses have been exhausted, preventing the clusters from adding more nodes during periods of high demand. What should StreamWave do?  

- **A.** Create another subnet in the same region as the existing cluster subnet.
- **B.** Add a secondary alias IP range to the subnet used by the GKE clusters.
- **C.** Create another VPC network and connect it to the existing VPC network by using VPC Network Peering.
- **D.** Expand the primary CIDR range of the subnet used by the GKE clusters.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because merely creating another subnet in the same region does not automatically make its IP addresses available to the existing GKE clusters. The clusters and their current node pools continue to obtain node IP addresses from the primary IP range of their configured subnet. Although newer GKE versions support assigning additional subnets to eligible VPC-native clusters, that requires explicitly associating the additional subnet with each cluster and creating node pools that use it. The option only creates a subnet and therefore does not directly resolve the exhausted node IP range for the existing cluster configuration.

**B is incorrect** because secondary alias IP ranges in a VPC-native GKE configuration are generally used for Pod and Service IP addresses. GKE nodes receive their primary internal IP addresses from the primary IPv4 range of the cluster’s subnet. Adding another secondary range could help when Pod IP addresses are exhausted, but it does not increase the number of primary subnet addresses available for nodes. Because the problem specifically states that node IP addresses are exhausted, expanding a secondary alias IP range would address the wrong IP address pool.

**C is incorrect** because VPC Network Peering enables private communication between resources in separate VPC networks, but it does not combine or share the subnet IP address pools of the peered networks. The existing GKE clusters would still use the exhausted primary range of their current subnet. Moving or extending the clusters into another VPC would require substantial network and cluster redesign, and peering alone would not provide additional node IP addresses to the existing node pools.

**D is correct** because GKE nodes obtain their internal IP addresses from the primary IPv4 range of the cluster subnet. Expanding that subnet’s primary CIDR range adds more addresses to the same subnet, allowing the GKE clusters to create additional nodes without being moved to another VPC or subnet. A subnet’s primary IPv4 range can be expanded to a larger contiguous CIDR block as long as the expanded range does not overlap another subnet or allocated IP range. The expansion cannot later be reversed or reduced, so the new range should be selected carefully. If the clusters use control-plane authorized networks or manually configured firewall rules, those configurations should also be reviewed to ensure that nodes created in the expanded address space can communicate correctly.

**Reference links**

- [cloud.google.com/kubernetes-engine/docs/concepts/alias-ips](https://cloud.google.com/kubernetes-engine/docs/concepts/alias-ips)
- [cloud.google.com/kubernetes-engine/docs/troubleshooting/vpc-clusters](https://cloud.google.com/kubernetes-engine/docs/troubleshooting/vpc-clusters)
- [cloud.google.com/vpc/docs/create-modify-vpc-networks](https://cloud.google.com/vpc/docs/create-modify-vpc-networks)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q7

> MedNova Research needs a browser-based JupyterLab environment for a data scientist who analyzes clinical datasets. The environment must include ready-to-use TensorFlow and PyTorch packages, integrate with BigQuery and Cloud Storage, and support an optional GPU. The infrastructure team does not want to build or maintain its own notebook VM image. What should MedNova Research provision?  

- **A.** A Cloud Shell session with a manually installed graphical desktop and notebook software
- **B.** A Cloud Storage bucket mounted by using Cloud Storage FUSE without a notebook compute environment
- **C.** A Gemini Enterprise Agent Platform Workbench instance configured with the required machine type, GPU, and networking options
- **D.** A regional external Application Load Balancer configured to forward notebook traffic

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Cloud Shell is primarily an interactive command-line environment for managing Google Cloud resources and performing lightweight development tasks. It is not designed to serve as a configurable, GPU-enabled managed JupyterLab platform for sustained data science and machine-learning workloads. The team would need to install and maintain the notebook software, graphical components, TensorFlow, PyTorch, drivers, and other dependencies manually. Cloud Shell also does not provide the selectable GPU hardware configuration required by the data scientist. This approach would create additional operational work and would not satisfy the requirement to avoid maintaining a custom notebook environment.

**B is incorrect** because mounting a Cloud Storage bucket with Cloud Storage FUSE only makes objects in the bucket accessible through file-system-like operations. It does not provision a JupyterLab interface, CPU or GPU compute resources, TensorFlow or PyTorch packages, notebook kernels, BigQuery integration, or a managed machine-learning development environment. Cloud Storage FUSE could be used as one storage-access component within a larger environment, but by itself it cannot run notebooks or machine-learning code.

**C is correct** because Gemini Enterprise Agent Platform Workbench provides a managed, JupyterLab-based development environment designed for data science and machine-learning workflows. Workbench instances include a preinstalled collection of deep-learning packages and support both TensorFlow and PyTorch, allowing the data scientist to begin working without the operations team creating and maintaining a custom VM image. The JupyterLab interface includes integrations for browsing and accessing BigQuery tables and Cloud Storage objects, subject to the user or instance service account having the necessary IAM permissions. When creating the instance, the team can select an appropriate Compute Engine machine type, memory and CPU capacity, data-disk configuration, region, zone, VPC network, subnet, external-IP behavior, and service account. It can also attach a supported NVIDIA GPU and enable automatic GPU-driver installation. This option directly satisfies the requirements for a managed notebook environment, preinstalled frameworks, Google Cloud data-service integrations, configurable networking, and optional GPU acceleration.

**D is incorrect** because a regional external Application Load Balancer distributes HTTP or HTTPS requests across backend services. It does not provide a JupyterLab runtime, notebook kernels, TensorFlow or PyTorch packages, BigQuery or Cloud Storage development integrations, persistent notebook storage, or GPU compute capacity. A load balancer might be placed in front of certain web applications, but it cannot replace the actual notebook environment needed by the data scientist.

**Reference links**

- [docs.cloud.google.com/gemini-enterprise-agent-platform/notebooks/workbench/introduction](https://docs.cloud.google.com/gemini-enterprise-agent-platform/notebooks/workbench/introduction)
- [docs.cloud.google.com/gemini-enterprise-agent-platform/notebooks/workbench/notebook-solution](https://docs.cloud.google.com/gemini-enterprise-agent-platform/notebooks/workbench/notebook-solution)
- [docs.cloud.google.com/gemini-enterprise-agent-platform/notebooks/workbench/instances/create](https://docs.cloud.google.com/gemini-enterprise-agent-platform/notebooks/workbench/instances/create)

**Related notes:** [Gemini Enterprise Agent Platform: Workbench](../08-iac-platform-ai/products/workbench.md)

</details>

[Back to index](#index)

---

### Q8

> FleetPulse Logistics rents refrigerated shipping containers equipped with sensors that report temperature, compressor status, battery level, location, and operating hours. Each container can generate several thousand measurements per hour. The billing system must retrieve measurements efficiently by event time, and each individual measurement must be written and read atomically. Which storage design should FleetPulse Logistics use?  

- **A.** Store every incoming batch of sensor measurements as a separate object in Cloud Storage.
- **B.** Create one file in Filestore for each refrigerated container and append new measurements to that file.
- **C.** Store the measurements in Cloud SQL and add multiple read replicas to support the ingestion volume.
- **D.** Store the measurements in Bigtable and use a row key that combines the container identifier with the event timestamp.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Cloud Storage is an object storage service optimized for durable storage of files and other immutable objects rather than for high-frequency, record-level operational data. Creating objects as individual measurements arrive would generate a very large number of small objects and would not provide an efficient way to query measurements by device and event time. Combining multiple measurements into larger objects would improve storage efficiency, but the application would then need to download and parse those objects to retrieve individual records. Cloud Storage operations are atomic at the object level, not at the individual sensor-record level inside an object, so it does not directly satisfy the requirement to store and retrieve each signal atomically.

**B is incorrect** because Filestore provides managed NFS file shares and is primarily intended for applications that require a shared POSIX-compatible file system. Appending every measurement from a device to one file would create contention when multiple processes attempt to write or read that file. The application would also have to implement custom indexing, file locking, record boundaries, corruption recovery, retention management, and time-range scanning. Filestore provides file-system semantics, but it is not a high-throughput, distributed time-series database and does not natively provide atomic access to individual logical sensor records stored inside an appended file.

**C is incorrect** because Cloud SQL is a relational database service and can store structured sensor records, but multiple read replicas do not increase the write capacity of the primary instance. All incoming sensor measurements must still be written to the primary database, while read replicas are read-only resources used to offload read queries and analytics traffic. At a large fleet scale, continuous writes from many devices can create a write bottleneck on the primary instance. Cloud SQL would also require relational schema management and potentially database sharding as the workload grows. It is appropriate when relational transactions, joins, and SQL constraints are central requirements, but it is not the best choice for this high-volume, single-keyed time-series workload.

**D is correct** because Bigtable is a distributed, wide-column NoSQL database designed for large operational and analytical workloads that require high read and write throughput with low latency. Sensor and telemetry data are common Bigtable use cases. Each measurement can be stored in its own row, with columns containing values such as temperature, battery level, compressor state, and usage counters. Bigtable mutations are atomic at the row level, so all values belonging to one sensor event can be written atomically in a single row mutation. A row key combining a distributed identifier such as the container ID with the event timestamp allows the application to retrieve a container’s measurements in timestamp order and perform efficient time-range scans. The timestamp should normally be placed after a device or hash-based prefix rather than at the beginning of the row key, because timestamp-prefixed sequential keys can concentrate new writes in one key range and create a hotspot. When very high traffic exists for individual devices, additional hashing or bucketing can be added to distribute writes more evenly.

**Reference links**

- [cloud.google.com/bigtable/docs/overview](https://cloud.google.com/bigtable/docs/overview)
- [cloud.google.com/bigtable/docs/schema-design-time-series](https://cloud.google.com/bigtable/docs/schema-design-time-series)
- [cloud.google.com/bigtable/docs/routing](https://cloud.google.com/bigtable/docs/routing)

**Related notes:** [Bigtable](../05-storage-databases-data/products/bigtable.md)

</details>

[Back to index](#index)

---

### Q9

> Northstar Media operates multiple Google Cloud projects for its video-streaming platform. The security team must prevent direct SSH access from all public IPv4 addresses to workloads in every current and future VPC network. Project teams must remain able to create their own lower-level firewall rules for web, database, and internal application traffic. The restriction must be administered centrally and inherited throughout the organization. What should the security team configure?  

- **A.** Create an ingress VPC firewall rule separately in each existing VPC network.
- **B.** Deploy Cloud NAT in every project and remove external IP addresses from the NAT gateways.
- **C.** Configure a Cloud DNS policy that prevents the resolution of hostnames associated with SSH servers.
- **D.** Associate a hierarchical firewall policy with the organization and add a high-priority ingress deny rule for TCP port 22 from 0.0.0.0/0.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because ordinary VPC firewall rules are configured for individual VPC networks and do not automatically apply to other networks in the organization. The security team would have to discover every existing network, create and maintain a matching rule in each one, and repeat the process whenever a new project or VPC network is created. This approach is decentralized, difficult to govern consistently, and vulnerable to configuration drift or accidental omission. It also does not provide the required inheritance from the organization level.

**B is incorrect** because Cloud NAT provides outbound network address translation for resources that do not have external IP addresses. It enables supported workloads to initiate outbound connections to the internet and does not create a centrally inherited inbound firewall control. Cloud NAT does not evaluate or block unsolicited inbound SSH traffic to resources that have reachable external IP addresses. Removing external IP addresses from workloads can reduce their direct internet exposure, but Cloud NAT itself does not satisfy the requirement to enforce an organization-wide inherited deny rule while allowing lower-level teams to manage other traffic.

**C is incorrect** because Cloud DNS policies control DNS behavior, such as name resolution, logging, forwarding, and response policies. Blocking the resolution of a hostname does not block SSH network traffic because a user can connect directly to an external IP address or use another hostname. DNS is not an enforcement mechanism for TCP port 22, and a Cloud DNS policy cannot provide an inherited network-layer deny rule across all VPC networks.

**D is correct** because a hierarchical firewall policy can be associated with the Google Cloud organization and inherited by folders, projects, and their VPC networks, including networks created later. The security team can create an ingress deny rule matching TCP port 22 with 0.0.0.0/0 as the source range and assign it a sufficiently high precedence, represented by a lower numerical priority value. Because hierarchical firewall policies are evaluated before VPC firewall rules, project teams cannot override this SSH restriction with a lower-level allow rule. The policy can use other rules or the goto_next action to delegate evaluation of unrelated traffic to folder-level policies, project-level policies, or VPC firewall rules, allowing application teams to retain control over other permitted traffic.

**Reference links**

- [docs.cloud.google.com/firewall/docs/firewall-policies](https://docs.cloud.google.com/firewall/docs/firewall-policies)
- [docs.cloud.google.com/firewall/docs/firewall-policies-rule-eval-order](https://docs.cloud.google.com/firewall/docs/firewall-policies-rule-eval-order)
- [docs.cloud.google.com/firewall/docs/using-firewall-policies](https://docs.cloud.google.com/firewall/docs/using-firewall-policies)

**Related notes:** [Firewall, Hierarchical Policies, and Secure Tags (Cloud NGFW)](../06-networking/products/firewall-hierarchical-policies-and-secure-tags.md)

</details>

[Back to index](#index)

---

### Q10

Choose 2.

> PixelForge Media has installed the Google Cloud CLI on a new administrator workstation. An engineer needs to display all Compute Engine virtual machine instances in the company’s existing Google Cloud project by running gcloud compute instances list. Which two actions must the engineer complete first? (Choose two.)  

- **A.** Run gcloud auth login and complete the browser-based sign-in process with an authorized corporate user account.
- **B.** Create a service account, download its service account key file, and save the key in a directory searched by the Google Cloud CLI.
- **C.** Download a private key for the engineer’s Cloud Identity user account and save it in a directory searched by the Google Cloud CLI.
- **D.** Run gcloud config set compute/zone europe-west3-b to configure a default Compute Engine zone.
- **E.** Run gcloud config set project media-production-42 to configure the target Google Cloud project.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A, E

**Explanation**

**A is correct** because the Google Cloud CLI must have an authenticated principal before it can make authorized requests to Google Cloud APIs. The gcloud auth login command starts a browser-based authorization flow in which the engineer signs in using a corporate Google account. The Google Cloud CLI then stores the resulting user credentials in its local configuration and uses them for subsequent commands. The authenticated user must also have an IAM role containing the compute.instances.list permission, such as Compute Viewer, for the target project. On systems where a browser cannot be opened locally, the command supports alternative authorization flows, but a normal corporate laptop typically uses the browser-based flow.

**B is incorrect** because creating a service account and downloading a service account key is not required for a human administrator using the Google Cloud CLI interactively. User credentials obtained through gcloud auth login are the appropriate authentication mechanism for this scenario. Downloaded service account keys are long-lived credentials that create additional security and key-management risks, so Google recommends avoiding them when a more secure authentication method is available. Service accounts are generally intended for applications and automated workloads, and even those workloads should preferably use service account impersonation, attached service accounts, or Workload Identity Federation instead of downloaded keys.

**C is incorrect** because Cloud Identity user accounts do not provide downloadable private key files for authenticating the Google Cloud CLI. Human users authenticate through an interactive OAuth sign-in flow, such as gcloud auth login. Service account keys exist for service accounts, but they are not Cloud Identity user account keys. Therefore, the engineer cannot download and place a Cloud Identity user key in a folder for automatic discovery by the Google Cloud CLI.

**D is incorrect** because gcloud compute instances list is not restricted to one zone by default. The command lists Compute Engine instances across all zones in the selected project unless the engineer explicitly limits the output by using the --zones flag or another filter. A default zone is useful for commands that operate on a specific zonal resource, such as creating or describing a virtual machine without supplying --zone, but it is not required to list all instances in a project.

**E is correct** because gcloud compute instances list needs to know which Google Cloud project should be queried. Running gcloud config set project media-production-42 sets the project property in the active Google Cloud CLI configuration, allowing subsequent commands to target that project without repeatedly specifying --project. The engineer could alternatively include --project=media-production-42 directly with the list command, but when using the command exactly as shown, setting the default project first is necessary. Authentication and project selection serve different purposes: authentication identifies the principal, while the project configuration identifies the resource scope to query.

**Reference links**

- [cloud.google.com/sdk/docs/authenticate](https://cloud.google.com/sdk/docs/authenticate)
- [cloud.google.com/sdk/gcloud/reference/config/set](https://cloud.google.com/sdk/gcloud/reference/config/set)
- [cloud.google.com/sdk/gcloud/reference/compute/instances/list](https://cloud.google.com/sdk/gcloud/reference/compute/instances/list)

</details>

[Back to index](#index)

---

### Q11

> VistaStream Studios is moving several datasets to Google Cloud. The company has below mentioned tech-stack. The raw media footage must be migrated to one Cloud Storage bucket, the Amazon Redshift data must be migrated to BigQuery, and the image thumbnails must be copied to another Cloud Storage bucket. The migration team wants to use Google-recommended managed services and does not want to develop custom migration code. Which combination of services should the team use?  
> -320 TB of raw media footage stored on an on-premises SAN  
> -Analytics tables stored in an Amazon Redshift data warehouse  
> -35 GB of image thumbnails stored in an Amazon S3 bucket  

- **A.** Use gcloud storage for the raw media footage, Dataflow for the Amazon Redshift data, and Storage Transfer Service for the image thumbnails.
- **B.** Use Transfer Appliance for the raw media footage, BigQuery Data Transfer Service for the Amazon Redshift data, and Storage Transfer Service for the image thumbnails.
- **C.** Use Storage Transfer Service for the raw media footage, BigQuery Data Transfer Service for the Amazon Redshift data, and Storage Transfer Service for the image thumbnails.
- **D.** Use Cloud Data Fusion for the raw media footage, Dataflow for the Amazon Redshift data, and Storage Transfer Service for the image thumbnails.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because gcloud storage is a command-line tool that can copy files to and from Cloud Storage, but it is not the preferred migration method for moving hundreds of terabytes from an on-premises SAN. Such a transfer would depend heavily on the organization’s available network bandwidth, could take a long time, and would require the team to manage command execution, retries, monitoring, and operational interruptions. Transfer Appliance is more appropriate for a large offline bulk migration. Dataflow is also not the recommended no-code service for a standard Amazon Redshift-to-BigQuery migration. Dataflow is a managed data-processing service used to run Apache Beam pipelines, so using it would generally require developing or configuring a custom pipeline to extract, transform, and load the warehouse data. Storage Transfer Service is appropriate for the image thumbnails because it supports managed transfers directly from Amazon S3 to Cloud Storage.

**B is correct** because each source is matched with the Google Cloud service designed for that migration pattern. Transfer Appliance is intended for securely migrating very large on-premises datasets when an online transfer would be slow, disruptive, or constrained by network capacity. The team can copy the SAN data to the physical appliance, return it to Google, and have the data uploaded into the designated Cloud Storage bucket without developing a custom transfer application. BigQuery Data Transfer Service provides a managed migration path from Amazon Redshift to BigQuery. It can coordinate the extraction of the Amazon Redshift schema and data, temporarily stage exported data in Amazon S3, and load the data into BigQuery without requiring the team to build a custom Dataflow pipeline. Storage Transfer Service is the recommended managed service for transferring objects from Amazon S3 to Cloud Storage, making it suitable for the 35 GB collection of image thumbnails. Therefore, this option satisfies the destination requirements, minimizes custom development, and uses services suited to the size and type of each dataset.

**C is incorrect** because BigQuery Data Transfer Service and Storage Transfer Service are appropriate for the Amazon Redshift data and Amazon S3 objects, respectively, but Storage Transfer Service is not the best choice for the initial migration of the 320 TB SAN dataset in this scenario. Storage Transfer Service can perform agent-based transfers from supported on-premises file systems to Cloud Storage, and it can be suitable when sufficient network bandwidth is available. However, transferring hundreds of terabytes online can consume substantial bandwidth, take an extended period, and compete with production traffic. For a one-time migration of this size, Transfer Appliance provides an offline transfer method that reduces dependence on the external network and is the more appropriate Google-recommended choice represented by the available answers.

**D is incorrect** because Cloud Data Fusion is a managed data integration and ETL service rather than a bulk offline data-transfer service. Although it provides a visual interface and connectors for building data pipelines, using it to move hundreds of terabytes of unstructured video files from a SAN to Cloud Storage would add unnecessary data-processing infrastructure and would still depend on network connectivity. Transfer Appliance is designed specifically for this large on-premises transfer requirement. Dataflow is also unnecessary for the Amazon Redshift migration because BigQuery Data Transfer Service already provides a managed Amazon Redshift migration workflow and avoids the need to create a custom Apache Beam pipeline. Storage Transfer Service remains appropriate for the Amazon S3 image files, but the first two service selections make this option incorrect.

**Reference links**

- [docs.cloud.google.com/transfer-appliance/docs/4.0/overview](https://docs.cloud.google.com/transfer-appliance/docs/4.0/overview)
- [docs.cloud.google.com/bigquery/docs/migration/redshift](https://docs.cloud.google.com/bigquery/docs/migration/redshift)
- [docs.cloud.google.com/storage-transfer/docs/create-transfers/agentless/s3](https://docs.cloud.google.com/storage-transfer/docs/create-transfers/agentless/s3)

**Related notes:** [Storage Transfer Service, Transfer Appliance, and BigQuery Data Transfer Service](../05-storage-databases-data/products/storage-transfer-service-transfer-appliance-and-bigquery-dat.md)

</details>

[Back to index](#index)

---

### Q12

> BrightCart hosts its online ordering application on Compute Engine VMs in europe-west1-b. The company wants the application to remain available if one Compute Engine zone fails while avoiding the additional cost and complexity of a multi-region deployment. What should BrightCart do?  

- **A.** Create Compute Engine resources in europe-west1-c and distribute application traffic across the resources in europe-west1-b and europe-west1-c.
- **B.** Create a Managed Instance Group only in europe-west1-b and configure its health check with a short check interval.
- **C.** Create an external Application Load Balancer and global forwarding rules that direct traffic only to the existing VMs.
- **D.** Back up the application regularly, configure a Cloud Monitoring alert for application failure, and restore the application from a backup after receiving an alert.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because deploying Compute Engine resources in a second zone within the same region removes the existing zone as the application’s single point of failure. A load balancer can distribute requests across healthy resources in europe-west1-b and europe-west1-c. If either zone becomes unavailable, traffic can be directed to the healthy instances in the remaining zone, allowing the application to continue serving users. Using two zones in one region is also less expensive and operationally simpler than deploying the application across multiple regions. In practice, a regional Managed Instance Group can spread instances across multiple zones and integrate with Cloud Load Balancing to provide this type of zonal-failure protection.

**B is incorrect** because a zonal Managed Instance Group whose instances all run in europe-west1-b cannot protect the application from the complete failure of europe-west1-b. The Managed Instance Group can automatically recreate an individual unhealthy VM, and a shorter health-check interval might detect an instance failure sooner, but it cannot create a replacement in an unavailable zone. Protection against a zonal outage requires instances to be distributed across multiple zones, such as through a regional Managed Instance Group.

**C is incorrect** because an external Application Load Balancer and global forwarding rules do not provide availability when every backend VM remains in the same zone. A load balancer can detect unhealthy backends and stop sending traffic to them, but it must have healthy backends in another failure domain to continue serving requests. If europe-west1-b fails and all backend VMs are located there, the load balancer has no functioning instances to which it can route traffic. Additional Compute Engine resources must therefore be deployed in another zone.

**D is incorrect** because monitoring, alerting, backups, and restoration provide detection and recovery capabilities rather than continuous availability. When the zone fails, the application remains unavailable until administrators receive the alert, provision or recover infrastructure, and restore the application from backup. This process introduces downtime and might also cause data loss between the most recent backup and the failure. Backups remain important for disaster recovery, but they do not replace redundant application resources distributed across independent zones.

**Reference links**

- [cloud.google.com/compute/docs/instance-groups/regional-migs](https://cloud.google.com/compute/docs/instance-groups/regional-migs)
- [cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups)
- [cloud.google.com/load-balancing/docs/load-balancing-overview](https://cloud.google.com/load-balancing/docs/load-balancing-overview)

**Related notes:** [Compute Engine](../03-compute-containers/products/compute-engine.md)

</details>

[Back to index](#index)

---

### Q13

> NovaLens Analytics runs a PyTorch application that uses custom CUDA extensions for model processing and GPU acceleration for interactive scientific visualization. The application is already optimized for NVIDIA hardware, and the company wants to move it to Google Cloud with minimal code changes. Which accelerator should NovaLens Analytics select?  

- **A.** Cloud TPU because every machine-learning application performs best on TPUs
- **B.** An NVIDIA GPU on a suitable accelerator-optimized Compute Engine machine
- **C.** A general-purpose Compute Engine VM without an accelerator because PyTorch cannot use accelerators on Google Cloud
- **D.** Storage Transfer Service

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Cloud TPUs are specialized accelerators designed to execute machine-learning computations compiled through XLA. PyTorch workloads can run on TPUs by using PyTorch/XLA, but this requires the application to target an XLA device instead of a CUDA device. Custom CUDA extensions are written specifically for NVIDIA’s CUDA platform and cannot run directly on a Cloud TPU. Migrating this application to a TPU would therefore require the team to replace, rewrite, or remove its CUDA-specific components and validate whether its visualization libraries support the TPU execution model. TPUs can be effective for compatible large-scale training and inference workloads, but they are not automatically the best choice for every machine-learning workload. Because this application already depends on NVIDIA CUDA and requires minimal migration effort, a Cloud TPU is unsuitable.

**B is correct** because Google Cloud accelerator-optimized Compute Engine machines provide attached NVIDIA GPUs that support CUDA-based workloads. The existing PyTorch application can continue using the CUDA execution model, its custom CUDA extensions, and NVIDIA-compatible visualization libraries with substantially fewer changes than would be required for a different accelerator architecture. Depending on the workload’s compute, graphics, GPU memory, and visualization requirements, the team can select an appropriate accelerator-optimized machine series and NVIDIA GPU. Compute-focused A-series machines are designed for demanding AI, machine-learning, and high-performance computing workloads, while G-series machines are suitable for graphics-intensive applications, visualization, rendering, and certain inference or training workloads. The team must also use compatible NVIDIA drivers, CUDA libraries, and PyTorch packages. This option preserves the application’s existing NVIDIA software stack and therefore provides the smallest migration effort.

**C is incorrect** because PyTorch supports GPU acceleration on Google Cloud Compute Engine instances equipped with NVIDIA GPUs. PyTorch can use CUDA to move tensors, model operations, and supported computations from the CPU to an NVIDIA GPU. Custom CUDA extensions can also be compiled and executed when the VM has a compatible NVIDIA driver, CUDA toolkit, compiler toolchain, and PyTorch environment. A general-purpose VM without an accelerator would execute the workload on CPUs and would not provide the CUDA device required by the application. The model and visualization operations would either fail when they attempt to access CUDA or require substantial CPU-specific modifications, while also losing the performance benefits of GPU acceleration.

**D is incorrect** because Storage Transfer Service is a data-movement service rather than a compute accelerator. It is used to transfer data between supported storage systems, such as moving datasets into Cloud Storage or transferring data between storage locations. It does not execute PyTorch models, provide NVIDIA CUDA capabilities, compile custom CUDA extensions, or accelerate visualization. Although the service could assist with migrating the research team’s datasets, it cannot provide the hardware environment required to run the application.

**Reference links**

- [docs.cloud.google.com/compute/docs/accelerator-optimized-machines](https://docs.cloud.google.com/compute/docs/accelerator-optimized-machines)
- [docs.cloud.google.com/compute/docs/gpus](https://docs.cloud.google.com/compute/docs/gpus)
- [docs.cloud.google.com/tpu/docs/intro-to-tpu](https://docs.cloud.google.com/tpu/docs/intro-to-tpu)

**Related notes:** [Compute Engine](../03-compute-containers/products/compute-engine.md) · [Cloud TPU and GPU](../03-compute-containers/products/cloud-tpu-and-gpu.md)

</details>

[Back to index](#index)

---

### Q14

> ParcelPilot is preparing to launch a containerized shipment-tracking service on Google Cloud. The operations team has already defined the application by using Kubernetes manifests and wants to manage Kubernetes objects such as Deployments, Services, ConfigMaps, and horizontal autoscaling policies. However, the team does not want to configure or maintain worker nodes, node pools, or most cluster infrastructure. Which deployment option should the team choose?  

- **A.** Deploy the application on GKE Autopilot.
- **B.** Deploy the application on Cloud Run.
- **C.** Deploy the application on GKE Standard.
- **D.** Deploy the application on Cloud Run functions.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because GKE Autopilot provides a managed Kubernetes environment while preserving access to the Kubernetes API. The team can deploy its Kubernetes manifests and manage workload-level objects such as Deployments, Services, ConfigMaps, Secrets, and HorizontalPodAutoscalers. At the same time, Google Cloud manages the underlying worker nodes, node provisioning, node scaling, operating system configuration, and many security and reliability settings. This workload-focused operating model gives the team control over its Kubernetes application without requiring it to configure and operate most of the cluster infrastructure. GKE Autopilot is therefore the best match for the combined requirements of using Kubernetes manifests, retaining control over Kubernetes workload deployment, and minimizing infrastructure administration.

**B is incorrect** because Cloud Run is a fully managed platform for running containers, but it does not provide a general-purpose Kubernetes cluster or the standard Kubernetes API for deploying Kubernetes manifests. Cloud Run can deploy container images and supports its own service configuration in YAML, but that YAML represents Cloud Run resources rather than Kubernetes objects such as Deployments, StatefulSets, DaemonSets, or Kubernetes Services. Cloud Run would minimize infrastructure management, but the team would lose the requested level of Kubernetes deployment control and would need to adapt its deployment configuration to the Cloud Run resource model.

**C is incorrect** because GKE Standard provides Kubernetes functionality and allows the team to deploy Kubernetes manifests, but it requires more infrastructure configuration and administration than GKE Autopilot. With GKE Standard, the team has greater control over node pools, machine types, node operating systems, networking settings, upgrades, scaling behavior, and other cluster-level components. That additional control is valuable when workloads require specialized node configurations or privileged capabilities, but it conflicts with the requirement to minimize infrastructure configuration. Because the scenario focuses on controlling Kubernetes workloads rather than managing the underlying nodes, GKE Autopilot is the more appropriate choice.

**D is incorrect** because Cloud Run functions is designed primarily for deploying event-driven, single-purpose functions rather than complete applications defined through Kubernetes manifests. It abstracts the underlying compute infrastructure and can respond to HTTP requests or events from Google Cloud services, but it does not provide direct management of Kubernetes objects or a Kubernetes cluster. The team would need to restructure the containerized application into functions and use the Cloud Run functions deployment model. This would not satisfy the requirement to retain control over a Kubernetes-based deployment.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/choose-cluster-mode](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/choose-cluster-mode)
- [docs.cloud.google.com/run/docs/deploying](https://docs.cloud.google.com/run/docs/deploying)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q15

> Northstar Clinic runs an appointment-processing application on a Compute Engine VM. Employees use the application from 8:30 AM until 5:30 PM, Monday through Friday. The operations team must create a disk backup every day for disaster recovery and automatically remove each backup after 35 days. The team wants to use the Google-recommended approach with minimal administration and no unnecessary services. What should the team do?  

- **A.** Add snapshot-schedule: 0 2 \* \* \* and snapshot-retention: 35 to the VM’s custom metadata.
- **B.** In the Google Cloud console, create a daily snapshot schedule for the VM’s disk, configure it to run between 2:00 AM and 3:00 AM, set the retention period to 35 days, and attach the schedule to the disk.
- **C.** Create one Cloud Run function to create disk snapshots and another Cloud Run function to delete snapshots older than 35 days, and invoke both functions daily by using Cloud Scheduler.
- **D.** Create scripts on the VM that copy the disk’s files to a Cloud Storage bucket and delete objects older than 35 days, and run the scripts daily by using cron.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Compute Engine does not create or retain scheduled disk snapshots based on custom VM metadata keys named snapshot-schedule and snapshot-retention. Custom metadata consists of key-value pairs that a VM or an application can read, but adding an arbitrary cron expression and retention value does not configure the Compute Engine snapshot service. Scheduled snapshots are configured through a snapshot schedule resource policy, which specifies the schedule frequency, start time, retention period, and deletion behavior. That resource policy must then be attached to the Persistent Disk or Hyperdisk volume that needs protection. Therefore, the proposed metadata values would not automatically create or delete any snapshots.

**B is correct** because Compute Engine provides managed snapshot schedules specifically for automatically backing up Persistent Disk and Hyperdisk volumes. The team can create a snapshot schedule resource policy, configure it to run once per day during a period of lower application activity, specify a 35-day retention policy, and attach the schedule to the VM’s disk. Compute Engine then creates the snapshots and automatically deletes scheduled snapshots after the configured retention period. This solution requires no custom code, VM-based cron jobs, Cloud Scheduler jobs, or Cloud Run functions. It therefore uses the fewest services and has the lowest management overhead. Scheduling the snapshot outside the application’s normal business hours can also reduce the likelihood of capturing the disk during periods of heavy write activity. For applications that require application-consistent backups, the team can additionally use guest-flush capabilities or an application-specific data-consistency process, but this does not change the fact that a managed snapshot schedule is the appropriate solution among the available options.

**C is incorrect** because custom Cloud Run functions and Cloud Scheduler jobs could use Compute Engine APIs to create and delete snapshots, but this design unnecessarily recreates capabilities already provided by managed snapshot schedules. The team would need to develop, deploy, secure, monitor, and maintain the functions; assign appropriate IAM permissions; configure API error handling and retries; and ensure that the deletion function identifies only the intended snapshots. Cloud Scheduler would introduce another service and additional configuration. This solution could technically meet the backup and retention requirements, but it does not satisfy the requirements for the least management overhead and the least number of services.

**D is incorrect** because copying files from inside the VM to Cloud Storage is not equivalent to creating a Compute Engine disk snapshot. A file-copy script might omit operating system data, hidden files, locked files, disk metadata, permissions, boot information, or files that change while the copy is running. Restoring an entire bootable disk from this collection of copied files would also require a custom recovery process. The team would be responsible for writing, testing, securing, monitoring, and maintaining both scripts and the cron configuration. The VM must remain operational for the backup scripts to run, so a VM failure could prevent the backup process itself from executing. Cloud Storage lifecycle management could reduce some deletion logic, but the overall design would still be more complex and less suitable for disk-level disaster recovery than a managed Compute Engine snapshot schedule.

**Reference links**

- [docs.cloud.google.com/compute/docs/disks/scheduled-snapshots](https://docs.cloud.google.com/compute/docs/disks/scheduled-snapshots)
- [docs.cloud.google.com/compute/docs/disks/about-snapshot-schedules](https://docs.cloud.google.com/compute/docs/disks/about-snapshot-schedules)
- [docs.cloud.google.com/compute/docs/disks/snapshot-best-practices](https://docs.cloud.google.com/compute/docs/disks/snapshot-best-practices)

**Related notes:** [Persistent Disk and snapshots](../03-compute-containers/products/persistent-disk-and-snapshots.md)

</details>

[Back to index](#index)

---

### Q16

> ArcadeWave operates an online gaming platform that receives match-result events from millions of players. Event traffic changes throughout the day and can increase suddenly during tournaments. The platform must ingest and process every event promptly while preventing traffic spikes from overwhelming the processing component. Which architecture should ArcadeWave use?  

- **A.** -Store the match-result events in Firestore.  
  -Use Cloud Scheduler to periodically invoke a Cloud Run function that processes the events.
- **B.** Send the match-result events directly to a dedicated Compute Engine instance for processing.
- **C.** Append the match-result events to a JSON file in Cloud Storage and process the file in a daily batch.
- **D.** Publish the match-result events to Pub/Sub and use the Pub/Sub topic to trigger a Cloud Run function.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Firestore is a scalable NoSQL document database, but combining it with Cloud Scheduler creates a polling-based batch workflow rather than an event-driven processing pipeline. Events would remain unprocessed until the next scheduled invocation, which introduces unnecessary latency. The function would also need logic to identify unprocessed records, prevent duplicate processing, update processing status, and efficiently scan or query the database. Firestore can be an appropriate destination for processed application data, but it is not the best service for buffering a variable stream of independent events before serverless processing. Pub/Sub provides the required messaging semantics and can immediately deliver each event to a processing function.

**B is incorrect** because sending events directly to one dedicated Compute Engine instance tightly couples event ingestion to the availability and capacity of that instance. A sudden increase in traffic could exceed the instance’s processing capacity, causing requests to fail or events to be lost unless the team builds its own buffering, retry, persistence, and scaling mechanisms. The instance would also become a potential single point of failure and would require operating system maintenance, monitoring, capacity planning, and availability management. Pub/Sub provides a managed buffer between the event producers and consumers, allowing events to continue being accepted even when the processing component is temporarily busy or unavailable.

**C is incorrect** because Cloud Storage is designed for storing objects rather than functioning as a real-time message queue. Continually appending independent events to one JSON object is not an efficient ingestion pattern because Cloud Storage objects are generally replaced rather than modified through concurrent record-level appends. Processing the data only once per day would also create substantial latency and would not satisfy the need to process events promptly. A failure involving the large batch could delay all events together, whereas Pub/Sub allows events to be delivered, acknowledged, retried, and processed independently.

**D is correct** because Pub/Sub is a scalable asynchronous messaging service designed to decouple event producers from event consumers. The website can publish every match-result event to a topic without waiting for the processing component to complete its work. Pub/Sub absorbs changes in the incoming event rate, retains messages that have not yet been acknowledged, and delivers them to subscribers as processing capacity becomes available. A Pub/Sub event can trigger a Cloud Run function, which can automatically scale across multiple instances to process events in parallel and scale down when traffic decreases. Pub/Sub also supports acknowledgment and redelivery behavior, improving reliability when processing fails temporarily. Because Pub/Sub commonly provides at-least-once delivery, the function should be designed to process duplicate events safely by using an event identifier or another idempotency mechanism.

**Reference links**

- [docs.cloud.google.com/pubsub/docs/overview](https://docs.cloud.google.com/pubsub/docs/overview)
- [docs.cloud.google.com/pubsub/docs/use-with-cloud-function-triggers](https://docs.cloud.google.com/pubsub/docs/use-with-cloud-function-triggers)
- [docs.cloud.google.com/firestore/native/docs](https://docs.cloud.google.com/firestore/native/docs)

**Related notes:** [Pub/Sub](../04-events-integration/products/pub-sub.md) · [Cloud Scheduler](../04-events-integration/products/cloud-scheduler.md)

</details>

[Back to index](#index)

---

### Q17

> MediLedger is deploying a patient appointment application on Google Cloud. The application requires a Cloud SQL for PostgreSQL database. Company policy requires all database connections to be encrypted and authenticated, and the application must use IAM database authentication instead of long-lived database passwords. The operations team also wants Google Cloud to manage certificates and authentication tokens wherever possible. What should the team do?  

- **A.** Deploy a Cloud SQL database with the SSL mode set to encrypted only, configure SSL/TLS client certificates, and configure a built-in database user and password.
- **B.** Deploy a Cloud SQL database with the SSL mode set to encrypted only, configure SSL/TLS client certificates, and configure IAM database authentication.
- **C.** Deploy a Cloud SQL database, configure IAM database authentication, and connect through the Cloud SQL Auth Proxy.
- **D.** Deploy a Cloud SQL database, configure a built-in database user and password, and connect through the Cloud SQL Auth Proxy.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because manually configuring SSL/TLS client certificates can create an encrypted connection, but the organization must distribute, store, rotate, and revoke those certificates. The application must also store and manage a database username and password. This approach does not integrate database login with IAM and introduces long-lived credentials that must be protected and rotated. Although it can provide encryption and authentication, it does not satisfy the requirements for IAM integration and minimal credential management.

**B is incorrect** because IAM database authentication removes the need for a conventional long-lived database password, but manually configuring SSL/TLS client certificates still requires the team to manage certificate generation, secure distribution, expiration, and rotation. In addition, a direct IAM database login generally requires the application or administrator to obtain and refresh short-lived OAuth 2.0 access tokens. This option can provide both encryption and IAM database authentication, but it requires more operational work than using the Cloud SQL Auth Proxy, which can manage the secure connection and automatic IAM authentication process.

**C is correct** because the Cloud SQL Auth Proxy provides an encrypted and authorized connection to Cloud SQL without requiring the application team to manually manage SSL/TLS certificates. The proxy uses IAM credentials to authorize access to the Cloud SQL instance and automatically creates a secure TLS connection using short-lived certificates. When automatic IAM database authentication is enabled, the proxy can also obtain and refresh the short-lived OAuth 2.0 access tokens used to log in to the database. The application connects to a local TCP port or Unix socket exposed by the proxy, while the proxy handles certificate management, connection authorization, encryption, and token refresh. This approach meets the encryption and authentication requirements, integrates with IAM, and minimizes operational management.

**D is incorrect** because the Cloud SQL Auth Proxy provides IAM-based connection authorization and encrypts traffic between the proxy and the Cloud SQL instance, so this option does provide a secure network connection with minimal certificate management. However, the application would still authenticate to the database by using a built-in database username and password. Those credentials would need to be stored, protected, rotated, and managed separately from IAM. Cloud SQL Auth Proxy authorization and database-user authentication are distinct layers. Because the requirement specifically calls for IAM-integrated database authentication and minimal credential management, IAM database authentication should be used instead of a long-lived database password.

**Reference links**

- [docs.cloud.google.com/sql/docs/postgres/sql-proxy](https://docs.cloud.google.com/sql/docs/postgres/sql-proxy)
- [docs.cloud.google.com/sql/docs/postgres/iam-authentication](https://docs.cloud.google.com/sql/docs/postgres/iam-authentication)
- [docs.cloud.google.com/sql/docs/postgres/connect-auth-proxy](https://docs.cloud.google.com/sql/docs/postgres/connect-auth-proxy)

**Related notes:** [Cloud SQL](../05-storage-databases-data/products/cloud-sql.md) · [Cloud SQL Auth Proxy](../02-identity-security/products/cloud-sql-auth-proxy.md)

</details>

[Back to index](#index)

---

### Q18

> NightPulse Media processes video analytics every evening by running a batch job across many Compute Engine VMs. The job saves progress regularly and continues successfully even when several worker VMs are interrupted. The company wants to significantly reduce the compute cost of future runs. What should NightPulse Media do?  

- **A.** -Test the workload’s ability to recover from VM interruptions.  
  -If the test succeeds, run future jobs on Spot VMs that use N1 standard machine types.
- **B.** -Test the workload during simulated host maintenance events.  
  -If the test succeeds, continue running future jobs on standard-priced N1 VMs.
- **C.** -Test the workload in a Managed Instance Group.  
  -If the test succeeds, run future jobs on standard-priced N1 VMs in the group.
- **D.** -Replace the current N2 VMs with standard-priced N1 VMs.  
  -If testing succeeds, use N1 VMs for all future jobs.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Spot VMs are designed for fault-tolerant workloads that can withstand unexpected VM termination, including distributed batch-processing jobs. Compute Engine can preempt a Spot VM at any time when it needs to reclaim capacity, but Spot VMs are available at substantially lower prices than standard VMs. Because this workload saves progress, tolerates the loss of some worker VMs, and runs as a nightly batch process, it is a strong match for the Spot provisioning model. Testing interruption handling first confirms that the job can retry failed tasks, resume from checkpoints, or redistribute work when a VM is preempted. The current Google Cloud terminology is Spot VMs; they are the recommended successor to preemptible VMs. Using N1 standard machine types with the Spot provisioning model preserves the required general-purpose resources while directly addressing the excessive VM cost.

**B is incorrect** because standard-priced N1 VMs do not provide the substantial cost reduction available from Spot VMs. Simulating a host maintenance event can test how an application responds to live migration or termination according to its host maintenance policy, but host maintenance is not the primary cost issue described in the scenario. Even if the test succeeds, continuing to use standard VMs means paying regular on-demand prices. This option does not take advantage of the workload’s ability to tolerate VM interruption and therefore misses the most relevant cost-optimization opportunity.

**C is incorrect** because a Managed Instance Group improves VM management by supporting features such as automated instance creation, autoscaling, autohealing, and standardized instance configuration, but using standard-priced N1 VMs within the group does not inherently provide the large pricing reduction required by the scenario. A Managed Instance Group could be configured to use Spot VMs and might be useful for automatically replacing interrupted workers, but this option explicitly continues using standard N1 VMs. It therefore adds infrastructure management capabilities without making effective use of the workload’s fault tolerance to reduce compute pricing.

**D is incorrect** because changing from N2 to N1 might alter the cost and performance characteristics of the workload, but it does not provide the same direct and significant cost reduction as moving from standard provisioning to Spot provisioning. N1 is an older general-purpose machine series, and selecting it solely because it might have a lower nominal price does not guarantee the best price-performance ratio. The workload’s most important characteristic is its tolerance for VM termination, which makes the provisioning model more relevant than merely switching machine series. Spot VMs can use supported machine types while offering discounted pricing in exchange for the possibility of preemption.

**Reference links**

- [cloud.google.com/compute/docs/instances/spot](https://cloud.google.com/compute/docs/instances/spot)
- [cloud.google.com/compute/docs/instances/preemptible](https://cloud.google.com/compute/docs/instances/preemptible)
- [cloud.google.com/compute/docs/general-purpose-machines](https://cloud.google.com/compute/docs/general-purpose-machines)

**Related notes:** [Spot VMs](../03-compute-containers/products/spot-vms.md)

</details>

[Back to index](#index)

---

### Q19

> BluePeak Games has several software engineering teams based in the United States. Each team uses a separate Google Cloud project for development workloads. BluePeak Games wants to centrally prevent these teams from creating supported regional resources outside United States locations. What should BluePeak Games do?  

- **A.** Place all development projects in a common folder, and enforce an organization policy on that folder that allows resource creation only in United States locations.
- **B.** Create a separate organization resource for the development projects, and configure an Identity and Access Management policy that limits resource creation to United States regions.
- **C.** Configure an Identity and Access Management policy that permits only United States resource locations, and apply the policy separately to every development project.
- **D.** Configure an Identity and Access Management policy that restricts resource locations, and attach the policy to every development team role.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Organization Policy Service provides the Resource locations constraint, identified as constraints/gcp.resourceLocations, which controls the locations where supported Google Cloud resources can be created. BluePeak Games can create a folder containing all development projects and apply a single organization policy to that folder with an allowed value such as in:us-locations. Organization policies are inherited through the Google Cloud resource hierarchy, so all projects inside the folder inherit the location restriction unless a lower-level policy is configured in accordance with the applicable policy rules. This centralized design is easier to manage than applying an individual policy to every project and automatically covers new development projects added to the folder. The constraint applies to supported resources for which a location can be selected. It is not retroactive, does not relocate existing resources, and generally does not restrict global resources or services that do not support the constraint.

**B is incorrect** because Identity and Access Management controls authorization by determining which principals can perform particular actions on particular resources. An IAM policy does not define the geographic regions in which resources can be created. Resource-location restrictions are governance requirements implemented through Organization Policy Service rather than IAM. Creating another organization resource is also unnecessary and would introduce additional administrative complexity. The existing organization can contain a dedicated folder for development projects, and the location organization policy can be applied at that folder.

**C is incorrect** because an IAM policy cannot specify that cloud resources may be created only in United States locations. IAM roles and policies grant or deny permissions such as creating Compute Engine instances or Cloud Storage buckets, but they do not evaluate the requested deployment location as an organizational location constraint. Applying IAM policies separately to every project would also create repetitive administrative work and increase the possibility of inconsistent configuration. The appropriate solution is to group the projects in a folder and apply the Resource locations organization policy once at the folder level.

**D is incorrect** because IAM roles represent sets of permissions and cannot be configured with a general restriction that limits supported Google Cloud resource locations to the United States. Applying policies to development roles would focus on user authorization rather than enforcing a resource-governance rule across the projects. It could also fail to cover resources created by service accounts, automation systems, or other principals that use different roles. Applying the Resource locations organization policy to the folder provides consistent enforcement for resource-creation requests within every descendant development project, regardless of which authorized principal submits the request.

**Reference links**

- [docs.cloud.google.com/organization-policy/restrict-locations](https://docs.cloud.google.com/organization-policy/restrict-locations)
- [docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy](https://docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)
- [docs.cloud.google.com/iam/docs/overview](https://docs.cloud.google.com/iam/docs/overview)

**Related notes:** [Organization Policy Service](../02-identity-security/products/organization-policy-service.md)

</details>

[Back to index](#index)

---

### Q20

> BrightCart runs an order-processing service on a Compute Engine VM. The VM uses the Compute Engine default service account, which still has the Editor role from a legacy project setup. The service only retrieves the value of one Secret Manager secret and publishes order events to one Pub/Sub topic. BrightCart wants to apply the principle of least privilege and avoid storing credentials on the VM. What should the cloud administrator do?  

- **A.** Retain the Editor role and use OAuth access scopes to block access to unnecessary Google Cloud APIs.
- **B.** Grant the Compute Engine default service account the Organization Administrator role so that its permissions are consistently inherited.
- **C.** Create a service account key, copy the key file to the VM, and configure the application to use that key.
- **D.** Create and attach a dedicated user-managed service account, grant it access only to the required Secret Manager secret and Pub/Sub topic, and remove the Editor role from the default service account.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because OAuth access scopes are not a suitable replacement for fine-grained IAM permissions. Access scopes provide an additional authorization boundary for credentials obtained through a Compute Engine VM, but they are coarse-grained and cannot precisely restrict access to an individual Secret Manager secret or Pub/Sub topic. A request from the VM must be allowed by both the service account’s IAM permissions and the VM’s access scopes, but retaining the Editor role still leaves the default service account with broad project-level permissions. Access scopes can also be changed during VM reconfiguration and do not adequately protect the account when it is used from another resource. Google Cloud recommends using a dedicated service account with narrowly scoped IAM roles rather than relying on access scopes to compensate for an overprivileged service account. The VM can use the cloud-platform access scope while IAM policies enforce the actual resource-level authorization.

**B is incorrect** because the Organization Administrator role is far more privileged than the application requires. It provides administrative control over organization-level resources and policies and does not make permissions safer or more predictable. Granting it to a runtime service account would substantially increase the potential impact of application compromise, remote code execution, or misuse of the VM’s credentials. IAM inheritance is already predictable: permissions granted at the organization, folder, and project levels are inherited by descendants. The correct security approach is to avoid unnecessary inherited permissions and grant the application only the permissions required for its workload.

**C is incorrect** because a service account key is a long-lived credential that must be securely stored, protected, monitored, and rotated. Copying a JSON key file to the VM creates an unnecessary credential-management risk because anyone who obtains the file can potentially impersonate the service account from another system. A Compute Engine workload does not need a downloaded key when a service account is attached to the VM. The application can use Application Default Credentials to obtain short-lived credentials automatically from the Compute Engine metadata server. This avoids embedding credentials, reduces the risk of key leakage, and lets Google Cloud manage credential issuance and rotation.

**D is correct** because it combines keyless authentication with the principle of least privilege. BrightCart should create a single-purpose user-managed service account for the order-processing application and attach it to the Compute Engine VM. The service account should receive the Secret Manager Secret Accessor role, roles/secretmanager.secretAccessor, on only the required secret and the Pub/Sub Publisher role, roles/pubsub.publisher, on only the required topic. Resource-level grants are preferable to project-level grants because they prevent the application from reading other secrets or publishing to unrelated topics. The application can then use Application Default Credentials and obtain short-lived access tokens through the VM’s metadata server without storing a service account key. After verifying that no other workload depends on the Compute Engine default service account’s Editor role, the team should remove that broad grant. The organization can also enforce the Disable Automatic IAM Grants for Default Service Accounts organization policy constraint to prevent similar broad grants in future projects.

**Reference links**

- [docs.cloud.google.com/iam/docs/best-practices-service-accounts](https://docs.cloud.google.com/iam/docs/best-practices-service-accounts)
- [docs.cloud.google.com/secret-manager/docs/manage-access-to-secrets](https://docs.cloud.google.com/secret-manager/docs/manage-access-to-secrets)
- [docs.cloud.google.com/pubsub/docs/access-control](https://docs.cloud.google.com/pubsub/docs/access-control)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md) · [Secret Manager](../02-identity-security/products/secret-manager.md)

</details>

[Back to index](#index)

---

### Q21

> PixelForge Studio is preparing a Compute Engine batch-rendering service in asia-southeast1. The selected NVIDIA GPU type is supported only in specific zones, and the new Google Cloud project has not previously provisioned GPU resources. The cloud engineer wants to avoid deployment failures when the production managed instance group is launched from an instance template. What should the engineer do before creating the template?  

- **A.** Treat Compute Engine as globally uniform and assume the GPU type can be provisioned in every zone.
- **B.** Create the instance template immediately and allow autoscaling to obtain any missing GPU quota.
- **C.** Remove the regional quota controls so that GPU provisioning is unrestricted.
- **D.** Check which zones support the GPU type and verify or request the necessary regional accelerator and global GPU quotas beforehand.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Compute Engine is a global Google Cloud service, but its physical resources are not uniformly available in every location. GPU model availability varies by region and zone, and some accelerator-optimized machine types are offered only in selected locations. A configuration that specifies an unsupported GPU type, machine series, or zone cannot be deployed successfully merely because Compute Engine itself is globally accessible. The engineer must therefore verify that the chosen GPU and its compatible machine configuration are available in the intended zone.

**B is incorrect** because creating an instance template does not cause Compute Engine autoscaling to request or approve additional quota. An autoscaler can increase or decrease the number of VM instances according to workload demand, but every new instance must still comply with the project’s existing resource quotas. When the required GPU quota is unavailable, scale-out operations can fail even though the instance template and autoscaling policy are valid. Quota requests should be submitted and approved before the production workload depends on those resources.

**C is incorrect** because Google Cloud quotas are service-enforced resource controls and cannot simply be disabled by a project administrator. GPU-related quotas can include a regional quota for the selected GPU model and a global quota that limits the total number of GPUs used by the project across all regions. The appropriate action is to review current quota values and request increases where necessary, not attempt to remove quota enforcement.

**D is correct** because a successful GPU deployment depends on both location support and sufficient quota. The engineer should first confirm that the selected GPU model and compatible machine type are available in a suitable zone within asia-southeast1. The engineer should then inspect the project’s regional quota for that GPU model and its global GPU quota, requesting increases before production deployment when either value is insufficient. Performing these checks before defining and using the instance template reduces the risk that managed instance group creation or autoscaling will fail because of an unsupported zone or exhausted quota. Quota availability does not guarantee that physical GPU capacity will always be available, so capacity planning or reservations might also be appropriate for a critical production workload.

**Reference links**

- [docs.cloud.google.com/compute/docs/regions-zones/gpu-regions-zones](https://docs.cloud.google.com/compute/docs/regions-zones/gpu-regions-zones)
- [docs.cloud.google.com/compute/docs/gpus/create-vm-with-gpus](https://docs.cloud.google.com/compute/docs/gpus/create-vm-with-gpus)
- [docs.cloud.google.com/compute/quotas-limits](https://docs.cloud.google.com/compute/quotas-limits)

**Related notes:** [Compute Engine](../03-compute-containers/products/compute-engine.md)

</details>

[Back to index](#index)

---

### Q22

> BrightCart, an online retail company, requires every Google Cloud resource to follow approved settings for networking, encryption, Identity and Access Management, labels, and logging. Platform engineers need to provide software teams with a reusable method for deploying and updating resources while consistently applying these security standards. What should the platform engineers do?  

- **A.** Develop Java packages that use the Cloud Client Libraries for Java to create configured Google Cloud resources, and distribute the packages through a source code repository.
- **B.** Develop bash scripts that use the Google Cloud CLI to create configured Google Cloud resources, and distribute the scripts through a source code repository.
- **C.** Create curl command templates that call Google Cloud APIs to create configured Google Cloud resources, and distribute the templates through a source code repository.
- **D.** Develop reusable Terraform modules that use the Terraform provider for Google Cloud to define configured resources, and distribute the modules through a source code repository.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Cloud Client Libraries for Java can programmatically create and configure Google Cloud resources, but custom Java packages are not the most suitable mechanism for standardizing infrastructure deployment. The platform team would need to develop application code for resource creation, implement dependency management, authentication, error handling, update logic, rollback behavior, and state tracking. Engineers would also need Java knowledge and would have to understand how the custom packages operate. A custom library does not naturally provide Terraform capabilities such as declarative configuration, execution plans, dependency graphs, reusable infrastructure modules, and managed state. Although the packages could encode approved settings, maintaining an internally developed infrastructure framework would require substantially more effort than using a purpose-built infrastructure as code solution.

**B is incorrect** because bash scripts using the Google Cloud CLI can automate resource creation, but scripts are generally imperative and describe a sequence of commands rather than the desired final state of the infrastructure. Engineers would need to implement logic for detecting existing resources, applying updates, handling partial failures, preserving idempotency, managing dependencies, and recovering from failed operations. As the number of resources and security requirements grows, scripts can become difficult to test, review, reuse, and maintain. Storing scripts in a source code repository provides version control, but it does not provide the standardized module interfaces, state management, dependency resolution, and change-planning capabilities that Terraform provides.

**C is incorrect** because Google Cloud APIs can create and update resources, but invoking them directly through curl requires engineers to manage authentication tokens, request payloads, API versions, operation polling, dependencies, retries, error handling, and update behavior. Curl commands are low-level and imperative, making them difficult to use as a scalable, reusable infrastructure standard. They also do not automatically track deployed infrastructure or compare the current environment with the approved configuration. Although storing command templates in a repository would permit version control, the organization would effectively be building and maintaining its own infrastructure deployment framework rather than using an established infrastructure as code tool.

**D is correct** because Terraform modules provide reusable, declarative building blocks for creating and managing Google Cloud resources. The platform team can define mandatory security settings, such as encryption configurations, approved networks, logging controls, labels, service accounts, and access restrictions, inside each module. Software engineers can then deploy approved resources by supplying only the permitted input variables instead of configuring every underlying resource property themselves. Terraform uses state to track managed resources, builds a dependency graph, generates an execution plan before changes are applied, and supports predictable updates to existing infrastructure. Storing the modules in a source code repository enables version control, peer review, automated testing, controlled releases, and reuse across multiple projects and teams. The organization can also integrate the modules into a CI/CD pipeline and add policy validation to detect configurations that violate security requirements. This makes reusable Terraform modules the most maintainable and scalable mechanism for enforcing preconfigured deployment standards.

**Reference links**

- [docs.cloud.google.com/docs/terraform/terraform-overview](https://docs.cloud.google.com/docs/terraform/terraform-overview)
- [docs.cloud.google.com/docs/terraform/best-practices/reusable-modules](https://docs.cloud.google.com/docs/terraform/best-practices/reusable-modules)
- [docs.cloud.google.com/docs/terraform/blueprints/terraform-blueprints](https://docs.cloud.google.com/docs/terraform/blueprints/terraform-blueprints)

**Related notes:** [Terraform](../08-iac-platform-ai/products/terraform.md)

</details>

[Back to index](#index)

---

### Q23

> Northstar Health operates separate Google Cloud environments for its clinical, finance, and research divisions. Each division must enforce its own security restrictions and centrally route logs from all projects. Developers have the Project Owner role on their respective projects, but they must not be able to modify or delete these security controls. How should the cloud administrator structure and configure the resources?  

- **A.** -Include the division name in every project name.  
  -Apply organization policies at the organization level and create log sinks in each project.
- **B.** -Include the division name in every project name.  
  -Apply organization policies and create log sinks separately in each project.
- **C.** -Place each division’s projects in a dedicated folder.  
  -Apply organization policies and create aggregated log sinks at the corresponding folder level.
- **D.** -Place each division’s projects in a dedicated folder.  
  -Apply organization policies at the organization level and create aggregated log sinks at the corresponding folder level.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a project naming convention does not establish a resource hierarchy or provide a policy-enforcement boundary. Applying organization policies only at the organization level would apply common restrictions across the organization and would not conveniently support different security requirements for each division. In addition, log sinks created directly within projects are project-level resources. Users with the necessary project-level administrative permissions, including broadly privileged Project Owners, could modify or delete those sinks. Therefore, this design does not adequately protect the logging configuration from project users and does not provide department-specific organization policies.

**B is incorrect** because configuring organization policies and log sinks directly on individual projects places the controls at the same resource level where the Project Owners have administrative access. Depending on their assigned permissions, these users could change project-level organization policy settings or modify and delete project-level log sinks. This option would also require administrators to configure and maintain the same controls separately for every project, increasing operational overhead and the possibility of inconsistent configurations. A naming convention helps identify which division owns a project, but it does not cause policies or logging configurations to be inherited and does not prevent project users from changing project-level resources.

**C is correct** because folders provide administrative and policy boundaries within the Google Cloud resource hierarchy. The administrator can create one folder for each division, place that division’s projects beneath it, and apply the division-specific organization policies to the folder. Projects under the folder inherit the applicable organization policies, allowing each division to have different security restrictions without configuring every project individually. The administrator can also create an aggregated log sink at each folder level to route logs generated by the projects and resources beneath that folder to an approved destination. A user who has the Project Owner role only on a child project does not automatically receive permissions on the parent folder. Consequently, project-level owners cannot modify or delete the organization policies or aggregated log sinks configured on the folder. This arrangement provides centralized enforcement, inheritance, separation between divisions, and protection from project-level administrators.

**D is incorrect** because organizing projects into division-specific folders and creating aggregated log sinks on those folders would correctly centralize and protect the logging configuration. However, applying the organization policies only at the organization level would impose the same baseline policy configuration across all folders and projects. The requirement states that the security policies differ for each division. To enforce distinct configurations, the relevant organization policies must be applied at each division’s folder level. Organization-level policies can still be used for requirements that apply universally, but they do not by themselves satisfy the need for different policies for each division.

**Reference links**

- [docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy](https://docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)
- [docs.cloud.google.com/organization-policy/overview](https://docs.cloud.google.com/organization-policy/overview)
- [docs.cloud.google.com/logging/docs/export/aggregated_sinks_overview](https://docs.cloud.google.com/logging/docs/export/aggregated_sinks_overview)

**Related notes:** [Organization Policy Service](../02-identity-security/products/organization-policy-service.md) · [Cloud Logging](../07-operations-cost/products/cloud-logging.md)

</details>

[Back to index](#index)

---

### Q24

> PulseGrid Energy receives continuous telemetry from thousands of smart meters deployed across several countries. The application needs a globally scalable database for large volumes of time-series sensor data, high read and write throughput, and sub-millisecond read latency for frequently accessed measurements. Which storage solution should PulseGrid Energy use?  

- **A.** Store the telemetry in Spanner and add application-managed caches to reduce database latency.
- **B.** Store the telemetry in Bigtable by using the Enterprise Plus edition and its integrated in-memory tier.
- **C.** Stream the telemetry directly into BigQuery datasets and use BigQuery as the operational database.
- **D.** Store the telemetry as objects in Cloud Storage and use Cloud CDN to cache frequently requested measurements.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Spanner is primarily designed for globally distributed, strongly consistent workloads that require relational schemas, SQL queries, secondary indexes, and ACID transactions. Although Spanner provides high availability, horizontal scalability, and low-latency regional access, those capabilities are more appropriate when the application needs transactional consistency across related records. Raw IoT telemetry normally consists of massive quantities of timestamped, single-keyed measurements and does not generally require complex multi-row transactions. Adding an application-managed cache could improve some read operations, but it would create additional infrastructure, cache invalidation logic, consistency concerns, and operational complexity. A cache also does not change the inherent latency characteristics of the underlying Spanner database or guarantee that all requested sensor records will be served with sub-millisecond latency. Bigtable is more directly optimized for high-throughput time-series and IoT workloads.

**B is correct** because Bigtable is a fully managed, massively scalable, wide-column NoSQL database designed for large volumes of single-keyed data and high-throughput, low-latency reads and writes. IoT sensor data is a common Bigtable use case because measurements can be organized efficiently by device identifier, time range, and other predictable row-key components. Bigtable can scale to billions of rows and petabytes of data while maintaining performance as additional compute capacity is added. It also supports replication across clusters and regions, allowing applications in multiple geographic areas to access the data while improving availability and disaster resilience. For the explicit sub-millisecond requirement, Bigtable Enterprise Plus provides an integrated in-memory tier that supports sub-millisecond read latency for hot data. This makes Bigtable the best option among the listed choices for globally scalable, operational access to high-volume sensor measurements. The table schema and row-key design must still distribute traffic evenly to avoid hotspots, and the company should validate the required latency under its actual workload.

**C is incorrect** because BigQuery is a serverless analytics platform and data warehouse rather than a low-latency operational database for individual sensor lookups. It is well suited to storing and analyzing very large telemetry datasets, running SQL aggregations, identifying long-term patterns, creating reports, and training analytical models. BigQuery also supports streaming ingestion, so sensor events can be made available for analysis soon after they arrive. However, query execution is optimized for scanning and analyzing large datasets, not for consistently serving individual application requests with sub-millisecond latency. PulseGrid Energy could export or stream historical Bigtable data into BigQuery for analytical workloads, but BigQuery should not replace Bigtable as the latency-sensitive operational data store.

**D is incorrect** because Cloud Storage is an object storage service intended for files and other unstructured objects rather than fine-grained, low-latency database access to individual sensor measurements. Storing telemetry in objects could be appropriate for archival data, batch-processing input, backups, or a data lake, but applications would need to retrieve and process entire objects or ranges rather than efficiently reading individual rows by device and timestamp. Cloud CDN is designed primarily to cache cacheable HTTP content near users at edge locations. It does not convert Cloud Storage into a high-throughput time-series database, and cache hits would depend on previously requested content, cache keys, expiration settings, and cacheability. Newly written or infrequently requested sensor values could still require origin access, so this architecture would not provide dependable sub-millisecond access to operational telemetry. It would also make frequent updates and fine-grained queries more difficult than using Bigtable.

**Reference links**

- [docs.cloud.google.com/bigtable/docs/overview](https://docs.cloud.google.com/bigtable/docs/overview)
- [docs.cloud.google.com/bigtable/docs/editions-overview](https://docs.cloud.google.com/bigtable/docs/editions-overview)
- [docs.cloud.google.com/bigquery/docs/introduction](https://docs.cloud.google.com/bigquery/docs/introduction)

**Related notes:** [Bigtable](../05-storage-databases-data/products/bigtable.md)

</details>

[Back to index](#index)

---

### Q25

> BrightForge Media uses a Jenkins deployment server that authenticates to Google Cloud with a service account. Deployments to the production project are failing because the service account might not have the required permissions. The platform administrator needs to verify the IAM roles granted to the service account in that project, including roles inherited through the resource hierarchy. What should the administrator do?  

- **A.** Open the IAM page in the Google Cloud console for the production project and review the roles granted directly to the service account or inherited from its parent folder and organization.
- **B.** Open the Organization Policies page in the Google Cloud console and review the constraints applied to the production project.
- **C.** Open Policy Analyzer in the Google Cloud console and query every Google Cloud resource that the service account might be able to access.
- **D.** Open Logs Explorer in the Google Cloud console and search Cloud Audit Logs for permission-denied events associated with the service account.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the IAM page for the specific project provides the most direct way to inspect which IAM roles are granted to the CI/CD service account. IAM access can be granted directly on the project or inherited from a parent folder or organization. A role binding created at a higher level of the Google Cloud resource hierarchy applies to descendant resources, so checking only project-level bindings might not reveal all of the service account’s effective role grants. By reviewing the service account under IAM for the production project and including inherited role grants, the administrator can determine whether it has the roles containing the permissions required by the deployment process. The administrator should also remember that having permission to authenticate as or impersonate a service account is different from the permissions granted to that service account on project resources.

**B is incorrect** because organization policies and IAM policies serve different purposes. Organization Policy Service constraints control how resources can be configured or used, such as restricting resource locations, external IP addresses, service account key creation, or allowed domains. They do not provide the primary view of IAM roles granted to a service account. An organization policy could potentially block a deployment operation even when the service account has sufficient IAM permissions, but reviewing organization policies does not directly validate whether the service account has the appropriate roles in the specified project. The administrator should inspect IAM role bindings first because the reported issue is related to the service account’s permissions.

**C is incorrect** because Policy Analyzer is intended to analyze access relationships and answer broader questions about which principals can access resources or which resources a principal might access. It can be useful for security investigations and access reviews, but querying every resource that the service account can access is broader than necessary and does not provide the simplest way to verify the roles granted in one known project. Access analysis can also depend on the query scope, the selected permissions, and the administrator’s own permission to inspect applicable policies. For this requirement, directly reviewing the project’s IAM policy and inherited role grants is faster and more targeted.

**D is incorrect** because Cloud Audit Logs can help identify individual failed operations, the service account that initiated them, and sometimes the permission associated with a permission-denied response. This information can be valuable after identifying a specific failing API request. However, audit logs provide evidence of operations that were attempted; they do not provide a complete list of the service account’s assigned or inherited IAM roles. Some relevant Data Access logs might also require configuration or additional permissions to view, and the absence of a permission-denied event does not prove that the service account has all required permissions. Therefore, logs can supplement troubleshooting but are not the best method for directly validating the service account’s role assignments.

**Reference links**

- [docs.cloud.google.com/iam/docs/granting-changing-revoking-access](https://docs.cloud.google.com/iam/docs/granting-changing-revoking-access)
- [docs.cloud.google.com/iam/docs/resource-hierarchy-access-control](https://docs.cloud.google.com/iam/docs/resource-hierarchy-access-control)
- [docs.cloud.google.com/policy-intelligence/docs/troubleshoot-access](https://docs.cloud.google.com/policy-intelligence/docs/troubleshoot-access)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q26

> FreshBasket, an online grocery platform, runs PostgreSQL database VMs in data-subnet. Its checkout application VMs and public web VMs run in services-subnet within the same VPC network. The VMs can be replaced frequently, so their internal IP addresses might change. FreshBasket must allow TCP port 5432 to the database VMs only from the checkout application VMs, not from the web VMs. No other firewall rule permits this database port. What should the cloud administrator do?  

- **A.** Create checkout-sa and postgres-sa service accounts; attach checkout-sa to the checkout application VMs and postgres-sa to the database VMs; create an ingress firewall rule that allows TCP port 5432 from source service account checkout-sa to target service account postgres-sa.
- **B.** Create checkout-app and postgres-db network tags; assign the tags to the corresponding VMs; create an egress firewall rule that allows traffic from source network tag checkout-app to destination network tag postgres-db.
- **C.** Create checkout-sa and a postgres-db network tag; attach checkout-sa to the checkout application VMs and postgres-db to the database VMs; create an ingress firewall rule that allows TCP port 5432 from the entire services-subnet IP range to the data-subnet IP range.
- **D.** Create a checkout-app network tag and postgres-sa service account; assign the tag to the checkout application VMs and the service account to the database VMs; create an egress firewall rule that allows traffic from source network tag checkout-app to destination service account postgres-sa.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because VPC firewall rules support using source service accounts and target service accounts together in an ingress rule. The checkout-sa source service account identifies the checkout application VMs that are permitted to initiate the connection, while the postgres-sa target service account limits the rule’s application to the database VMs. Restricting the rule to TCP port 5432 ensures that only the required PostgreSQL traffic is allowed. This approach is more reliable than using internal IP addresses because the rule continues to identify the intended VM workloads when instances are recreated or their IP addresses change. Google Cloud VPC firewall rules are stateful, so response packets associated with an allowed database connection are automatically permitted. In an actual default VPC network, the administrator must also review the preconfigured default-allow-internal rule because that broader rule might already allow internal traffic. To enforce true exclusivity, any overlapping permissive rule must be removed, narrowed, or otherwise prevented from allowing the same database traffic.

**B is incorrect** because an egress VPC firewall rule cannot identify its destination by using a destination network tag. For an egress rule, target network tags identify the VM instances to which the outbound rule applies; they do not identify the destination VMs receiving the traffic. Egress destinations are normally specified through destination IP ranges or other supported destination parameters. Source and target network tags can be used together with an ingress rule, where the source tag identifies the initiating VMs and the target tag identifies the receiving VMs, but the egress construction described in this option is not valid for selecting postgres-db-tagged VMs as destinations. A tag-based ingress rule could solve the requirement, but that is not the rule proposed here.

**C is incorrect** because allowing traffic from the complete services-subnet IP range would include both the checkout application VMs and the public web VMs. It therefore fails the requirement that only checkout application servers be allowed to connect to the databases. A subnet IP range identifies network locations rather than workload identities, so any current or future VM using an address in that subnet could match the rule. In addition, classic VPC ingress firewall rules select destination VM interfaces through targets such as all instances, target network tags, or target service accounts; they do not use a destination subnet IP range as a substitute for a target. Mixing a source service account with a target network tag in the same VPC firewall rule is also not supported. Using matching source and target service accounts, as described in option A, provides the required workload-level restriction.

**D is incorrect** because an egress VPC firewall rule cannot use a service account as the identity of the remote destination VM. A target service account in an egress rule identifies the source VM instances to which the egress rule applies, not the database VMs receiving the connection. Similarly, the checkout-app network tag would need to be used as the target of an egress rule to select the VMs whose outbound traffic is controlled; it would not be specified as a source tag in the manner described. VPC firewall rules also prohibit unsupported combinations of network tags and service accounts. To use workload identities at both ends of a connection, the appropriate construction is an ingress rule with checkout-sa as the source service account and postgres-sa as the target service account.

**Reference links**

- [cloud.google.com/firewall/docs/firewalls](https://cloud.google.com/firewall/docs/firewalls)
- [cloud.google.com/firewall/docs/using-firewalls](https://cloud.google.com/firewall/docs/using-firewalls)
- [cloud.google.com/vpc/docs/vpc](https://cloud.google.com/vpc/docs/vpc)

**Related notes:** [Firewall, Hierarchical Policies, and Secure Tags (Cloud NGFW)](../06-networking/products/firewall-hierarchical-policies-and-secure-tags.md)

</details>

[Back to index](#index)

---

### Q27

> VistaMetrics runs a data-processing application in a Google Kubernetes Engine Standard cluster. The application’s existing pods run on four n1-standard-2 nodes. The company must deploy additional memory-intensive pods that require n2-highmem-16 nodes while keeping the existing application available. What should the platform team do?  

- **A.** Run gcloud container clusters upgrade on the existing cluster, and then deploy the additional pods.
- **B.** Add a node pool that uses the n2-highmem-16 machine type to the existing cluster, and then deploy the additional pods to that node pool.
- **C.** Create another cluster that contains only n2-highmem-16 nodes, redeploy all existing and additional pods to it, and then delete the original cluster.
- **D.** Create another cluster with separate n1-standard-2 and n2-highmem-16 node pools, redeploy all pods to it, and then delete the original cluster.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because gcloud container clusters upgrade is used to upgrade the Kubernetes version of a GKE cluster’s control plane or node pools. It does not change the machine type of the existing nodes or add a different class of nodes for memory-intensive workloads. Nodes within a single node pool share the same configuration, including their Compute Engine machine type. Therefore, upgrading the cluster would not provide n2-highmem-16 capacity for the additional pods. It could also initiate unnecessary node upgrade operations that are unrelated to the workload requirement.

**B is correct** because a GKE Standard cluster can contain multiple node pools with different machine types and configurations. The team can leave the existing n1-standard-2 node pool and its running pods unchanged while adding a new node pool that uses n2-highmem-16 machines. After the new nodes become ready, the additional memory-intensive pods can be scheduled onto that node pool. The team can use the automatically assigned cloud.google.com/gke-nodepool node label, a custom node label, nodeSelector, node affinity, or taints and tolerations to ensure that the new pods run on the intended nodes. Because the original pods continue running on the existing node pool while the new node pool is created, this approach supports deployment without application downtime and avoids the complexity of migrating the entire cluster.

**C is incorrect** because creating a separate cluster and redeploying all workloads introduces unnecessary migration work and operational risk. The team would need to reproduce cluster networking, identity and access settings, Kubernetes objects, secrets, policies, monitoring configuration, ingress resources, and other dependencies. Traffic would also need to be shifted from the original cluster to the new cluster without interrupting users. A cluster containing only n2-highmem-16 nodes would require the existing workloads to use the larger and potentially more expensive machine type even though they already run successfully on n1-standard-2 nodes. GKE node pools are specifically designed to allow heterogeneous node configurations within one Standard cluster, so a new cluster is not required.

**D is incorrect** because a cluster with both n1-standard-2 and n2-highmem-16 node pools could technically support both workload types, but creating an entirely new cluster is unnecessary. The existing cluster can already support the same architecture by adding an n2-highmem-16 node pool. Redeploying all pods and deleting the original cluster would add migration complexity and create a greater possibility of downtime due to configuration differences, traffic cutover problems, or missing dependencies. Adding a node pool to the current cluster is simpler, preserves the running workloads, and directly satisfies the requirement.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/node-pools](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/node-pools)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/node-pools](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/node-pools)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/migrate-nodes](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/migrate-nodes)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q28

> GlobeTix is building a ticket-reservation platform for customers in several continents. The platform requires a relational database that can process strongly consistent transactions, expand horizontally as traffic increases, and reduce the operational work performed by the engineering team. Which Google Cloud service should GlobeTix use?  

- **A.** Migrate the application database to Cloud SQL.
- **B.** Migrate the application database to Spanner.
- **C.** Store the application data in Firestore.
- **D.** Load the application data into BigQuery.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Cloud SQL is a fully managed relational database service for MySQL, PostgreSQL, and SQL Server, and it reduces administrative work such as installation, maintenance, backups, and patching. However, Cloud SQL is primarily designed around regional database instances. It supports larger machine configurations, read replicas, and high availability, but it does not provide the same native horizontal scaling and globally distributed, strongly consistent transactional architecture as Spanner. Cloud SQL is suitable when an application requires a conventional relational database engine and its workload can operate within the scaling limits of an instance-based database. It is not the Google-recommended choice for this scenario because GlobeTix specifically requires relational transactions at global scale.

**B is correct** because Spanner is a fully managed, horizontally scalable database designed for mission-critical applications. It provides relational schemas, SQL support, ACID transactions, strong transactional consistency, synchronous replication, and high availability. Spanner can distribute data across regions while presenting the application with a logically unified database. Its architecture allows the database to scale by adding compute capacity rather than requiring the company to manually divide the application into independent database shards. Google Cloud also handles infrastructure provisioning, replication, maintenance, and many availability-related operations. These capabilities satisfy GlobeTix’s requirements for a relational database that can support rapidly growing global traffic while minimizing database administration.

**C is incorrect** because Firestore is a fully managed, serverless NoSQL document database rather than a relational database. It can automatically scale and is well suited to mobile, web, and server applications that naturally represent their data as documents and collections. However, choosing Firestore would require GlobeTix to redesign its relational schema, relationships, joins, and access patterns around a document-oriented data model. Although Firestore can support transactions, its data model and query capabilities are different from those of a relational database. Because the requirement explicitly calls for a globally scalable relational database, Spanner is the more appropriate choice.

**D is incorrect** because BigQuery is a fully managed, serverless data platform designed primarily for analytics, data warehousing, business intelligence, and large-scale analytical queries. It is an excellent choice for analyzing historical ticket sales, customer behavior, revenue trends, and operational metrics. However, it is not intended to serve as the primary transactional relational database behind a ticket-reservation application that performs frequent record-level reads and writes. GlobeTix could export or replicate operational data into BigQuery for analytics, but it should use Spanner as the transactional system of record.

**Reference links**

- [docs.cloud.google.com/spanner/docs](https://docs.cloud.google.com/spanner/docs)
- [docs.cloud.google.com/docs/databases](https://docs.cloud.google.com/docs/databases)
- [docs.cloud.google.com/bigquery/docs/introduction](https://docs.cloud.google.com/bigquery/docs/introduction)

**Related notes:** [Spanner](../05-storage-databases-data/products/spanner.md)

</details>

[Back to index](#index)

---

### Q29

> HarborView Media hosts its public website behind a Google Cloud load balancer with a reserved IPv4 address. The company manages the oceanstream.io domain in Cloud DNS and wants oceanstream.io, www.oceanstream.io, and portal.oceanstream.io to direct users to the same load balancer. What should HarborView Media do?  

- **A.** Create a CNAME record that maps oceanstream.io to the load balancer, and create A records that map www.oceanstream.io and portal.oceanstream.io to oceanstream.io.
- **B.** Create a CNAME record that maps oceanstream.io to the load balancer, and create AAAA records that map www.oceanstream.io and portal.oceanstream.io to oceanstream.io.
- **C.** Create an A record that maps oceanstream.io to the load balancer’s IPv4 address, and create CNAME records that map www.oceanstream.io and portal.oceanstream.io to oceanstream.io.
- **D.** Create an A record that maps oceanstream.io to the load balancer’s IPv4 address, and create NS records that map www.oceanstream.io and portal.oceanstream.io to oceanstream.io.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a standard CNAME record cannot be created at the zone apex, which is oceanstream.io in this scenario. The apex already contains mandatory DNS records, including SOA and NS records, while a CNAME record cannot coexist with other record types at the same name. In addition, an A record must contain an IPv4 address as its record data; it cannot point to another domain name such as oceanstream.io. Therefore, both the apex CNAME and the proposed A records are inappropriate.

**B is incorrect** because a CNAME record cannot be placed at the zone apex alongside the required SOA and NS records. AAAA records are also intended to map hostnames to IPv6 addresses, not to another hostname such as oceanstream.io. Because the load balancer in this scenario has an IPv4 address, its address should be stored in an A record. Hostnames that must act as aliases of the apex domain should use CNAME records instead of AAAA records.

**C is correct** because an A record maps a hostname to an IPv4 address. HarborView Media should therefore create an A record at the zone apex that maps oceanstream.io directly to the reserved IPv4 address of the Google Cloud load balancer. It can then create separate CNAME records for www.oceanstream.io and portal.oceanstream.io, with oceanstream.io as their canonical name. DNS resolvers will first resolve each alias to oceanstream.io and then resolve the apex domain’s A record to the load balancer’s IPv4 address. This configuration also simplifies future changes because the load balancer address is maintained in one A record, while both subdomains continue to reference the apex domain.

**D is incorrect** because NS records identify the authoritative name servers for a DNS zone or delegate a subdomain to another DNS zone. They do not map application hostnames to an IP address or create aliases to another hostname. Creating NS records for www.oceanstream.io and portal.oceanstream.io would attempt to delegate those subdomains to DNS name servers, and oceanstream.io would not be valid NS record data unless it represented the hostname of an authoritative name server. CNAME records are the appropriate record type for making these subdomains aliases of the apex domain.

**Reference links**

- [docs.cloud.google.com/dns/docs/set-up-dns-records-domain-name](https://docs.cloud.google.com/dns/docs/set-up-dns-records-domain-name)
- [docs.cloud.google.com/dns/docs/records-overview](https://docs.cloud.google.com/dns/docs/records-overview)
- [docs.cloud.google.com/dns/docs/key-terms](https://docs.cloud.google.com/dns/docs/key-terms)

**Related notes:** [Cloud DNS](../06-networking/products/cloud-dns.md)

</details>

[Back to index](#index)

---

### Q30

> RideWave operates a fleet-management platform on Google Cloud. Its Compute Engine VM instances use a subnet in the asia-south1 region whose primary IPv4 range is nearly exhausted. The company expects to add many more VM instances during the next five days. You need to increase the available private IP addresses without interrupting existing workloads or creating unnecessary infrastructure costs. What should you do?  

- **A.** Create another VPC network with an overlapping subnet range, and connect it to the current network by using VPC Network Peering.
- **B.** Remove the existing subnet, and replace it with a new subnet that provides twice as many private IP addresses.
- **C.** Update the VPC firewall rules to allow traffic from a larger private IPv4 range.
- **D.** Use the gcloud CLI to expand the subnet’s primary IPv4 range.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because creating another VPC network with the same subnet IP range does not provide a valid extension of the existing subnet. Subnet ranges in peered VPC networks must not overlap because overlapping routes create ambiguous network paths, and VPC Network Peering does not combine the address spaces of two subnets into one larger subnet. Existing VM instances would also remain attached to the original subnet, so they could not automatically consume addresses from the subnet in the second VPC network. This approach would introduce another network, peering configuration, routing considerations, firewall policies, and additional operational management without solving the original subnet exhaustion problem.

**B is incorrect** because deleting and recreating the subnet would disrupt the resources that depend on it. A subnet generally cannot be deleted while resources such as VM network interfaces are still using it, so the administrator would first need to stop, delete, migrate, or reconfigure those resources. Replacing the subnet could also require assigning new internal IP addresses and updating dependent configurations. This approach creates unnecessary downtime and operational effort. Google Cloud supports directly expanding a subnet’s primary IPv4 range, so deleting the existing subnet is neither necessary nor recommended.

**C is incorrect** because VPC firewall rules control which network traffic is allowed or denied; they do not allocate private IP addresses or enlarge a subnet’s address range. Allowing traffic from additional addresses would not make those addresses part of the subnet, and Compute Engine would still be unable to assign them to new VM network interfaces. Firewall rules might need to be reviewed after an address-range change when rules use specific source or destination ranges, but changing firewall rules alone cannot resolve subnet IP address exhaustion.

**D is correct** because Google Cloud allows the primary IPv4 range of an existing subnet to be expanded by using the gcloud CLI command gcloud compute networks subnets expand-ip-range. The administrator specifies a shorter prefix length to create a larger CIDR range that contains the subnet’s existing range. Existing VM instances retain their current internal IP addresses, and the subnet gains additional addresses for new instances without requiring the subnet or its workloads to be deleted. This solution avoids downtime, minimizes administrative effort, and does not require an additional VPC network or other unnecessary infrastructure. The administrator should choose the new range carefully because a subnet’s primary IPv4 range can be expanded but cannot later be shrunk or replaced, and the expanded range must not overlap with other subnet ranges or connected network address spaces.

**Reference links**

- [docs.cloud.google.com/vpc/docs/create-modify-vpc-networks](https://docs.cloud.google.com/vpc/docs/create-modify-vpc-networks)
- [docs.cloud.google.com/vpc/docs/subnets](https://docs.cloud.google.com/vpc/docs/subnets)
- [docs.cloud.google.com/sdk/gcloud/reference/compute/networks/subnets/expand-ip-range](https://docs.cloud.google.com/sdk/gcloud/reference/compute/networks/subnets/expand-ip-range)

**Related notes:** [VPC, Subnets, and IPs](../06-networking/products/vpc-subnets-and-ips.md)

</details>

[Back to index](#index)

---

### Q31

> ParcelPilot is deploying an order-processing application in a new Google Cloud VPC network. The application must initiate outbound connections only on a small set of approved destination ports. The security team wants all other egress traffic blocked. Which firewall configuration should you use?  

- **A.** Create an egress deny-all rule with priority 65000 and an egress allow rule with priority 900 for only the approved ports.
- **B.** Create one rule with priority 900 that matches both ingress and egress ports.
- **C.** Create an egress deny-all rule with priority 900 and an egress allow rule with priority 65000 for only the approved ports.
- **D.** Create only an egress allow rule with priority 900 for the approved ports.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Google Cloud VPC networks include an implied allow-egress rule at priority 65535, which permits outbound traffic that does not match a higher-priority rule. An explicit deny-all egress rule at priority 65000 overrides this implied rule because 65000 has a higher priority than 65535. The allow rule at priority 900 is evaluated before the deny-all rule because lower numerical values represent higher priorities. Therefore, traffic using the approved protocols and destination ports is permitted by the priority-900 rule, while all remaining outbound traffic is blocked by the priority-65000 rule. This implements a least-privilege egress configuration and leaves only the required destination ports open.

**B is incorrect** because a VPC firewall rule has a single traffic direction: ingress or egress. One rule cannot simultaneously evaluate both directions. Ingress rules control packets entering the target network interface, whereas egress rules control packets leaving it. Because the requirement concerns outbound data transfer, dedicated egress rules must be created. Google Cloud VPC firewall rules are stateful, so response traffic for an allowed outbound connection is automatically permitted; a corresponding ingress rule is not required merely to receive the response.

**C is incorrect** because the deny-all rule has priority 900, while the allow rule has priority 65000. Google Cloud evaluates matching rules by priority, and a smaller number represents a higher priority. Consequently, every outbound packet would first match the priority-900 deny-all rule and be blocked. Processing would stop at that rule, so the lower-priority allow rule would never permit the approved ports. The specific allow rule must have a higher priority than the general deny rule.

**D is incorrect** because an allow rule does not create an implicit denial for traffic that fails to match it. Traffic using the approved ports would match the explicit priority-900 allow rule, but other outbound traffic would continue to the VPC network’s implied allow-egress rule at priority 65535. As a result, unapproved ports would remain available for outbound connections. An explicit deny-all egress rule with a priority higher than 65535 is required to override the implied allow-egress behavior.

**Reference links**

- [docs.cloud.google.com/firewall/docs/firewalls](https://docs.cloud.google.com/firewall/docs/firewalls)
- [docs.cloud.google.com/firewall/docs/using-firewalls](https://docs.cloud.google.com/firewall/docs/using-firewalls)
- [docs.cloud.google.com/firewall/docs/firewall-policies-overview](https://docs.cloud.google.com/firewall/docs/firewall-policies-overview)

**Related notes:** [Firewall, Hierarchical Policies, and Secure Tags (Cloud NGFW)](../06-networking/products/firewall-hierarchical-policies-and-secure-tags.md)

</details>

[Back to index](#index)

---

### Q32

> Northstar Media runs Linux-based build servers on Compute Engine. A new support vendor must connect to these virtual machines to update and troubleshoot installed software, but the vendor’s engineers do not have Google Accounts. How should Northstar Media provide the required access?  

- **A.** Enable Identity-Aware Proxy for the Compute Engine instances and grant the vendor’s engineers the IAP-Secured Tunnel User role.
- **B.** Apply a shared network tag to the instances and create an ingress firewall rule that permits TCP port 22 from the vendor’s network.
- **C.** Configure Cloud VPN between the Google Cloud VPC network and the vendor’s corporate network.
- **D.** Ask the vendor’s engineers to create SSH key pairs and add their public SSH keys to the metadata of the required VM instances.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Identity-Aware Proxy TCP forwarding authorizes access by evaluating Identity and Access Management permissions assigned to an authenticated principal. Granting the IAP-Secured Tunnel User role therefore requires the vendor’s engineers to have identities that Google Cloud IAM can recognize, such as Google Accounts, Cloud Identity accounts, or appropriately configured federated workforce identities. The scenario states that the vendor does not use Google Accounts and does not describe an identity federation configuration. Additionally, IAP only creates and authorizes the tunnel to the instance; the engineer still needs a valid operating-system login method, such as an SSH key or OS Login authorization. Therefore, assigning an IAP role alone does not meet the stated requirement.

**B is incorrect** because a VPC firewall rule controls network reachability but does not authenticate users to the Linux operating system. Allowing TCP port 22 from the vendor’s source addresses would let SSH connection attempts reach the tagged instances, but the engineers would still need valid SSH credentials to log in. Network tags identify which VM network interfaces the firewall rule applies to; they do not create Linux user accounts, install public keys, or grant administrative access. The source range should also be restricted rather than broadly described as traffic from the partner, but even a properly restricted firewall rule would solve only the connectivity requirement, not the authentication requirement.

**C is incorrect** because Cloud VPN provides encrypted private network connectivity between the Google Cloud VPC network and the vendor’s network. It can allow the vendor’s systems to route traffic to internal IP addresses on the Compute Engine instances, but it does not grant individual engineers permission to log in to Linux. The engineers would still require operating-system credentials such as SSH key pairs. Deploying Cloud VPN solely to provide administrative access would also introduce unnecessary gateways, tunnels, routing, availability planning, and operational overhead when the primary requirement is to authenticate engineers who do not have Google Accounts.

**D is correct** because SSH public-key authentication does not require the engineers to have Google Accounts. Each engineer can generate an SSH key pair, retain the private key securely, and provide the public key to Northstar Media. Northstar Media can add those public keys to the metadata of only the VM instances that the vendor must maintain. The Compute Engine guest environment reads metadata-managed SSH keys and configures the corresponding Linux accounts and authorized keys, allowing the engineers to authenticate by proving possession of their private keys. Instance-level metadata is preferable to project-wide metadata when access must be limited to selected VMs. This approach assumes OS Login is disabled for those instances because enabling OS Login causes metadata-managed SSH keys to be ignored. Appropriate firewall access to TCP port 22 and a valid network path must also exist, but among the listed options, adding the vendor’s SSH public keys is the action that actually grants login access without requiring Google Accounts. The keys should be removed promptly when the engagement ends, and expiration dates should be applied where supported.

**Reference links**

- [docs.cloud.google.com/compute/docs/connect/add-ssh-keys](https://docs.cloud.google.com/compute/docs/connect/add-ssh-keys)
- [docs.cloud.google.com/compute/docs/connect/create-ssh-keys](https://docs.cloud.google.com/compute/docs/connect/create-ssh-keys)
- [docs.cloud.google.com/compute/docs/instances/ssh](https://docs.cloud.google.com/compute/docs/instances/ssh)

**Related notes:** [Identity-Aware Proxy (IAP)](../02-identity-security/products/identity-aware-proxy.md)

</details>

[Back to index](#index)

---

### Q33

Choose 2.

> GlobeCart runs an online shopping website on Compute Engine. Its customer base is growing across North America, Europe, and Asia. GlobeCart needs to serve users from nearby infrastructure, reduce page-load latency, and scale traffic without managing separate traffic-routing systems for every location. Which two actions should GlobeCart take? (Choose two.)  

- **A.** Configure an external Application Load Balancer in Regional mode.
- **B.** Deploy Compute Engine VMs in multiple Google Cloud regions located near the company’s major user populations.
- **C.** Configure a Network Load Balancer to distribute website traffic.
- **D.** Configure an external Application Load Balancer in Global mode.
- **E.** Place every Compute Engine VM in one Google Cloud region that has a large available IP address range.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B, D

**Explanation**

**A is incorrect** because an external Application Load Balancer in Regional mode is designed for workloads whose frontend and backends are confined to a single Google Cloud region. Although it can distribute HTTP and HTTPS requests among backends within that region, it does not provide the global traffic distribution required for users located across multiple continents. GlobeCart would need to create and operate separate regional load balancers and implement an additional traffic-routing mechanism, such as DNS-based routing, to direct users to the appropriate region. This would increase operational complexity and would not provide the simplified global entry point offered by a global external Application Load Balancer.

**B is correct** because deploying Compute Engine VMs in multiple regions close to major user populations reduces the physical distance that requests must travel between users and application servers. Shorter network paths generally improve response times and reduce application latency. A multi-region deployment also gives GlobeCart additional capacity for its expanding user base and prevents all users from depending on one geographical location. The regional VM deployments can be organized into managed instance groups so that instance templates, health checking, autoscaling, and automated instance repair reduce administrative effort. These regional backends can then be connected to a global external Application Load Balancer, which directs incoming requests to an appropriate healthy backend.

**C is incorrect** because a Network Load Balancer primarily operates at the transport layer and distributes TCP, UDP, or other supported network-protocol traffic without providing the application-aware HTTP and HTTPS features that are normally appropriate for a public website. Depending on its type and configuration, a Network Load Balancer can serve regional or proxy-based networking use cases, but merely selecting a Network Load Balancer does not satisfy the requirement for globally routing website requests to application backends in several regions. An external Application Load Balancer is better suited to web traffic because it operates at Layer 7 and supports capabilities such as HTTP and HTTPS routing, URL maps, TLS termination, backend services, health checks, and integration with globally distributed Compute Engine backends.

**D is correct** because an external Application Load Balancer in Global mode provides a single global frontend for HTTP and HTTPS traffic and can distribute requests to healthy backends located in multiple Google Cloud regions. With Premium Tier, users can connect through Google’s globally distributed edge infrastructure, and the load balancer can direct requests toward an appropriate backend based on proximity, backend capacity, and health. This architecture helps reduce latency for GlobeCart’s international users while allowing the company to add regional backends as demand expands. It also lowers operational overhead because GlobeCart can manage one global load-balancing configuration instead of maintaining independent public endpoints and custom routing systems for every region.

**E is incorrect** because deploying every VM in a single region creates a geographically centralized application. Users who are far from that region experience longer network paths and higher latency, regardless of how large the region’s available CIDR range is. CIDR capacity determines how many internal IP addresses can be allocated within a subnet; it does not improve global application performance or bring compute resources closer to users. A single-region deployment also makes the website dependent on one regional failure domain and limits its ability to continue serving global users during a regional disruption. Distributing the application across regions is more appropriate for GlobeCart’s latency, growth, and geographical-availability requirements.

**Reference links**

- [cloud.google.com/load-balancing/docs/https](https://cloud.google.com/load-balancing/docs/https)
- [cloud.google.com/load-balancing/docs/choosing-load-balancer](https://cloud.google.com/load-balancing/docs/choosing-load-balancer)
- [cloud.google.com/solutions/best-practices-compute-engine-region-selection](https://cloud.google.com/solutions/best-practices-compute-engine-region-selection)

**Related notes:** [Cloud Load Balancing](../06-networking/products/cloud-load-balancing.md)

</details>

[Back to index](#index)

---

### Q34

> TrailNest Travel operates a trip-planning website on Cloud Run for approximately 650 customers. Users report that the first page they open after a period of inactivity is noticeably slower than the pages they visit afterward. You want to reduce this startup latency by following Google Cloud recommendations. What should you do?  

- **A.** Configure the Cloud Run service to maintain a minimum of 2 instances.
- **B.** Configure the Cloud Run service with a maximum concurrency of 1 request per instance.
- **C.** Configure the Cloud Run service to allow a maximum of 80 instances.
- **D.** Modify the application container to receive all requests through HTTP/2 instead of HTTP/1.1.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the symptoms indicate Cloud Run cold-start latency. When a service has no active instances, Cloud Run can scale it to zero. The first incoming request must then wait while Cloud Run creates an instance, starts the container, loads the application, and completes any initialization work. After the instance is running, subsequent requests are processed faster, which explains why only the first page is noticeably slow. Configuring minimum instances keeps the specified number of instances initialized and available even when there is no traffic. This reduces the likelihood that a user’s request must wait for a new container instance to start. The exact number of minimum instances should normally be selected according to traffic, concurrency, latency objectives, and cost, but maintaining 2 warm instances directly addresses the problem described.

**B is incorrect** because setting concurrency to 1 means that each Cloud Run instance can process only one request at a time. This configuration can cause Cloud Run to create more instances when several requests arrive simultaneously, potentially increasing the frequency of instance startups and raising costs. A concurrency value of 1 may be appropriate for applications that cannot safely process parallel requests or that are heavily constrained by CPU or memory, but it does not keep an instance running when the service has no traffic. Therefore, it does not directly prevent the cold start responsible for the slow initial page.

**C is incorrect** because maximum instances limits how far the service can scale out; it does not specify how many instances remain initialized during periods of inactivity. Setting the maximum to 80 can protect downstream systems, control costs, or prevent a service from scaling beyond an operational limit, but the service can still scale down to zero when no minimum-instance setting is configured. Consequently, the next request after an idle period may still trigger a cold start and experience the same initial delay.

**D is incorrect** because enabling HTTP/2 is not the recommended solution for container startup latency. HTTP/2 can provide transport-level benefits such as multiplexing multiple streams over a connection and is important for use cases such as gRPC, but it does not keep Cloud Run instances initialized. In addition, clients can communicate with Cloud Run through HTTP/2 at the external endpoint without necessarily requiring end-to-end HTTP/2 between Cloud Run and the application container. Configuring the container for HTTP/2 would not eliminate the initialization work performed when a new instance starts, so it would not directly resolve the pattern of a slow first request followed by faster requests.

**Reference links**

- [docs.cloud.google.com/run/docs/configuring/min-instances](https://docs.cloud.google.com/run/docs/configuring/min-instances)
- [docs.cloud.google.com/run/docs/tips/general](https://docs.cloud.google.com/run/docs/tips/general)
- [docs.cloud.google.com/run/docs/about-instance-autoscaling](https://docs.cloud.google.com/run/docs/about-instance-autoscaling)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md)

</details>

[Back to index](#index)

---

### Q35

Choose 2.

> BrightCart operates several applications on Google Cloud, including an order-processing service and an inventory-sync service. The cloud team needs to create and maintain service accounts for these workloads while following Google-recommended security and lifecycle practices. What should the team do? (Choose two.)  

- **A.** Minimize the total number of service accounts by sharing them across workloads.
- **B.** Permanently delete a service account as soon as it appears to be unused.
- **C.** Create a dedicated, single-purpose service account for each workload.
- **D.** Manage each service account as a resource together with its associated workload.
- **E.** Assign random names to service accounts so their purposes cannot be identified.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C, D

**Explanation**

**A is incorrect** because Google Cloud does not recommend minimizing the number of service accounts by making unrelated workloads share a common identity. Sharing one service account across multiple applications makes it difficult to apply the principle of least privilege because the account must receive the combined permissions required by every application. As the applications evolve, the shared account can accumulate excessive permissions. Sharing also complicates lifecycle management because the account cannot be safely disabled when one application is retired if another application still depends on it. In addition, Cloud Audit Logs identify the service account that performed an operation but might not reveal which of several applications using that account initiated it. Therefore, the objective is not to create as few service accounts as possible; it is to create an appropriate number of narrowly scoped service accounts.

**B is incorrect** because an apparently unused service account should not normally be deleted immediately. Google recommends first confirming its usage through tools such as service account insights, Activity Analyzer, and Cloud Monitoring service account usage metrics. After confirming that the account is unused, administrators should disable it before deleting it. Disabling provides a reversible safety period during which the account can be re-enabled with its existing IAM bindings if a workload unexpectedly fails. Immediate deletion can remove an identity that is still required, and recreating a service account with the same name does not recreate the same identity because the new account receives a different unique identifier. Existing IAM bindings associated with the deleted identity therefore do not automatically apply to the replacement account.

**C is correct** because Google recommends creating single-purpose service accounts. Each application, workload, or independently managed component should generally use a dedicated service account with only the permissions it needs. This design supports least-privilege access, allows permissions to evolve independently, and reduces the potential impact if one workload is compromised. It also improves auditability because activity recorded for a service account can be associated with a specific workload. When the workload is decommissioned, its dedicated service account can be disabled and eventually deleted without affecting unrelated applications.

**D is correct** because Google recommends managing service accounts as resources rather than viewing them only as identities that receive permissions. A service account should be managed together with the workload or resource that uses it, following the same ownership, deployment, monitoring, documentation, and lifecycle processes. For example, when an associated VM, application, or job is retired, the corresponding service account should be reviewed and disabled if it is no longer required. Service accounts are also IAM resources with their own allow policies, so administrators must carefully control who can impersonate them, attach them to resources, modify them, or create credentials for them.

**E is incorrect** because random names make service accounts difficult to identify, audit, and manage. Google recommends following a consistent naming and documentation convention. A service account’s name should help administrators understand its associated application, resource type, environment, or function without exposing sensitive information. Its display name and description can record its purpose, owner, contact person, or relevant documentation. Meaningful names make it easier to investigate audit logs, review permissions, identify unused accounts, and determine whether an account can safely be disabled.

**Reference links**

- [docs.cloud.google.com/iam/docs/best-practices-service-accounts](https://docs.cloud.google.com/iam/docs/best-practices-service-accounts)
- [docs.cloud.google.com/iam/docs/service-account-overview](https://docs.cloud.google.com/iam/docs/service-account-overview)
- [docs.cloud.google.com/policy-intelligence/docs/service-account-insights](https://docs.cloud.google.com/policy-intelligence/docs/service-account-insights)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q36

Choose 2.

> CipherForge Labs wants to provide its engineers with standardized, browser-accessible development environments on Google Cloud. Every engineer must receive the same security-approved tools, files saved in the home directory must remain available after a workstation stops and restarts, and inactive environments must shut down automatically to reduce costs. Which two configuration choices should CipherForge Labs make? (Choose two.)  

- **A.** Create a Cloud Workstations configuration that uses the approved container image and provisions a persistent home directory.
- **B.** Assign every engineer a permanent Compute Engine VM with local administrator privileges.
- **C.** Set an idle timeout or running timeout in the Cloud Workstations configuration.
- **D.** Save each engineer’s home-directory files exclusively on the workstation’s ephemeral boot disk.
- **E.** Create one service account key and use it as the shared login credential for every engineer.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A, C

**Explanation**

**A is correct** because a Cloud Workstations configuration provides a centrally managed template for creating consistent development environments. Administrators can specify an approved container image containing the required IDE, compilers, command-line tools, libraries, security utilities, and organizational settings. Every workstation created from that configuration receives the same standardized environment. The configuration can also provision a persistent directory that is mounted as the user’s home directory. When a workstation session stops, the underlying ephemeral VM can be deleted, but the persistent disk is detached and retained. When the workstation starts again, the disk is reattached, allowing source files, configuration files, shell settings, and other home-directory data to remain available between sessions.

**B is incorrect** because permanent Compute Engine VMs do not provide the same centrally managed, on-demand developer experience as Cloud Workstations. Giving developers local administrator access also allows them to modify installed tools, security settings, and operating-system configurations, causing environments to drift away from the approved standard. Permanently running VMs can continue generating compute charges even when developers are not actively using them unless a separate shutdown system is implemented. Cloud Workstations is specifically designed to provide centrally configured development environments that users can access through a browser while administrators control the underlying workstation configuration.

**C is correct** because Cloud Workstations configurations support automatic shutdown controls. An idle timeout stops a workstation after it has remained inactive for the configured period, which helps prevent unused environments from continuing to consume compute resources. A running timeout can stop a workstation after a maximum amount of running time regardless of activity, providing an additional cost-control and governance mechanism. These timeout settings apply consistently to workstations created from the configuration and eliminate the need to depend on developers to manually stop their environments.

**D is incorrect** because a workstation’s boot disk and runtime VM are ephemeral. When the workstation stops, the VM and its ephemeral runtime data can be deleted. Files stored only on that boot disk could therefore be lost between sessions. To preserve source code, settings, credentials managed within the development environment, and other user files, the workstation configuration should provision a persistent home directory backed by persistent storage. The persistent disk is mounted at the home-directory location when the workstation starts and retained when the session ends.

**E is incorrect** because a shared service account key is neither an appropriate user-login mechanism nor a secure way to provide access to Cloud Workstations. Service account keys are long-lived credentials intended for workload authentication in limited scenarios, not for identifying individual developers. Sharing one key prevents reliable user-level auditing, makes access revocation difficult, and creates a serious security risk if the key is copied or exposed. Developers should authenticate with their individual Google identities, and IAM permissions should determine who can access or operate each workstation. This approach preserves accountability and avoids distributing shared credentials.

**Reference links**

- [docs.cloud.google.com/workstations/docs/overview](https://docs.cloud.google.com/workstations/docs/overview)
- [docs.cloud.google.com/workstations/docs/customize-development-environment](https://docs.cloud.google.com/workstations/docs/customize-development-environment)
- [docs.cloud.google.com/workstations/docs/reference/rest/v1/projects.locations.workstationClusters.workstationConfigs](https://docs.cloud.google.com/workstations/docs/reference/rest/v1/projects.locations.workstationClusters.workstationConfigs)

**Related notes:** [Cloud Workstations](../08-iac-platform-ai/products/cloud-workstations.md)

</details>

[Back to index](#index)

---

### Q37

> CodeHarbor Labs manages Cloud Workstations for developers building its online payment platform. An administrator changes a workstation configuration to use a more powerful machine type and an updated container image containing security fixes. One developer’s running workstation still uses the previous machine type and image, but the developer has critical source files stored in the configured persistent home directory. What should the administrator instruct the developer to do?  

- **A.** Restart the workstation so that it starts with the updated configuration.
- **B.** Delete the persistent home disk and then restart the workstation.
- **C.** Manually replace the IDE and development tools inside the existing ephemeral VM.
- **D.** Create a separate Google Cloud organization and move the workstation into it.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because updates made to a Cloud Workstations configuration are applied to associated workstations the next time those workstations start. A running workstation continues to use the VM resources and container image with which its current session was created, so changing the machine type or development image does not immediately replace the active environment. Restarting the workstation causes Cloud Workstations to stop and replace the ephemeral VM, provision the workstation with the newly configured machine type, and start the updated container image. Because the workstation has a configured persistent home directory, its persistent disk is detached when the workstation stops and reattached when the new session starts. Files saved in the persistent home directory therefore remain available after the restart. Files stored outside that directory on the ephemeral VM might be lost, so the developer should first ensure that all important work is saved under the persistent home directory.

**B is incorrect** because deleting the persistent disk would remove the storage that protects the developer’s important files across workstation sessions. The persistent home directory is intentionally separated from the workstation’s ephemeral VM so that the VM can be replaced during a restart without deleting the developer’s source code, settings, and other files stored in the home directory. The disk only needs to be detached and reattached as part of the normal workstation lifecycle; it does not need to be deleted for a new machine type or container image to take effect. Deleting it would introduce unnecessary risk of permanent data loss and would defeat the purpose of configuring persistent storage.

**C is incorrect** because manually reinstalling the IDE or development tools inside the current ephemeral VM does not apply the updated workstation configuration. It would not change the VM’s machine type, and manually installed changes might disappear when the workstation stops because the underlying VM is ephemeral. The container image specified in the workstation configuration defines the standardized development environment and should be applied by restarting the workstation. Administrators should make durable environment changes through the workstation configuration and container image rather than relying on manual modifications to individual running workstations.

**D is incorrect** because a Google Cloud organization is an administrative resource hierarchy used to centrally manage projects, policies, identities, and access controls. Creating another organization has no role in applying a modified Cloud Workstations configuration to an existing workstation. Moving resources to another organization would add substantial administrative complexity and would not solve the issue. The workstation only needs to be restarted so Cloud Workstations can recreate its ephemeral runtime from the updated configuration while preserving the configured persistent home directory.

**Reference links**

- [docs.cloud.google.com/workstations/docs/overview](https://docs.cloud.google.com/workstations/docs/overview)
- [docs.cloud.google.com/workstations/docs/create-configuration](https://docs.cloud.google.com/workstations/docs/create-configuration)
- [docs.cloud.google.com/workstations/docs/architecture](https://docs.cloud.google.com/workstations/docs/architecture)

**Related notes:** [Cloud Workstations](../08-iac-platform-ai/products/cloud-workstations.md)

</details>

[Back to index](#index)

---

### Q38

> ImageForge operates a media platform where customers upload images to a Cloud Storage bucket. A small code component must run automatically each time a new image is successfully uploaded. Which deployment approach should ImageForge use?  

- **A.** Deploy the code to App Engine and use Cloud Scheduler to publish recurring messages to Pub/Sub.
- **B.** Deploy the code as a Cloud Run function and configure the Cloud Storage bucket as its event trigger.
- **C.** Deploy the code to Google Kubernetes Engine and create a CronJob that consumes messages from Pub/Sub.
- **D.** Deploy the code as a Dataflow batch pipeline and configure the Cloud Storage bucket as its input source.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because App Engine can host an application that processes requests, but Cloud Scheduler is intended to invoke workloads according to a time-based schedule. A scheduled Pub/Sub message would run at predetermined intervals rather than immediately in response to each newly uploaded object. Additional logic would be required to discover which files had arrived, avoid processing the same file more than once, and track previously processed objects. This architecture introduces App Engine, Cloud Scheduler, and Pub/Sub even though Cloud Storage can directly generate an object-finalization event. It therefore does not provide the simplest event-driven deployment model for the code snippet.

**B is correct** because Cloud Functions has been renamed to Cloud Run functions, and Cloud Run functions are designed for small, event-driven code components that run without requiring the user to provision or manage servers. The function can be configured with a Cloud Storage trigger for the object-finalized event. When a new object is created or an upload successfully completes in the selected bucket, Cloud Storage produces an event that is delivered to the function through the managed eventing infrastructure. The function can then read information about the uploaded object, such as its bucket name and object name, and execute the required processing logic. This approach provides automatic scaling, managed execution, event-driven invocation, and minimal infrastructure administration. The code should also be designed to be idempotent because event delivery can be retried and, like many distributed event systems, can result in the same event being processed more than once.

**C is incorrect** because a Google Kubernetes Engine CronJob starts containers according to a schedule rather than in direct response to individual Cloud Storage object uploads. The solution would require a Kubernetes cluster, container images, CronJob configuration, Pub/Sub integration, subscription management, scaling decisions, and operational maintenance. It would also need a separate mechanism to publish Cloud Storage events to Pub/Sub. Although a continuously running Kubernetes workload could consume Pub/Sub messages, a CronJob is not the appropriate primitive for immediate event processing. This design is substantially more complex than deploying the code as a Cloud Run function with a Cloud Storage trigger.

**D is incorrect** because Dataflow is intended for distributed batch and streaming data-processing pipelines, particularly workloads that process large datasets using Apache Beam. Configuring a Cloud Storage location as a batch input source would cause a pipeline to process available data when the batch job runs, but it would not naturally deploy a small code snippet that is invoked once for every new file upload. Repeatedly launching Dataflow batch jobs for individual objects would add startup overhead, pipeline-management complexity, and unnecessary cost. Dataflow could be appropriate when uploaded files feed a large-scale transformation pipeline, but it is not the most direct service for executing lightweight event-driven code.

**Reference links**

- [docs.cloud.google.com/run/docs/tutorials/trigger-functions-storage](https://docs.cloud.google.com/run/docs/tutorials/trigger-functions-storage)
- [docs.cloud.google.com/run/docs/triggering/storage-triggers](https://docs.cloud.google.com/run/docs/triggering/storage-triggers)
- [docs.cloud.google.com/run/docs/functions-with-run](https://docs.cloud.google.com/run/docs/functions-with-run)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md)

</details>

[Back to index](#index)

---

### Q39

> BrightTrail Media is developing a local automation script that runs several gcloud CLI commands to inspect Cloud Storage buckets and Compute Engine instances. A developer must test the script using the permissions of a service account while avoiding long-lived credentials on the workstation. What should the developer do?  

- **A.** Create an ID token for the service account and supply that token to each gcloud CLI command.
- **B.** Grant the developer permission to impersonate the service account and configure gcloud CLI to impersonate it by default using gcloud config set.
- **C.** Create and download a service account key, store the file in an encrypted local directory, and set GOOGLE_APPLICATION_CREDENTIALS to its path.
- **D.** Create and download a service account key, use the key to generate an access token, and provide the token to each gcloud CLI command.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because an ID token primarily proves the identity of a caller to a specific audience, such as a Cloud Run service or another application that validates OpenID Connect tokens. It is not the general-purpose credential that gcloud CLI commands use to authorize access to Google Cloud resource APIs. Most gcloud CLI operations require OAuth 2.0 access tokens containing appropriate scopes and permissions. Even where a manually generated token could be used in a specialized workflow, manually obtaining and supplying tokens would introduce unnecessary complexity and would not provide the secure, automatically refreshed credential workflow available through service account impersonation.

**B is correct** because service account impersonation allows the developer to authenticate locally using their own user identity and temporarily operate with the service account’s permissions. The developer must have an appropriate role, typically Service Account Token Creator, on the target service account. The command gcloud config set auth/impersonate_service_account SERVICE_ACCOUNT_EMAIL configures the active gcloud CLI configuration so that subsequent commands automatically request short-lived credentials for that service account. These credentials expire automatically and do not require downloading or storing a private service account key. This follows Google-recommended security practices by providing auditable access, supporting least privilege, and reducing the risk associated with long-lived credentials. A separate named gcloud configuration can also be used so that impersonation applies only while testing the script.

**C is incorrect** because a downloaded service account key is a long-lived credential that can be copied, leaked, committed to source control, or extracted from the developer’s workstation. Encrypting the directory reduces some local exposure but does not eliminate the security risks or the operational burden of protecting, rotating, monitoring, and eventually deleting the key. In addition, GOOGLE_APPLICATION_CREDENTIALS is primarily used by Application Default Credentials-aware applications and client libraries; it is not the recommended mechanism for selecting an identity for ordinary gcloud CLI commands. Service account impersonation avoids creating a persistent private key and is therefore the more secure option.

**D is incorrect** because downloading a service account key creates the same long-lived credential risk even when the key is used only to generate an access token. Anyone who obtains the key can continue generating new access tokens until the key is disabled or deleted. Manually generating and supplying access tokens also complicates the script because access tokens expire and must be refreshed. Service account impersonation already generates short-lived access credentials automatically without exposing a service account private key, making it safer and easier to operate.

**Reference links**

- [cloud.google.com/iam/docs/service-account-impersonation](https://cloud.google.com/iam/docs/service-account-impersonation)
- [cloud.google.com/sdk/docs/authorizing](https://cloud.google.com/sdk/docs/authorizing)
- [cloud.google.com/iam/docs/best-practices-for-managing-service-account-keys](https://cloud.google.com/iam/docs/best-practices-for-managing-service-account-keys)

**Related notes:** [Service account impersonation](../02-identity-security/products/service-account-impersonation.md)

</details>

[Back to index](#index)

---

### Q40

> MediRoute, a medical appointment mobile app, stores its scheduling database on a Persistent Disk attached to a single Compute Engine VM. The operations team must create a recoverable backup of the complete disk every 24 hours and retain each backup for 10 days. The solution must use Google Cloud security controls and require no custom backup code or ongoing maintenance. What should the team do?  

- **A.** Configure Persistent Disk Asynchronous Replication to copy the primary disk to a secondary disk in another region.
- **B.** Attach a daily snapshot schedule to the Persistent Disk and configure a snapshot retention period of 10 days.
- **C.** Configure Cloud Scheduler to invoke a Cloud Run function daily that creates a machine image and deletes machine images older than 10 days.
- **D.** Configure a cron job that uses the gcloud storage CLI to copy files from the mounted disk to an Archive storage bucket and configure Object Lifecycle Management to delete the objects after 10 days.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Persistent Disk Asynchronous Replication is designed primarily for low-recovery-point-objective and low-recovery-time-objective disaster recovery across regions. It continuously transfers changes from a primary disk to a secondary disk, providing a relatively current replica that can be used during a regional failure. However, a replica is not the same as a series of retained point-in-time backups. This configuration does not automatically create one independent backup per day or maintain 10 days of historical disk states. Logical corruption, accidental deletion, or unwanted application changes can also be copied to the secondary disk. Additional procedures would be required to manage the replica, promote it during recovery, and create historical recovery points.

**B is correct** because Compute Engine snapshot schedules are a native, fully managed mechanism for creating recurring point-in-time backups of Persistent Disk data. A snapshot schedule can run once per day and include a retention policy that automatically deletes scheduled snapshots after 10 days. This directly satisfies both the backup frequency and retention requirements without requiring scripts, Cloud Scheduler jobs, functions, or manually implemented cleanup logic. Persistent Disk snapshots are incremental after the initial snapshot, meaning subsequent snapshots generally store only changed blocks while still presenting a complete recovery point. Snapshot access can be controlled through Identity and Access Management, and snapshots are encrypted at rest by default. The organization can also use customer-managed encryption keys when its security requirements demand additional control over encryption keys. Because scheduling, snapshot creation, and expiration are handled by Compute Engine, this option requires the least setup and ongoing administration.

**C is incorrect** because machine images can capture a VM’s disks together with configuration information, metadata, and other instance properties, so the proposed automation could technically create usable recovery resources. However, it introduces unnecessary components and operational complexity. The team would need to develop, deploy, secure, test, and monitor a Cloud Run function; configure Cloud Scheduler; assign appropriate service-account permissions; implement naming and deletion logic; handle retries and partial failures; and monitor quota or execution errors. Machine images are more appropriate when the recovery requirement includes reproducing the complete VM configuration rather than simply backing up Persistent Disk data. A managed snapshot schedule already provides the required daily backups and automatic retention without custom code.

**D is incorrect** because copying files from a mounted filesystem creates a file-level copy rather than a block-level backup of the complete Persistent Disk. The copy might omit the boot structure, partition information, filesystem metadata, inaccessible files, or other disk-level data required for complete disk restoration. Files can also change while the script is running, potentially producing an inconsistent backup unless the application and filesystem are coordinated or paused. The solution additionally requires maintaining a script, cron configuration, service-account credentials, transfer error handling, monitoring, and recovery procedures. Archive storage is intended for long-term data retention and has a minimum storage duration, so deleting archived objects after only 10 days can result in early-deletion charges. Although Object Lifecycle Management can delete objects according to their age, the overall approach does not provide the simple, complete, managed disk-backup solution required.

**Reference links**

- [docs.cloud.google.com/compute/docs/disks/about-snapshot-schedules](https://docs.cloud.google.com/compute/docs/disks/about-snapshot-schedules)
- [docs.cloud.google.com/compute/docs/disks/async-pd/about](https://docs.cloud.google.com/compute/docs/disks/async-pd/about)
- [docs.cloud.google.com/compute/docs/machine-images](https://docs.cloud.google.com/compute/docs/machine-images)

**Related notes:** [Persistent Disk and snapshots](../03-compute-containers/products/persistent-disk-and-snapshots.md)

</details>

[Back to index](#index)

---

### Q41

> NovaLedger has assigned you responsibility for maintaining an existing Google Cloud project named ledger-archive-prod. During an access review, you need to identify the principals that currently have the Project Owner role in the project. What should you do?  

- **A.** Review the project-wide SSH keys configured for Compute Engine.
- **B.** Open Identity-Aware Proxy and inspect the access permissions configured for protected applications.
- **C.** Enable Data Access audit logs for all services and examine the generated log entries.
- **D.** Run gcloud projects get-iam-policy ledger-archive-prod and review the bindings for roles/owner.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because project-wide SSH keys control SSH authentication to Compute Engine virtual machine instances that accept project-level keys. Reviewing these keys can help identify users who might be able to sign in to certain VMs, but SSH keys do not represent IAM role assignments for the Google Cloud project. A principal can have the Project Owner role without having an SSH key, and a user with an SSH key does not necessarily have the Project Owner role. Therefore, checking project-wide SSH keys does not answer who has been granted roles/owner.

**B is incorrect** because Identity-Aware Proxy controls access to applications and resources that are protected by Identity-Aware Proxy. Its access settings show which principals can access those protected resources, typically through roles such as IAP-secured Web App User. These permissions are separate from the project’s general IAM allow policy. Reviewing Identity-Aware Proxy permissions would not provide a complete or authoritative list of principals assigned the Project Owner role.

**C is incorrect** because Cloud Audit Logs record administrative activities, data access events, system events, and policy-denied events. Audit logs can help investigate when an IAM policy was changed and which principal performed the change, provided the relevant logs are available. However, enabling additional audit logs now does not directly display the project’s current IAM role assignments, and it does not retroactively create log entries for historical activity that was not previously recorded. Examining audit logs is therefore less direct and less efficient than retrieving the current IAM policy.

**D is correct** because gcloud projects get-iam-policy retrieves the current IAM allow policy attached to the specified Google Cloud project. The output contains role bindings that associate IAM roles with principals such as users, groups, service accounts, and domains. You can inspect the binding for roles/owner to determine which principals have been directly granted the Project Owner role on the project. You can also use output formatting or filtering to make the result easier to review, but the essential action is to retrieve and inspect the project’s IAM policy.

**Reference links**

- [cloud.google.com/sdk/gcloud/reference/projects/get-iam-policy](https://cloud.google.com/sdk/gcloud/reference/projects/get-iam-policy)
- [cloud.google.com/iam/docs/granting-changing-revoking-access](https://cloud.google.com/iam/docs/granting-changing-revoking-access)
- [cloud.google.com/resource-manager/docs/access-control-proj](https://cloud.google.com/resource-manager/docs/access-control-proj)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q42

> TerraPulse Agriculture operates approximately 4 million connected field devices that continuously produce JSON telemetry, binary diagnostic files, and equipment logs. The company wants to retain the raw data in a Google Cloud data lake by using a highly available, scalable, and resilient architecture. What should the company do?  

- **A.** Publish the device data to Pub/Sub, and use a Dataflow streaming pipeline to write the data to Cloud Storage.
- **B.** Publish the device data to Pub/Sub, and use Storage Transfer Service to load the data into BigQuery.
- **C.** Send the device data directly to Dataflow, and use Cloud Data Fusion to write the data to Bigtable.
- **D.** Send the device data directly to Dataflow, and use Storage Transfer Service to load the data into BigQuery.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Pub/Sub provides a fully managed, scalable, asynchronous messaging layer that can accept continuous event streams from a very large number of devices. It decouples the sensor publishers from downstream processing, which improves resilience because the devices do not need to communicate directly with the data-processing system. Dataflow can continuously consume messages from Pub/Sub, perform transformations, windowing, validation, enrichment, or format conversion, and write the results to Cloud Storage. Cloud Storage is appropriate for a data lake because it provides durable object storage for structured, semi-structured, and unstructured data. This combination separates ingestion, processing, and storage into independently managed services and is a standard Google Cloud architecture for large-scale streaming data.

**B is incorrect** because Storage Transfer Service is designed primarily to move files and objects between supported storage systems, such as transferring data from Amazon S3, Azure Blob Storage, on-premises file systems, or another Cloud Storage bucket into Cloud Storage. It does not consume a continuous Pub/Sub message stream and write those events directly to BigQuery. BigQuery can store and analyze structured data, but it is primarily an analytics data warehouse rather than the raw object-storage layer normally used for a data lake containing both structured and unstructured sensor data. A Dataflow pipeline or a supported Pub/Sub-to-BigQuery subscription would be required for streaming Pub/Sub data into BigQuery.

**C is incorrect** because Dataflow is a managed data-processing service rather than a device-facing messaging endpoint. A durable ingestion layer such as Pub/Sub should receive and buffer the sensor events before Dataflow processes them. Sending millions of device streams directly to a processing pipeline would create tighter coupling and would not provide the same message retention, delivery, and replay capabilities. Cloud Data Fusion is a managed data-integration service intended for building data pipelines through a graphical interface, but adding it after Dataflow would introduce an unnecessary processing layer. Bigtable is suitable for high-throughput, low-latency access to large amounts of keyed data, but it is not an object-based data lake for retaining arbitrary structured and unstructured files.

**D is incorrect** because it omits Pub/Sub, which should provide the scalable and resilient ingestion layer between the IoT devices and Dataflow. Dataflow pipelines consume data from supported sources; they are not normally exposed as direct streaming endpoints for millions of independently connected sensors. Storage Transfer Service also cannot take the output of a live Dataflow stream and continuously load it into BigQuery. It transfers files and objects between supported storage sources and destinations, and BigQuery is not a supported Storage Transfer Service destination. This design therefore uses the services for purposes they are not intended to perform and does not provide an appropriate data-lake storage layer for unstructured data.

**Reference links**

- [docs.cloud.google.com/pubsub/docs/overview](https://docs.cloud.google.com/pubsub/docs/overview)
- [docs.cloud.google.com/dataflow/docs/guides/templates/provided/pubsub-topic-subscription-to-text](https://docs.cloud.google.com/dataflow/docs/guides/templates/provided/pubsub-topic-subscription-to-text)
- [docs.cloud.google.com/storage-transfer/docs/overview](https://docs.cloud.google.com/storage-transfer/docs/overview)

**Related notes:** [Dataflow](../05-storage-databases-data/products/dataflow.md)

</details>

[Back to index](#index)

---

### Q43

> NordicCare Analytics is migrating several healthcare reporting workloads to Google Cloud. Its projects are organized under separate folders for engineering, data, and operations. The company requires every supported location-based resource created anywhere in its Google Cloud hierarchy to use only approved locations within the European Economic Area. You must enforce this requirement centrally by using the Organization Policy Service resource locations constraint. What should you do?  

- **A.** Apply the policy to each folder and specify all approved EEA locations as allowed values.
- **B.** Apply the policy at the organization level and specify all approved EEA locations as allowed values.
- **C.** Apply the policy to each folder and specify every location outside the EEA as denied values.
- **D.** Apply the policy at the organization level and specify every location outside the EEA as denied values.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because a policy configured at the folder level applies only to that folder and its descendants. NordicCare Analytics has projects distributed across several folders, so administrators would need to configure and maintain the same policy separately on every applicable folder. A new folder or a project located outside those folders could remain unrestricted if the policy were not applied correctly. Although using allowed values is the appropriate restrictive policy model, applying the policy independently to folders does not provide the simplest and most comprehensive organization-wide enforcement.

**B is correct** because the organization resource is the root of the Google Cloud resource hierarchy, and an organization policy applied there is inherited by descendant folders and projects by default. Configuring the constraints/gcp.resourceLocations constraint at the organization level therefore provides one central policy for all supported resources created throughout the organization. Specifying the approved EEA locations as allowed values creates an allowlist: supported resources can be created only in those locations, while locations not included in the policy are unavailable. Where an appropriate Google-managed location value group exists, using the value group is preferable to manually listing individual regions because Google maintains its membership as eligible locations change. The organization should also test the policy on non-production resources before applying it broadly because the constraint can prevent services from creating required resources in unapproved locations.

**C is incorrect** because applying separate deny policies at the folder level creates both incomplete coverage and additional administrative work. Every existing folder would need the same configuration, and administrators would also need to remember to configure each new folder. In addition, maintaining an explicit list of disallowed locations is less reliable for a strict geographical boundary because a newly introduced Google Cloud location might not be present in the deny list and could therefore be permitted until the policy is updated. An organization-level allowlist is a more secure and manageable approach.

**D is incorrect** because applying the policy at the organization level provides the correct scope, but listing all disallowed locations is not the best approach for enforcing a strict EEA-only boundary. A denylist must account for every location outside the approved boundary and may require updates whenever Google Cloud introduces new regions, zones, multi-regions, or applicable value groups. A location omitted from the denylist could remain usable. An allowlist instead defines the complete permitted boundary and implicitly prevents the use of locations that are not approved, making option B the more reliable choice.

**Reference links**

- [docs.cloud.google.com/organization-policy/restrict-locations](https://docs.cloud.google.com/organization-policy/restrict-locations)
- [docs.cloud.google.com/organization-policy/hierarchy-evaluation](https://docs.cloud.google.com/organization-policy/hierarchy-evaluation)
- [docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy](https://docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)

**Related notes:** [Organization Policy Service](../02-identity-security/products/organization-policy-service.md)

</details>

[Back to index](#index)

---

### Q44

> HarborLine Logistics grants its cloud engineering team the Compute Admin role on the Core-Services folder, and every project in that folder inherits the access. A recently purchased warehouse automation project requires stricter isolation and must not provide this role to the cloud engineering team. Access to all other Core-Services projects must remain unchanged. Which approach should the administrator use?  

- **A.** Add an allow policy to the warehouse automation project that attempts to remove the inherited Compute Admin permissions.
- **B.** Move the warehouse automation project into a separate folder that does not inherit the Core-Services folder binding, and grant only the necessary roles in the new folder.
- **C.** Grant the cloud engineering team the Owner role on the warehouse automation project so that it replaces the inherited Compute Admin role.
- **D.** Delete the cloud engineering group and grant permissions separately to each engineer.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because an IAM allow policy can grant permissions but cannot explicitly deny permissions granted by an inherited allow policy. IAM allow policies are additive across the Google Cloud resource hierarchy. Therefore, omitting the Compute Admin role from the project-level policy or adding another project-level allow binding does not cancel the role inherited from the parent folder. Google Cloud supports separate IAM deny policies that can block specified permissions, including inherited permissions, but the option specifically proposes an allow policy. In addition, using a deny policy to counteract a broad parent-folder grant can make the access model more difficult to understand because administrators must evaluate both inherited allow bindings and project-level deny rules.

**B is correct** because IAM role bindings attached to a folder are inherited only by the folders and projects located beneath that folder in the Google Cloud resource hierarchy. Moving the acquired project to a separate folder removes it from the scope of the Compute Admin binding on the Core-Services folder. The administrator can then assign only the roles required for the isolated project at its new folder or directly on the project. All projects that remain in the original folder continue inheriting the existing Compute Admin role, so their access is unchanged. This approach creates a clear administrative and security boundary and is easier to understand and maintain than introducing exception policies that counteract inherited permissions.

**C is incorrect** because IAM role bindings do not override one another based on privilege level. Google Cloud combines applicable permissions from organization-level, folder-level, and project-level allow policies. Granting the Owner role would add highly privileged permissions to the permissions already inherited through Compute Admin; it would not replace or cancel the inherited role. The Owner role would also violate least privilege by allowing extensive control over project resources and IAM configuration.

**D is incorrect** because deleting the group does not provide a maintainable exception for one project. It would disrupt the group’s valid access to every other project that inherits the folder-level binding. Assigning permissions to each operator individually would also increase administrative work, make employee onboarding and offboarding more difficult, and raise the risk of inconsistent access. Groups should generally be retained for centralized identity and membership management, while folders should be used to define different access boundaries for groups of resources.

**Reference links**

- [docs.cloud.google.com/iam/docs/resource-hierarchy-access-control](https://docs.cloud.google.com/iam/docs/resource-hierarchy-access-control)
- [docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy](https://docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)
- [docs.cloud.google.com/resource-manager/docs/moving-projects-folders](https://docs.cloud.google.com/resource-manager/docs/moving-projects-folders)

</details>

[Back to index](#index)

---

### Q45

> AsterBank routes security logs from Cloud Logging to a centralized destination. After an IAM policy review, the sink stops exporting logs, and audit records show that roles/logging.serviceAgent was removed from the Google-managed Cloud Logging service agent. The security team must restore log routing without assigning the service-agent role to employees. What should the administrator do?  

- **A.** Grant roles/logging.serviceAgent to the logging administrators group.
- **B.** Create a user-managed service account with the Owner role and use it to replace all Google-managed service accounts.
- **C.** Restore roles/logging.serviceAgent to the designated Google-managed Cloud Logging service agent.
- **D.** Allow unauthenticated users to write to the log destination.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because service-agent roles are designed for specific Google-managed service agents, not human users or administrative groups. These roles can include powerful permissions that Google Cloud services require to perform operations on behalf of a project. Granting roles/logging.serviceAgent to the logging administrators group would unnecessarily expose those service-level permissions to human identities and violate the principle of least privilege. Logging administrators should receive standard administrative roles appropriate to their responsibilities, while the Cloud Logging service agent should retain the service-agent role required for managed service operations.

**B is incorrect** because creating a user-managed service account with the Owner role would grant extremely broad permissions and would not be an appropriate replacement for every Google-managed service agent. Google-managed service agents have service-specific identities and predefined roles that enable individual Google Cloud services to operate. Replacing them with one highly privileged identity would weaken isolation, increase the impact of credential or permission misuse, complicate troubleshooting, and violate least privilege. Cloud Logging supports user-managed service accounts for certain sink configurations, but such an account should receive only the destination-specific permissions it needs and should not be given Owner or used as a universal replacement for managed service agents.

**C is correct** because the audit trail identifies the removal of the predefined Cloud Logging service-agent role from the Google-managed principal that requires it. The administrator should restore the documented IAM binding between roles/logging.serviceAgent and the correct service agent, such as service-PROJECT_NUMBER@gcp-sa-logging.iam.gserviceaccount.com for a project-level Cloud Logging service agent. Service-agent roles contain permissions required by Google Cloud services and should be assigned only to the corresponding service agents. Restoring the original binding repairs the service’s authorization while avoiding the dangerous practice of granting the role to users. The administrator should also verify that the sink’s writer identity still has the destination-specific role required to write exported logs, such as Storage Object Creator for a Cloud Storage destination, Pub/Sub Publisher for a Pub/Sub topic, or BigQuery Data Editor for a BigQuery dataset.

**D is incorrect** because making the destination publicly writable would allow unauthenticated or unauthorized parties to insert, modify, or flood data at the destination. This would create serious security, integrity, compliance, and cost risks without restoring the missing service-agent permissions correctly. Public access also removes meaningful caller accountability and does not follow least privilege. The destination should remain protected by IAM, with write access granted only to the sink’s designated writer identity or other explicitly authorized principals.

**Reference links**

- [docs.cloud.google.com/iam/docs/service-agents](https://docs.cloud.google.com/iam/docs/service-agents)
- [docs.cloud.google.com/iam/docs/roles-permissions/logging](https://docs.cloud.google.com/iam/docs/roles-permissions/logging)
- [docs.cloud.google.com/logging/docs/export/configure_export_v2](https://docs.cloud.google.com/logging/docs/export/configure_export_v2)

**Related notes:** [Cloud Logging](../07-operations-cost/products/cloud-logging.md)

</details>

[Back to index](#index)

---

### Q46

> ParcelPulse uses Pub/Sub to process shipment status events. A pull subscription named tracking-worker is connected to the shipment-events topic. An administrator needs to retrieve currently available messages from the subscription by using the Google Cloud CLI and acknowledge each returned message automatically. Which command should the administrator run?  

- **A.** Run gcloud pubsub subscriptions seek tracking-worker.
- **B.** Run gcloud pubsub topics describe shipment-events.
- **C.** Run gcloud pubsub subscriptions pull tracking-worker --auto-ack.
- **D.** Run gcloud pubsub topics list-subscriptions shipment-events --filter="tracking-worker".

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because gcloud pubsub subscriptions seek is used to change the acknowledgment state of a subscription’s message backlog by moving the subscription to a specified timestamp or snapshot. It is primarily used to replay previously acknowledged messages or purge messages by marking part of the backlog as acknowledged. A valid seek operation also requires an argument such as --time or --snapshot. The command does not retrieve waiting messages and display their contents for processing, so it does not meet the requirement to fetch and acknowledge available messages.

**B is incorrect** because gcloud pubsub topics describe shipment-events returns configuration and metadata about the specified topic, such as its resource name, labels, message storage policy, schema settings, or other topic properties. A topic is the resource to which publishers send messages, but subscribers receive messages through subscriptions. Describing the topic neither retrieves messages from tracking-worker nor acknowledges any messages. The administrator must perform a pull operation against the subscription rather than a describe operation against the topic.

**C is correct** because gcloud pubsub subscriptions pull tracking-worker retrieves one or more available messages from the specified pull subscription. Adding the --auto-ack flag instructs the Google Cloud CLI to acknowledge the messages that it successfully returns. Acknowledgment informs Pub/Sub that those messages have been handled and generally prevents them from being redelivered through that subscription. Without --auto-ack, the command displays the messages but does not automatically acknowledge them, and they can become available for redelivery after the acknowledgment deadline expires. The administrator can also add options such as --limit to request more than the default number of messages, but the command shown directly satisfies the requirement to fetch and acknowledge waiting messages.

**D is incorrect** because gcloud pubsub topics list-subscriptions shipment-events lists the subscriptions attached to the shipment-events topic. A filter can narrow the displayed subscription resources, but the command only discovers or verifies the relationship between a topic and its subscriptions. It does not access the message backlog, return message payloads, or acknowledge messages. This command could confirm that tracking-worker is associated with the topic, but the pull command must be used to consume messages from the subscription.

**Reference links**

- [docs.cloud.google.com/sdk/gcloud/reference/pubsub/subscriptions/pull](https://docs.cloud.google.com/sdk/gcloud/reference/pubsub/subscriptions/pull)
- [docs.cloud.google.com/pubsub/docs/publish-receive-messages-gcloud](https://docs.cloud.google.com/pubsub/docs/publish-receive-messages-gcloud)
- [docs.cloud.google.com/sdk/gcloud/reference/pubsub/subscriptions/seek](https://docs.cloud.google.com/sdk/gcloud/reference/pubsub/subscriptions/seek)

**Related notes:** [Pub/Sub](../04-events-integration/products/pub-sub.md)

</details>

[Back to index](#index)

---

### Q47

> BrightCart operates an online retail platform across two Google Cloud projects. The web application runs in network web-vpc with the IP range 172.16.0.0/16 in project-web, while the internal inventory services run in network services-vpc with the IP range 172.20.0.0/16 in project-services. The web application must communicate privately with the inventory services. BrightCart wants a simple, efficient, and cost-effective solution that follows Google-recommended practices. What should the company do?  

- **A.** Deploy OpenVPN servers to establish a connection between web-vpc and services-vpc.
- **B.** Configure VPC Network Peering between web-vpc and services-vpc.
- **C.** Create a Cloud Router in web-vpc and another Cloud Router in services-vpc.
- **D.** Establish a Cloud Interconnect connection between web-vpc and services-vpc.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because an OpenVPN connection could provide connectivity between the two networks, but it would require BrightCart to deploy, configure, secure, scale, patch, monitor, and maintain VPN server instances. The company would also need to manage VPN routing, certificates, availability, throughput, and failover. This introduces unnecessary infrastructure and operational overhead for connecting two VPC networks that are already hosted in Google Cloud. A self-managed VPN solution can also create performance bottlenecks and additional compute costs. VPC Network Peering provides a native managed solution that does not require VPN gateways or third-party software.

**B is correct** because VPC Network Peering directly connects two VPC networks and allows resources in each network to communicate by using internal IP addresses. The peered networks can belong to different Google Cloud projects, and the provided IP ranges do not overlap, which is required for exchanging subnet routes successfully. BrightCart must create a peering configuration from web-vpc to services-vpc and a corresponding configuration from services-vpc to web-vpc. After both sides are configured, eligible subnet routes are exchanged automatically. Traffic remains within Google’s network and does not require external IP addresses, VPN appliances, Cloud Routers, or physical connectivity. For direct communication between two Google Cloud VPC networks, VPC Network Peering is a simple, efficient, and cost-effective managed solution. BrightCart must still configure appropriate ingress and egress firewall rules because peering exchanges routes but does not automatically permit all traffic.

**C is incorrect** because Cloud Router is a managed Border Gateway Protocol control-plane service that dynamically exchanges routes with another network through products such as Cloud VPN, Cloud Interconnect, Network Connectivity Center, or a router appliance. Creating one Cloud Router in each VPC does not create a network connection or data path between the VPC networks. Additional connectivity resources and BGP sessions would still be required. Cloud Router is useful when dynamic routing is needed across hybrid or externally connected networks, but it is unnecessary for straightforward communication between two Google Cloud VPC networks.

**D is incorrect** because Cloud Interconnect is primarily designed to connect an on-premises network to Google Cloud through Dedicated Interconnect or Partner Interconnect, or to connect a network in another cloud provider through Cross-Cloud Interconnect. It is not intended to create a direct connection between two VPC networks that are already in Google Cloud. Cloud Interconnect would also introduce unnecessary physical or service-provider infrastructure, VLAN attachments, Cloud Routers, provisioning complexity, and recurring costs. VPC Network Peering is the appropriate native service for this two-VPC connectivity requirement.

**Reference links**

- [docs.cloud.google.com/vpc/docs/vpc-peering](https://docs.cloud.google.com/vpc/docs/vpc-peering)
- [docs.cloud.google.com/network-connectivity/docs/router/concepts/overview](https://docs.cloud.google.com/network-connectivity/docs/router/concepts/overview)
- [docs.cloud.google.com/network-connectivity/docs/interconnect/concepts/overview](https://docs.cloud.google.com/network-connectivity/docs/interconnect/concepts/overview)

**Related notes:** [VPC Network Peering and Shared VPC](../06-networking/products/vpc-network-peering-and-shared-vpc.md)

</details>

[Back to index](#index)

---

### Q48

> TensorPeak Labs is training a large language model with JAX. The workload relies heavily on large matrix operations and can distribute training across multiple accelerator chips. The required TPU generation is available in a location that meets the company’s deployment requirements. TensorPeak Labs wants purpose-built hardware optimized for this type of machine-learning workload. What should it choose?  

- **A.** A Filestore Basic instance
- **B.** One e2-small Compute Engine VM
- **C.** A Cloud NAT gateway
- **D.** Cloud TPU resources provisioned through Compute Engine

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a Filestore Basic instance is a managed network-attached file storage service, not a machine-learning accelerator. Filestore provides shared file systems that Compute Engine and Google Kubernetes Engine workloads can access by using the Network File System protocol. It could store training datasets, checkpoints, or other model artifacts, but it does not execute tensor operations or accelerate matrix calculations. Provisioning Filestore would not supply the specialized processing hardware required to train the model.

**B is incorrect** because an e2-small VM is a low-cost, general-purpose Compute Engine machine intended for workloads with modest CPU and memory requirements. It does not provide TPU hardware and would need to perform the model’s large matrix calculations on general-purpose virtual CPUs. This would deliver substantially less acceleration than purpose-built TPU resources and would not satisfy the requirement to distribute the training job across accelerator chips. Although a Compute Engine VM might be suitable for lightweight development, orchestration, or preprocessing, a single e2-small VM is not appropriate for this large distributed training workload.

**C is incorrect** because Cloud NAT is a managed network address translation service rather than a compute resource. It enables workloads without external IP addresses to establish outbound connections to the internet and other external destinations while preventing unsolicited inbound connections. Cloud NAT does not provide CPUs, GPUs, TPUs, memory for model execution, or matrix-processing capabilities. The team might use Cloud NAT as part of the workload’s network architecture, but it cannot perform or accelerate model training.

**D is correct** because Cloud TPUs are Google-designed application-specific integrated circuits built to accelerate machine-learning workloads dominated by tensor and matrix calculations. TPU chips contain specialized Matrix Multiplication Units that efficiently execute the large matrix operations commonly required during neural-network training. TPU-supported frameworks use the XLA compiler to optimize model computations for TPU hardware. Because the training job can be distributed, the team can provision a multi-chip TPU slice and divide the workload across the available accelerator chips. Through the TPU VM architecture, the team manages TPU resources using Compute Engine interfaces and can run its code directly on the associated TPU hosts. The team has also confirmed that the required TPU generation is available in an acceptable location, which is important because TPU versions and capacity vary by region and zone. This option therefore provides hardware specifically optimized for the model’s computation pattern while supporting distributed training.

**Reference links**

- [docs.cloud.google.com/tpu/docs/intro-to-tpu](https://docs.cloud.google.com/tpu/docs/intro-to-tpu)
- [docs.cloud.google.com/tpu/docs/system-architecture-tpu-vm](https://docs.cloud.google.com/tpu/docs/system-architecture-tpu-vm)
- [docs.cloud.google.com/compute/docs/regions-zones/tpu-regions-zones](https://docs.cloud.google.com/compute/docs/regions-zones/tpu-regions-zones)

**Related notes:** [Cloud TPU and GPU](../03-compute-containers/products/cloud-tpu-and-gpu.md)

</details>

[Back to index](#index)

---

### Q49

> FestivalNest has created a containerized website that publishes schedules and accepts registrations for a weekend music festival. Visitor traffic may increase sharply before performances and fall to zero during inactive periods. The company wants a fully managed deployment that automatically handles HTTP requests and minimizes compute costs. What should FestivalNest do?  

- **A.** Deploy the container image as a Cloud Run job.
- **B.** Deploy the container image to a Google Kubernetes Engine cluster in Standard mode.
- **C.** Deploy the container image as a Cloud Run service.
- **D.** Deploy the container image to a Google Kubernetes Engine cluster in Autopilot mode.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a Cloud Run job is designed for containerized tasks that perform work and then exit. Unlike a Cloud Run service, a job does not continuously listen for incoming HTTP requests or provide a web endpoint for user traffic. Cloud Run jobs are appropriate for workloads such as batch processing, scheduled report generation, database migrations, and data transformation. Because FestivalNest needs to operate an interactive website that receives unpredictable HTTP requests, it requires a Cloud Run service rather than a Cloud Run job.

**B is incorrect** because Google Kubernetes Engine in Standard mode requires the company to make more infrastructure and cluster-management decisions. Although GKE Standard can run the containerized application and can scale workloads, the administrators are responsible for configuring and managing node pools, capacity, workload scaling, upgrades, security settings, and other cluster resources. The application is a straightforward HTTP website for a temporary event and does not require Kubernetes-specific capabilities. Running a Standard cluster would therefore introduce unnecessary administrative effort and could leave provisioned resources running during periods with little or no traffic, making it less suitable for minimizing costs.

**C is correct** because a Cloud Run service is designed to host containerized applications that listen for and respond to incoming HTTP requests. Cloud Run provides a managed HTTPS endpoint and automatically adds or removes service instances according to request volume. This allows FestivalNest to handle sudden traffic increases without manually provisioning servers or managing a Kubernetes cluster. By default, the service can scale down to zero instances when it receives no requests, which is particularly cost-effective for a local event website with irregular or temporary traffic. Cloud Run uses a pay-per-use model, so the company primarily pays for resources consumed while requests are being processed. This combination of automatic scaling, scale-to-zero behavior, and minimal infrastructure management makes a Cloud Run service the best choice.

**D is incorrect** because Google Kubernetes Engine in Autopilot mode is more fully managed than Standard mode and reduces the need to manage nodes directly. It can automatically provision infrastructure for Kubernetes workloads and is preferable to Standard mode when an organization requires Kubernetes but wants Google Cloud to manage more of the underlying environment. However, FestivalNest has a simple containerized HTTP application and no stated requirement for Kubernetes features such as complex multi-service orchestration, Kubernetes APIs, specialized scheduling, or cluster-level configuration. GKE Autopilot would still require Kubernetes objects and cluster administration, creating more complexity than Cloud Run. For a request-driven website with unpredictable traffic and a requirement to minimize costs, the simpler Cloud Run service and its native scale-to-zero behavior are more appropriate.

**Reference links**

- [docs.cloud.google.com/run/docs/overview/what-is-cloud-run](https://docs.cloud.google.com/run/docs/overview/what-is-cloud-run)
- [docs.cloud.google.com/run/docs/create-jobs](https://docs.cloud.google.com/run/docs/create-jobs)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/choose-cluster-mode](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/choose-cluster-mode)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md)

</details>

[Back to index](#index)

---

### Q50

> Northwind Media uses a Cloud SQL instance to support an internal content-management application. An employee named Priya receives an error when trying to access the database, but another employee named Daniel can connect successfully. You need to begin troubleshooting Priya’s access problem by following Google-recommended practices. What should you do first?  

- **A.** Check whether VPC firewall rules are blocking Priya’s connection.
- **B.** Grant Priya the Identity and Access Management Project Owner role.
- **C.** Inspect recent project configuration changes for accidental permission modifications.
- **D.** Examine the complete error message Priya received.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because checking network controls before understanding the reported error assumes that the failure is related to connectivity. Cloud SQL access can fail for many reasons, including missing IAM permissions, incorrect database credentials, an invalid database user, an expired authentication token, an unauthorized source IP address, a disabled API, an incorrect instance connection name, or a network routing problem. In addition, VPC firewall rules are not always the relevant control for a Cloud SQL connection. The applicable network configuration depends on whether the user connects through a public IP address, private IP address, Cloud SQL Auth Proxy, Cloud SQL connectors, or another connection method. Because Daniel can connect successfully, the database is likely available, but this does not prove that Priya’s issue is caused by a firewall rule. The error message should be reviewed first because it can indicate whether network troubleshooting is necessary.

**B is incorrect** because the Project Owner role is a highly privileged basic IAM role that grants broad administrative access across project resources. Assigning this role merely to troubleshoot database access violates the principle of least privilege and can expose the project to unnecessary security risk. Depending on the connection method and requested operation, Priya might need a specific Cloud SQL IAM role, permission to use the Cloud SQL instance, IAM database authentication permissions, or privileges assigned inside the database engine. IAM permissions and database-level privileges are separate access-control layers. The administrator should identify the exact cause of the failure before changing any permissions and should then grant only the minimum required role or database privilege.

**C is incorrect** because reviewing recent configuration changes can be a useful troubleshooting step, especially when access previously worked and then suddenly stopped. A modified IAM policy, removed database user, changed authorized network, disabled API, altered SSL configuration, or updated instance setting could cause an access failure. However, this is not the first step because the administrator does not yet know which category of configuration is relevant. Examining every recent change could be time-consuming and might lead to unnecessary modifications. The error message should first be used to narrow the problem to authentication, authorization, networking, database credentials, instance availability, or another specific area. After identifying the likely failure domain, recent changes related to that domain can be investigated.

**D is correct** because the first troubleshooting step should be to collect and examine the complete error message, including any error code, timestamp, connection method, database engine message, and operation that Priya attempted. The error message provides the most direct evidence about the failure and helps the administrator avoid making unsupported assumptions. For example, a permission-denied message suggests an IAM or database authorization issue, an access-denied message might indicate invalid database credentials or insufficient database privileges, and a timeout or unreachable-host message suggests a connectivity or network configuration issue. After reviewing the error, the administrator can investigate the relevant IAM policies, database users, authorized networks, firewall settings, logs, or recent configuration changes. This evidence-based approach follows recommended troubleshooting practices and reduces the risk of applying unnecessary or overly broad changes.

**Reference links**

- [docs.cloud.google.com/sql/docs/debugging-connectivity](https://docs.cloud.google.com/sql/docs/debugging-connectivity)
- [docs.cloud.google.com/sql/docs/troubleshooting](https://docs.cloud.google.com/sql/docs/troubleshooting)
- [docs.cloud.google.com/iam/docs/using-iam-securely](https://docs.cloud.google.com/iam/docs/using-iam-securely)

**Related notes:** [Cloud SQL](../05-storage-databases-data/products/cloud-sql.md)

</details>

[Back to index](#index)

---
