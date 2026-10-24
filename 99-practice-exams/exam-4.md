# Practice Exam 4

[Previous](exam-3.md) · [All exams](README.md) · [Next](exam-5.md)

50 questions in the original English. Open "Show answer" under each question to see the correct answer and the explanation.

## Index

| Q | Question |
|---|---|
| [Q1](#q1) | BluePeak Media manages the Google Cloud infrastructure for its video-streaming platform. T... |
| [Q2](#q2) | PixelWave Media runs several microservices in a Google Kubernetes Engine cluster. Its thum... |
| [Q3](#q3) | StreamForge operates a video-processing API on Cloud Run. The engineering team has created... |
| [Q4](#q4) | BrightCart Retail has four existing Google Cloud projects. The Finance department is start... |
| [Q5](#q5) | OrbitLedger develops GlobeAccounts, a financial recordkeeping application that stores stru... |
| [Q6](#q6) | BrightTrail, an online travel platform, runs its booking, recommendation, and analytics wo... |
| [Q7](#q7) | PixelNest, a digital media company, runs an image-processing service on Compute Engine VM ... |
| [Q8](#q8) | BrightCart Analytics generates a full customer-demand forecast every month. The batch job ... |
| [Q9](#q9) | Northwind Health is consolidating two independently managed business units. One unit opera... |
| [Q10](#q10) | Northstar Analytics hosts an internal reporting service on a Linux Compute Engine VM. A te... |
| [Q11](#q11) | ParcelPulse operates a delivery-tracking platform on Google Cloud. After detecting an unau... |
| [Q12](#q12) | HarborTrack runs inventory applications on Compute Engine and in its private data center. ... |
| [Q13](#q13) | BlueOrbit Logistics developed a shipment-tracking application on a developer workstation. ... |
| [Q14](#q14) | BrightCart runs its customer portal on Compute Engine VMs in the storefront-services proje... |
| [Q15](#q15) | DataForge Labs runs an Apache Hadoop analytics workload on a Dataproc cluster in one VPC n... |
| [Q16](#q16) | TripSphere is developing a global travel-booking service that will store reservation and p... |
| [Q17](#q17) | Northstar Analytics uses Workforce Identity Federation to give consultants from partner co... |
| [Q18](#q18) | HarborCart, an online retail platform, has acquired a delivery application named SwiftParc... |
| [Q19](#q19) | VoxLoom, a customer-research platform, stores newly uploaded interview recordings in a Clo... |
| [Q20](#q20) | NimbusCart operates an online marketplace using Google Cloud resources across several proj... |
| [Q21](#q21) | Northstar Books operates a public ecommerce website on Compute Engine virtual machines in ... |
| [Q22](#q22) | AtlasStream Media has installed the gcloud CLI on an administrator’s workstation and authe... |
| [Q23](#q23) | ConnectSphere operates a real-time messaging gateway on a Compute Engine managed instance ... |
| [Q24](#q24) | BluePeak Solutions is organizing the Google Cloud environment for a new online education p... |
| [Q25](#q25) | RouteWave is deploying a shipment-tracking service to Google Kubernetes Engine (GKE). The ... |
| [Q26](#q26) | NovaLedger is moving its public documentation website and a monthly billing process to Goo... |
| [Q27](#q27) | BrightCart, an online retail company, is preparing to migrate its data-center applications... |
| [Q28](#q28) | AeroPulse, a flight analytics company, has several application teams that create Google Cl... |
| [Q29](#q29) | BrightLedger runs a payment-processing service on a Compute Engine instance named ledger-p... |
| [Q30](#q30) | HarborTrack Logistics runs a Java shipment-processing application in its private data cent... |
| [Q31](#q31) | HarborLink Media is connecting a new Google Cloud VPC network to its corporate data center... |
| [Q32](#q32) | MarketWave operates an online retail platform through an existing Cloud Run service. The e... |
| [Q33](#q33) | NovaCart Labs is creating a new online ordering platform and needs a Jenkins server to bui... |
| [Q34](#q34) | MetroFleet Scooters rents electric delivery scooters to businesses across several cities. ... |
| [Q35](#q35) | NovaArcade Studios operates RealmRush, a real-time multiplayer strategy game used by playe... |
| [Q36](#q36) | LedgerNest runs a stateful transaction-processing service on Google Kubernetes Engine (GKE... |
| [Q37](#q37) | NimbusSketch, a collaborative design platform, allows developers to create experimental re... |
| [Q38](#q38) | BrightCart operates an online marketplace with several services running across multiple Go... |
| [Q39](#q39) | StreamForge Studios maintains a large collection of production footage on its on-premises ... |
| [Q40](#q40) | NexaFleet manages Linux Compute Engine instances across dozens of Google Cloud projects. T... |
| [Q41](#q41) | HarborCart, an online retail company, uses Terraform to manage its Google Cloud infrastruc... |
| [Q42](#q42) | BlueOrbit Health is planning a patient scheduling application with a web interface, an API... |
| [Q43](#q43) | LumenFleet Systems wants to deploy a Compute Engine VM for a new route-planning service. T... |
| [Q44](#q44) | SkyRoute Logistics operates applications across Google Cloud projects Fleet-Core, Dispatch... |
| [Q45](#q45) | BrightPath Retail operates a sales forecasting portal that queries BigQuery. An external r... |
| [Q46](#q46) | Northstar Analytics uses a GitHub Actions pipeline to publish application updates to a Clo... |
| [Q47](#q47) | SilverLine Commerce uses Workforce Identity Federation to provide external incident-respon... |
| [Q48](#q48) | BlueHarbor Media runs a content-processing application on GKE. The application needs to up... |
| [Q49](#q49) | SkyForge Media operates an automated release pipeline in a third-party cloud platform. The... |
| [Q50](#q50) | BluePeak Insurance has a governance team that must view resources across all current and f... |

---

### Q1

> BluePeak Media manages the Google Cloud infrastructure for its video-streaming platform. The engineering team plans to modify several shared resources and wants other team members to review the proposed configuration before the changes are deployed. The company needs a repeatable and auditable approach that follows Google-recommended practices. What should the team do?  

- **A.** Define the proposed infrastructure changes in Terraform configurations for Infrastructure Manager and store the files in a Cloud Storage bucket.
- **B.** Define the proposed infrastructure changes in Terraform configurations for Infrastructure Manager and store the files in Secure Source Manager.
- **C.** Apply the changes in a test project, run gcloud compute instances list, and store the command output in a shared Cloud Storage bucket.
- **D.** Apply the changes in a test project, run gcloud compute instances list, and commit the command output to Secure Source Manager.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because defining the required infrastructure declaratively in Terraform configurations for Infrastructure Manager is appropriate, but a Cloud Storage bucket is not the best repository for collaborative infrastructure change management. Infrastructure Manager can deploy Terraform configurations stored in Cloud Storage, but a bucket does not inherently provide the complete Git-based workflow expected for reviewing proposed changes. It does not provide native branches, pull or merge requests, line-by-line code review, commit history, or standard approval workflows. Cloud Storage object versioning can preserve older object generations when it is enabled, but that is not equivalent to source version control. Therefore, this approach can technically store and deploy the configuration, but it is not the best choice when the main requirement is to share proposed changes with a team and follow recommended collaboration practices.

**B is correct** because Google recommends managing infrastructure declaratively as infrastructure as code and storing the configuration in a version-controlled source repository. Infrastructure Manager deploys and manages Google Cloud resources from Terraform configurations. Secure Source Manager provides managed Git repositories where the team can create branches, commit configuration changes, compare revisions, review proposed updates, use pull requests, record approvals, maintain an audit trail, and revert changes when necessary. Team members can review the intended infrastructure state before it is deployed instead of trying to infer changes from already-created resources. The team can also generate an Infrastructure Manager preview, which runs the equivalent of a Terraform plan, to identify which resources would be created, modified, or deleted. This combination of declarative configuration, version control, peer review, and deployment previews provides a repeatable, traceable, and collaborative infrastructure-management workflow.

**C is incorrect** because this approach applies the changes before the rest of the team reviews them. A recommended infrastructure-as-code workflow defines and reviews the desired changes before deployment. In addition, gcloud compute instances list displays information about existing Compute Engine VM instances; it does not describe the Terraform configuration that produced them, show the complete proposed change set, or represent resources such as VPC networks, firewall policies, Cloud Storage buckets, IAM bindings, and managed services. Saving the command output in Cloud Storage creates only a static inventory snapshot. It does not provide declarative configuration, revision history, code review, change approval, or a reliable method for reproducing the infrastructure.

**D is incorrect** because committing the output of gcloud compute instances list to Secure Source Manager does not turn that output into infrastructure as code. The command reports the current state of Compute Engine instances after the changes have already been applied, rather than describing the desired state before deployment. Although Secure Source Manager provides version control, it must contain the actual Terraform configurations for its collaboration and audit features to be useful for infrastructure management. A list of VM instances cannot be used by Infrastructure Manager to reproduce the environment, calculate all proposed infrastructure changes, manage resource dependencies, or safely roll back the configuration. The correct workflow is to commit the declarative Terraform configuration itself and have the team review it before applying the changes.

**Reference links**

- [docs.cloud.google.com/infrastructure-manager/docs/overview](https://docs.cloud.google.com/infrastructure-manager/docs/overview)
- [docs.cloud.google.com/docs/terraform/best-practices/version-control](https://docs.cloud.google.com/docs/terraform/best-practices/version-control)
- [docs.cloud.google.com/secure-source-manager/docs/overview](https://docs.cloud.google.com/secure-source-manager/docs/overview)

**Related notes:** [Infrastructure Manager](../08-iac-platform-ai/products/infrastructure-manager.md) · [Secure Source Manager](../08-iac-platform-ai/products/secure-source-manager.md)

</details>

[Back to index](#index)

---

### Q2

> PixelWave Media runs several microservices in a Google Kubernetes Engine cluster. Its thumbnail-generation service performs CPU-intensive image transformations but consumes relatively little memory. The remaining services, including authentication, billing, and content management, run efficiently on general-purpose machine types. You need to select an infrastructure configuration that uses cluster resources efficiently. What should you do?  

- **A.** Give the thumbnail-generation Pods a higher Kubernetes PriorityClass than the Pods for the remaining services.
- **B.** Create a node pool with compute-optimized machine types for the thumbnail-generation service, and continue running the remaining services in a node pool with general-purpose machine types.
- **C.** Run the thumbnail-generation service in the general-purpose node pool, and create a compute-optimized node pool for the remaining services.
- **D.** Define CPU and memory resource requests only for the thumbnail-generation deployment, and leave the resource requests for all remaining services unchanged.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Kubernetes pod priority determines the order in which pending Pods are scheduled and can influence which lower-priority Pods are preempted when cluster resources are insufficient. It does not change the CPU-to-memory ratio or machine type of the nodes on which the Pods run. Giving the thumbnail-generation service a higher priority might allow it to be scheduled before other services, but it would not provide the compute-optimized infrastructure required for a CPU-intensive workload. It could also unnecessarily displace other services without improving the overall efficiency of the cluster.

**B is correct** because Google Kubernetes Engine node pools allow a single cluster to contain groups of nodes with different Compute Engine machine types. Compute-optimized machine types provide high performance per CPU core and are intended for compute-bound workloads, making them appropriate for CPU-intensive image processing that requires comparatively little memory. The other microservices can remain on general-purpose nodes because those machine types provide a balanced CPU-to-memory ratio suitable for their requirements. The thumbnail-generation Pods should be directed to the compute-optimized node pool by using mechanisms such as node labels with nodeSelector or node affinity. Taints and tolerations can also be used when stronger workload isolation is required. This arrangement matches each workload to the most suitable hardware and avoids paying for unnecessary memory on the CPU-intensive nodes.

**C is incorrect** because it assigns the machine families to the opposite workloads. The thumbnail-generation service is CPU intensive, so placing it on general-purpose nodes would not provide the best CPU-focused performance and resource ratio. The remaining services are already optimized for general-purpose machine types, so moving them to compute-optimized nodes could waste CPU capacity or provide an unsuitable CPU-to-memory balance. This configuration would reduce rather than improve resource efficiency.

**D is incorrect** because resource requests tell the Kubernetes scheduler how much CPU and memory a Pod needs, but they do not by themselves create nodes with a more appropriate CPU-to-memory ratio. Accurate resource requests are important for scheduling, autoscaling, capacity planning, and preventing resource contention, but the image-rendering Pods would still run on general-purpose nodes unless node pools and scheduling constraints were configured appropriately. In addition, leaving the other microservices at default or unspecified resource requests is not a recommended way to optimize the cluster. Each workload should have realistic resource requests, but resource requests alone do not replace the need for a compute-optimized node pool in this scenario.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/node-pools](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/node-pools)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/node-pools](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/node-pools)
- [docs.cloud.google.com/compute/docs/compute-optimized-machines](https://docs.cloud.google.com/compute/docs/compute-optimized-machines)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q3

> StreamForge operates a video-processing API on Cloud Run. The engineering team has created a new revision and wants to deploy it without immediately sending production traffic to it. Before shifting traffic, StreamForge must keep three instances of the new revision running and ready to handle requests without container startup delay. The team wants the simplest solution with the least ongoing administration. What should StreamForge do?  

- **A.** Deploy the new revision without serving it immediately, and use a load-testing tool to send requests to the revision before updating the traffic allocation.
- **B.** Configure service-level autoscaling and set the minimum number of instances to 3.
- **C.** Configure revision-level autoscaling on the new revision and set the minimum number of instances to 3.
- **D.** Configure revision-level autoscaling on the currently serving revision and set the minimum number of instances to 3.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because sending simulated traffic to the new revision might temporarily cause Cloud Run to start instances, but it does not guarantee that three instances will remain available until production traffic is redirected. After the simulated traffic stops, Cloud Run can scale the revision back down when the instances are no longer required. The team would also need to deploy the revision without traffic, assign a revision tag or otherwise obtain a revision-specific URL, operate a traffic-generation tool, confirm that the expected number of instances has started, and coordinate the traffic migration. This introduces unnecessary administrative overhead and provides no persistent minimum-instance guarantee. The native minimum-instances setting is specifically designed to keep instances warm and reduce startup latency.

**B is incorrect** because service-level minimum instances are allocated among revisions according to the service’s configured traffic distribution. Before the traffic migration, the new revision receives no production traffic, so a service-level minimum of three does not guarantee that three instances will be assigned to that new revision. The instances could remain allocated to the existing revision that currently receives the traffic. Service-level minimum instances are useful when the goal is to maintain a minimum amount of capacity for the Cloud Run service as a whole, particularly across revisions included in a traffic split. They are not the appropriate choice when a specific revision that currently receives no traffic must have a guaranteed number of warm instances before the traffic allocation changes.

**C is correct** because a revision-level minimum-instances setting applies directly to the selected Cloud Run revision, independent of the percentage of production traffic currently assigned to that revision. Configuring the new revision with a minimum of three instances causes Cloud Run to start and maintain at least three instances for that revision even while it receives no production traffic. These instances are initialized and ready to accept requests when the team subsequently redirects traffic, reducing the risk of startup latency during the rollout. This approach uses a native Cloud Run autoscaling feature and does not require custom load generation, scheduled requests, deployment scripts, or continuous manual monitoring. The organization should remember that maintaining minimum instances can incur charges even when the instances are idle, but this is the intended tradeoff when immediately available capacity is required.

**D is incorrect** because configuring minimum instances on the existing revision keeps instances of the old application version ready, not instances of the newly deployed version. Cloud Run revisions are immutable, and each revision has its own container image and revision-level configuration. Warm instances belonging to the existing revision cannot be converted into instances of the new revision or used to eliminate the new revision’s startup time. When traffic is moved to the new revision, Cloud Run would still need to start instances containing the new application version unless that new revision had its own minimum-instances configuration. This option therefore consumes resources without satisfying the requirement.

**Reference links**

- [docs.cloud.google.com/run/docs/configuring/min-instances](https://docs.cloud.google.com/run/docs/configuring/min-instances)
- [docs.cloud.google.com/run/docs/managing/revisions](https://docs.cloud.google.com/run/docs/managing/revisions)
- [docs.cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration](https://docs.cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md)

</details>

[Back to index](#index)

---

### Q4

> BrightCart Retail has four existing Google Cloud projects. The Finance department is starting a new expense-analysis initiative, and all Google Cloud charges generated by this initiative must be billed exclusively to Finance. What should you do?  

- **A.** Verify that you have the Billing Account Administrator IAM role on an existing Finance project, and link the initiative project to the Finance Cloud Billing account.
- **B.** Verify that you have the Billing Account Administrator IAM role for the organization, create a new Google Cloud project for the Finance initiative, and apply the project label department:finance to its services.
- **C.** Verify that you have the appropriate organization-level permissions, create a new Google Cloud project for the Finance initiative, and link the project to a Finance Cloud Billing account.
- **D.** Verify that you have the Organization Administrator IAM role, create a new Google Cloud project for the Finance initiative, and apply the project label department:finance to its services.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the option does not include creating a dedicated project for the new initiative, even though it refers to linking an initiative project. A Google Cloud project provides a clear resource, access-control, quota, and cost-management boundary. Additionally, the Billing Account Administrator role is granted on a Cloud Billing account rather than on an individual project. Linking a project to a billing account also requires permissions on both the project and the target Cloud Billing account.

**B is incorrect** because labels help categorize resources and analyze costs, but they do not determine which Cloud Billing account pays for a project’s usage. Applying department:finance can make costs easier to filter in billing reports or exported billing data, but the charges are still sent to the Cloud Billing account linked to the project. Additionally, Cloud Billing permissions do not automatically grant permission to create projects in the organization.

**C is correct** because creating a dedicated project establishes a separate cost-management boundary for the Finance initiative, and linking that project to the Finance Cloud Billing account causes the project’s billable Google Cloud usage to be charged to that account. This is more reliable than depending on labels across services because all supported billable resources in the project are associated with the project’s linked billing account. In an actual least-privilege implementation, the administrator needs the Project Creator role on the relevant organization or folder, the Billing Account User role on the Finance Cloud Billing account, and suitable project-side permissions such as Project Billing Manager. The Organization Administrator role by itself does not automatically provide every billing permission, but C is the only option that contains the required project and billing-account separation design.

**D is incorrect** because creating a separate project improves resource and cost isolation, but assigning labels does not route the project’s charges to a department-specific Cloud Billing account. Labels are metadata used for organization, filtering, and cost allocation analysis. Without linking the new project to the Finance Cloud Billing account, its charges would be paid through whichever billing account is linked to the project. The Organization Administrator role also does not, by itself, provide all permissions required to associate a project with a Cloud Billing account.

**Reference links**

- [docs.cloud.google.com/resource-manager/docs/creating-managing-projects](https://docs.cloud.google.com/resource-manager/docs/creating-managing-projects)
- [docs.cloud.google.com/billing/docs/how-to/modify-project](https://docs.cloud.google.com/billing/docs/how-to/modify-project)
- [docs.cloud.google.com/resource-manager/docs/labels-overview](https://docs.cloud.google.com/resource-manager/docs/labels-overview)

**Related notes:** [Cloud Billing](../07-operations-cost/products/cloud-billing.md)

</details>

[Back to index](#index)

---

### Q5

> OrbitLedger develops GlobeAccounts, a financial recordkeeping application that stores structured relationships among customers, accounts, subscriptions, and transactions. The company expects users from many countries, but it cannot predict how quickly the workload will grow. OrbitLedger needs a relational database that can scale horizontally as demand increases while requiring minimal application and infrastructure changes. Which storage solution should it use?  

- **A.** Cloud SQL
- **B.** Firestore
- **C.** Cloud Spanner
- **D.** Bigtable

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Cloud SQL is a fully managed relational database service supporting MySQL, PostgreSQL, and SQL Server, but an individual Cloud SQL instance primarily scales vertically by increasing its CPU, memory, and storage resources. Read replicas can distribute read-only workloads, but writes generally remain dependent on the primary instance. As the application grows globally, the team might need to resize instances, add replicas, configure replication, route traffic, and plan for instance-specific resource limits. Cloud SQL is suitable for conventional relational applications with moderate or predictable scaling requirements, but it is not the best solution when the user population is unknown and the database must scale horizontally with minimal architectural changes.

**B is incorrect** because Firestore is a fully managed, serverless NoSQL document database that automatically scales as application traffic grows. Although this automatic scaling would reduce operational work, Firestore stores information as documents organized into collections rather than in relational tables. Relationships are commonly represented by document references, duplicated data, embedded objects, or application-level logic. This can be effective for mobile and web applications designed around a document data model, but the requirement specifically calls for relational data. Selecting Firestore could require redesigning the application’s relational schema and access patterns, so it is not the most appropriate choice.

**C is correct** because Cloud Spanner is a fully managed, distributed database that combines relational database capabilities with horizontal scalability. It supports schemas, SQL queries, secondary indexes, ACID transactions, and strong transactional consistency, making it appropriate for structured data with relationships among users and other application entities. Spanner automatically partitions data into splits and distributes those splits as the database grows. The organization can increase processing capacity without redesigning the database around manual sharding or migrating to a different storage technology. It also provides regional, dual-region, and multi-region configurations, allowing the application to serve a global user base with high availability. These capabilities make Cloud Spanner the best option for relational data, unpredictable user growth, and minimal configuration or application changes during scaling.

**D is incorrect** because Bigtable is a distributed NoSQL wide-column and key-value database designed for very large workloads that require high throughput and low-latency access by row key. It is well suited to time-series information, telemetry, event data, personalization, and large-scale operational analytics. However, Bigtable does not provide a traditional relational data model with joins, foreign-key relationships, or general-purpose multirow relational transactions. Applications must design row keys and denormalize data according to specific query patterns. Using Bigtable for this requirement would therefore require substantial data-model and application changes and would not preserve the relational characteristics requested in the scenario.

**Reference links**

- [docs.cloud.google.com/spanner/docs](https://docs.cloud.google.com/spanner/docs)
- [docs.cloud.google.com/sql/docs](https://docs.cloud.google.com/sql/docs)
- [docs.cloud.google.com/bigtable/docs/overview](https://docs.cloud.google.com/bigtable/docs/overview)

</details>

[Back to index](#index)

---

### Q6

> BrightTrail, an online travel platform, runs its booking, recommendation, and analytics workloads across several Google Cloud projects connected to one Cloud Billing account. The finance team needs a dashboard that automatically updates and calculates internal metrics such as adjusted cost per booking and department-specific cost allocations. What should BrightTrail do?  

- **A.** Use the Reports page in the Google Cloud console to visualize costs for the projects.
- **B.** Use the Cost breakdown page in the Google Cloud console to visualize costs for the projects.
- **C.** Download the Cost table data as a CSV file and build a Data Studio dashboard using the exported file.
- **D.** Enable Cloud Billing data export to BigQuery for the Cloud Billing account and build a Data Studio dashboard using the BigQuery data.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because the Cloud Billing Reports page is intended for interactive, at-a-glance analysis of existing billing metrics. It supports time ranges, filters, grouping by dimensions such as project, service, SKU, location, and labels, and predefined cost calculations involving credits and savings. However, it is not designed to implement arbitrary company-specific business logic such as adjusted cost per booking, internal chargeback formulas, or department-specific allocation rules. Although report views can be customized and downloaded, the Reports page alone does not provide the flexible data-processing layer required to calculate custom metrics dynamically and maintain a fully automated external dashboard.

**B is incorrect** because the Cost breakdown report primarily explains how gross usage costs are transformed into final costs after negotiated savings, credits, taxes, adjustments, and other billing components. It is useful for understanding savings and reconciling overall charges, but it does not provide a general-purpose analytics environment for implementing custom organizational formulas. Its available dimensions, filters, and calculations are predefined by Cloud Billing. Therefore, it cannot adequately support dynamically calculated company-specific metrics or serve as the automated data foundation for a customized financial dashboard.

**C is incorrect** because a CSV downloaded from the Cost table is a static snapshot of the billing data available at the time of download. The Cost table can provide detailed project-level, service-level, and SKU-level invoice information, but downloading the file from the console is not an automatically updating data pipeline. New billing records would require another download and a replacement or upload of the CSV data used by Data Studio. This creates manual operational work, introduces the possibility of outdated dashboard data, and does not satisfy the requirement to automate the process. CSV files can be useful for one-time or offline analysis, but they are not the preferred source for a continuously refreshed billing dashboard.

**D is correct** because Cloud Billing data export automatically sends detailed cost and usage information from the Cloud Billing account to tables in a BigQuery dataset. Because all the projects are linked to the same billing account, the exported data can provide a centralized billing dataset that includes project, service, SKU, usage, cost, credit, label, and other relevant attributes. BrightTrail can use BigQuery SQL, views, scheduled queries, or Data Studio calculated fields to apply its own allocation rules and derive metrics such as adjusted cost per booking or department-specific spending. Data Studio can connect directly to a BigQuery table, view, or custom query, allowing the dashboard to retrieve updated data without repeatedly downloading files. This architecture provides the automation, flexibility, scalability, and customized calculations required by the scenario.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery)
- [docs.cloud.google.com/billing/docs/how-to/reports](https://docs.cloud.google.com/billing/docs/how-to/reports)
- [docs.cloud.google.com/data-studio/connect-to-google-bigquery](https://docs.cloud.google.com/data-studio/connect-to-google-bigquery)

**Related notes:** [Looker Studio](../05-storage-databases-data/products/looker-studio.md)

</details>

[Back to index](#index)

---

### Q7

> PixelNest, a digital media company, runs an image-processing service on Compute Engine VM instances in a custom Virtual Private Cloud network. The VM instances have only internal IP addresses, and organizational security rules prohibit internet access. The service must retrieve design assets from a Cloud Storage bucket in the same Google Cloud project. What should PixelNest do?  

- **A.** Configure Private services access for the Cloud Storage bucket.
- **B.** Add storage.googleapis.com as a restricted service in a VPC Service Controls perimeter and place the project inside the perimeter.
- **C.** Enable Private Google Access on the subnet used by the Compute Engine VM instances.
- **D.** Configure Cloud NAT and route requests to a dedicated external IP address assigned to the Cloud Storage bucket.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Private services access is used to establish private connectivity between a consumer VPC network and supported service producer networks through VPC Network Peering. It commonly supports managed services that require private IP connectivity from a customer VPC, but it is not configured directly on a Cloud Storage bucket and is not the standard mechanism for VM instances with only internal IP addresses to reach Google APIs such as Cloud Storage. Access to Cloud Storage through Google API endpoints is provided by Private Google Access or, in more specialized designs, Private Service Connect endpoints for Google APIs.

**B is incorrect** because VPC Service Controls provides a security boundary around supported Google Cloud services to reduce data-exfiltration risks. Adding Cloud Storage as a restricted service and placing the project inside a service perimeter can control which identities and networks are permitted to access protected resources, but it does not independently provide network connectivity from VM instances that have only internal IP addresses. The VM subnet would still need Private Google Access or another supported private connectivity mechanism to reach the Cloud Storage API. VPC Service Controls and Private Google Access can be used together, but the service perimeter alone does not meet the connectivity requirement.

**C is correct** because Private Google Access allows Compute Engine VM instances that have only internal IP addresses to communicate with supported Google APIs and services, including Cloud Storage. Private Google Access is enabled on the subnet containing the VM instances rather than on each individual VM or Cloud Storage bucket. After it is enabled, traffic from eligible VM instances can reach Google API endpoints without assigning external IP addresses to the instances and without sending the traffic through the public internet. The application must still have appropriate Identity and Access Management permissions for the bucket, and the VPC network must have suitable routes, firewall rules, and DNS configuration, but enabling Private Google Access is the required networking solution described by the question.

**D is incorrect** because Public Cloud NAT is intended to provide outbound connectivity for resources that do not have external IP addresses, including connectivity to internet destinations. This conflicts with the requirement that the VM instances must not connect to the internet. Cloud NAT is also a distributed, managed service rather than a NAT VM instance. Additionally, a Cloud Storage bucket does not receive a dedicated external IP address to which a static route can be directed. Cloud Storage is accessed through Google API service endpoints, so Private Google Access is the appropriate solution.

**Reference links**

- [docs.cloud.google.com/vpc/docs/private-google-access](https://docs.cloud.google.com/vpc/docs/private-google-access)
- [docs.cloud.google.com/vpc/docs/configure-private-google-access](https://docs.cloud.google.com/vpc/docs/configure-private-google-access)
- [docs.cloud.google.com/nat/docs/overview](https://docs.cloud.google.com/nat/docs/overview)

**Related notes:** [Private Google Access](../06-networking/products/private-google-access.md)

</details>

[Back to index](#index)

---

### Q8

> BrightCart Analytics generates a full customer-demand forecast every month. The batch job takes approximately 34 hours, does not require network connectivity while running, and cannot resume from a checkpoint; if interrupted, it must restart from the beginning. BrightCart wants to migrate the job to Google Cloud and minimize infrastructure costs without preventing the job from completing. What should BrightCart do?  

- **A.** Run the batch job on a Compute Engine Preemptible VM.
- **B.** Containerize the job and run it on a Google Kubernetes Engine cluster that uses Preemptible VM nodes.
- **C.** Run the job on a standard Compute Engine VM and start and stop the VM according to the monthly processing schedule.
- **D.** Create an instance template that enables Preemptible VMs, create a managed instance group from the template, and configure autoscaling based on target CPU utilization.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a Compute Engine Preemptible VM is always stopped after running for a maximum of 24 hours and can also be stopped earlier when Compute Engine needs to reclaim capacity. Because the batch job requires approximately 34 uninterrupted hours and cannot resume from a checkpoint, it cannot finish within the guaranteed maximum lifetime of a Preemptible VM. Every forced stop would cause the entire job to restart, wasting the compute time already consumed. Preemptible VMs are appropriate for fault-tolerant, distributed, checkpoint-enabled, or short-running batch workloads. Although Spot VMs are the newer alternative and do not have the same fixed 24-hour maximum runtime, they can still be preempted at any time and would remain unsuitable when reliable uninterrupted execution is required.

**B is incorrect** because Google Kubernetes Engine does not remove the underlying interruption limitation of Preemptible VM nodes. A Preemptible VM used as a GKE node can still be terminated within 24 hours or earlier because of capacity reclamation. Kubernetes could recreate the Pod on another node, but the application would restart from the beginning because it does not support checkpointing. The additional GKE control-plane, cluster, containerization, scheduling, and operational complexity also provides no benefit for a single monthly batch process that needs only one machine. GKE is more suitable when workloads require container orchestration, horizontal scaling, multiple replicas, service discovery, or coordinated processing across several workers.

**C is correct** because a standard Compute Engine VM can remain running for the entire 34-hour batch process without the mandatory 24-hour termination that applies to Preemptible VMs. BrightCart can start the VM shortly before the monthly job begins and stop it immediately after processing finishes. Compute charges for vCPU and memory do not continue while the VM is stopped, although charges for retained resources such as Persistent Disk storage can still apply. This approach therefore combines reliable execution with cost control: the company pays for the VM’s compute capacity only during the relatively short monthly processing window and avoids the complexity of operating a Kubernetes cluster or managed instance group.

**D is incorrect** because a managed instance group with Preemptible VMs still uses instances that are subject to preemption and the 24-hour maximum runtime. The managed instance group can recreate a terminated VM, but recreating the VM does not preserve the batch process’s in-memory execution state. The job would restart rather than continue from where it stopped. Target CPU utilization is an autoscaling signal designed to add or remove instances in response to aggregate CPU demand. It does not make a single, non-distributed batch job complete faster unless the application has been specifically designed to divide work across multiple instances. This design would add unnecessary instance-template, autoscaling, and managed-instance-group complexity without solving the interruption problem.

**Reference links**

- [docs.cloud.google.com/compute/docs/instances/preemptible](https://docs.cloud.google.com/compute/docs/instances/preemptible)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/preemptible-vms](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/preemptible-vms)
- [docs.cloud.google.com/compute/docs/instances/suspend-stop-reset-instances-overview](https://docs.cloud.google.com/compute/docs/instances/suspend-stop-reset-instances-overview)

**Related notes:** [Spot VMs](../03-compute-containers/products/spot-vms.md)

</details>

[Back to index](#index)

---

### Q9

> Northwind Health is consolidating two independently managed business units. One unit operates a production Google Cloud project under a separate organization resource. Northwind Health must transfer the existing project into its primary organization resource and charge all future usage to its central Cloud Billing account while minimizing migration work. What should Northwind Health do?  

- **A.** Use the projects.move method to migrate the existing project to the primary organization resource, and then link the project to Northwind Health’s Cloud Billing account.
- **B.** Obtain the Organization Administrator IAM role in both organization resources, and drag the project from one organization resource to the other in Resource Manager.
- **C.** Add the project’s resources to a collection in Google Cloud Private Marketplace, share the collection with the primary organization, and deploy the resources again.
- **D.** Describe all project resources in Terraform, deploy them into a newly created project in the primary organization, and delete the original project.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the Resource Manager projects.move method moves an existing project to a different parent in the Google Cloud resource hierarchy. Moving the project is a metadata operation, so the project ID and project number remain unchanged, and the resources inside the project generally do not need to be recreated. Before performing the migration, the required IAM permissions and organization policies must be configured in the source and destination organizations. In particular, the caller needs the resourcemanager.projects.move permission on the project, its current parent, and its proposed destination parent. Moving a project does not automatically change the Cloud Billing account linked to it. Without a separate billing update, charges continue to be applied to the original Cloud Billing account. Therefore, after moving the project, Northwind Health must link it to its own Cloud Billing account. This approach preserves the existing project and workloads while avoiding the effort and risk of rebuilding the environment.

**B is incorrect** because projects cannot be transferred between separate organization resources by dragging them from one organization to another in Resource Manager. The Google Cloud console supports moving projects between folders within a resource hierarchy, but an inter-organization project migration must follow the supported migration process by using the Google Cloud CLI or Resource Manager API and satisfying the required organization-policy and IAM prerequisites. The Organization Administrator role alone also does not necessarily provide every required project-migration permission on the project and both parent resources. Additionally, this option does not change the project’s Cloud Billing account, so it would not ensure that future charges are billed to Northwind Health.

**C is incorrect** because Google Cloud Private Marketplace is a governance and procurement feature that lets an organization curate and share approved Google Cloud Marketplace products. It is not a project-migration or resource-export service, and it cannot package arbitrary resources from an existing production project for transfer to another organization. Creating a Private Marketplace collection would neither move the project nor preserve its project identity, IAM configuration, networking, service data, and running workloads. It would also not automatically associate the project with Northwind Health’s Cloud Billing account.

**D is incorrect** because recreating the environment with Terraform would require identifying, importing, and describing every supported resource and dependency in infrastructure-as-code configuration. Some existing resource state, application data, IAM bindings, service-managed configuration, and resources that Terraform does not manage could require separate migration procedures. A new project would also have a different project ID and project number, potentially requiring changes to service accounts, permissions, DNS records, integrations, quotas, and application configuration. Deleting the original project would increase the risk of downtime or data loss. Although Terraform can help standardize infrastructure, rebuilding the environment is significantly more work than directly moving the existing project and updating its billing association.

**Reference links**

- [docs.cloud.google.com/resource-manager/reference/rest/v3/projects/move](https://docs.cloud.google.com/resource-manager/reference/rest/v3/projects/move)
- [docs.cloud.google.com/resource-manager/docs/project-migration](https://docs.cloud.google.com/resource-manager/docs/project-migration)
- [docs.cloud.google.com/billing/docs/how-to/modify-project](https://docs.cloud.google.com/billing/docs/how-to/modify-project)

</details>

[Back to index](#index)

---

### Q10

> Northstar Analytics hosts an internal reporting service on a Linux Compute Engine VM. A temporary support engineer must troubleshoot the VM from a partner office that is connected to Northstar Analytics through Cloud VPN. The engineer does not have a Google account. What should Northstar Analytics do?  

- **A.** Ask the support engineer to run gcloud compute ssh and connect to the VM through Identity-Aware Proxy.
- **B.** Ask the support engineer to run gcloud compute ssh and connect to the VM through its external IP address.
- **C.** -Ask the support engineer to create an SSH key pair and send the public key to Northstar Analytics.  
  -Add the public key to the VM, and have the engineer connect by using the corresponding private key.
- **D.** -Ask the support engineer to create an SSH key pair and send the private key to Northstar Analytics.  
  -Add the private key to the VM, and have the engineer connect by using the corresponding public key.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Identity-Aware Proxy authorizes TCP forwarding through Google Cloud Identity and Access Management. A user connecting through IAP must authenticate with an appropriate Google identity and must be granted permissions such as the IAP-secured Tunnel User role. Because the support engineer has no Google account, the engineer cannot complete the required Google Cloud authentication and authorization process. IAP is useful for identity-controlled SSH access to instances without external IP addresses, but it does not replace the need for an authenticated identity.

**B is incorrect** because gcloud compute ssh normally interacts with Google Cloud APIs to identify the VM, determine its IP address, manage SSH keys, and verify the caller’s permissions. This requires the engineer to authenticate the Google Cloud CLI with a Google identity that has the necessary Compute Engine permissions. The engineer has no Google account, so this is not an appropriate access method. Additionally, using an external IP address would unnecessarily expose an SSH access path when the engineer already has private network connectivity through Cloud VPN.

**C is correct** because SSH public-key authentication does not require the external engineer to have a Google account. The engineer generates a key pair and retains the private key securely on their workstation. Northstar Analytics adds only the public key to the VM’s instance metadata, project metadata, or the appropriate user’s authorized_keys file, depending on the VM’s SSH configuration. When the engineer connects, the VM verifies that the engineer possesses the private key corresponding to the installed public key. The private key is never shared. Because the partner office is connected through Cloud VPN, the engineer can use the VM’s internal IP address, provided that routing and firewall rules permit TCP port 22 from the relevant VPN network. After the engagement ends, Northstar Analytics should remove the engineer’s public key to revoke access.

**D is incorrect** because SSH key responsibilities are reversed in this option. A private key must remain confidential and under the exclusive control of the person using it to authenticate. It must never be sent to an administrator or installed on the destination VM. The VM stores the public key, while the connecting client proves possession of the matching private key. A public key cannot be used by the client as the authentication secret. Sharing the private key would also create a serious security risk because anyone obtaining it could impersonate the engineer.

**Reference links**

- [docs.cloud.google.com/compute/docs/connect/add-ssh-keys](https://docs.cloud.google.com/compute/docs/connect/add-ssh-keys)
- [docs.cloud.google.com/compute/docs/connect/standard-ssh](https://docs.cloud.google.com/compute/docs/connect/standard-ssh)
- [docs.cloud.google.com/iap/docs/using-tcp-forwarding](https://docs.cloud.google.com/iap/docs/using-tcp-forwarding)

**Related notes:** [Identity-Aware Proxy (IAP)](../02-identity-security/products/identity-aware-proxy.md)

</details>

[Back to index](#index)

---

### Q11

> ParcelPulse operates a delivery-tracking platform on Google Cloud. After detecting an unauthorized configuration change, the security team wants to detect unexpected VPC firewall rule modifications and Compute Engine VM creation. The company wants a managed solution that is simple to operate. What should the security team do?  

- **A.** -Create a log sink that routes Cloud Audit Logs for VPC firewall rules and Compute Engine VMs to Cloud Storage.  
  -Periodically query the stored logs from BigQuery to identify changes.
- **B.** -Create Cloud Logging filters and log-based metrics for VPC firewall rule changes and Compute Engine VM creation.  
  -Configure monitoring and alerting policies for the metrics.
- **C.** -Deploy Kibana on a Compute Engine VM.  
  -Route filtered Cloud Audit Logs to Pub/Sub, and configure Pub/Sub to push the messages to Kibana for real-time analysis.
- **D.** Enable VPC firewall rules logging and configure alerts for firewall insert, update, and delete operations.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because routing Cloud Audit Logs to Cloud Storage and periodically analyzing them with BigQuery introduces unnecessary components and operational steps. Cloud Storage is suitable for long-term archival and compliance retention, but periodic analysis does not provide timely detection of security-sensitive changes. Additional configuration would also be required to load the exported data into BigQuery or query it through supported external-table mechanisms. A sink could instead route logs directly to BigQuery, but that would still require queries, scheduling, and alerting logic. This approach is therefore more complex and less responsive than using Cloud Logging and Cloud Monitoring directly.

**B is correct** because Cloud Audit Logs record administrative operations such as creating Compute Engine instances and inserting, updating, or deleting VPC firewall rules. Cloud Logging filters can identify the relevant audit log entries by resource type, service name, or API method name. Log-based counter metrics can then count matching events, and Cloud Monitoring alerting policies can notify the security team whenever the metrics cross an appropriate threshold. For particularly sensitive actions, the threshold can be configured so that a single matching event triggers an alert. This solution uses fully managed Google Cloud services, requires no additional infrastructure, supports near-real-time monitoring, and satisfies the company’s preference for simplicity.

**C is incorrect** because it requires the company to deploy, secure, patch, scale, and maintain a Compute Engine VM and a separate logging and visualization stack. Kibana is primarily a visualization interface and normally relies on Elasticsearch or another compatible data store, so Pub/Sub messages cannot simply be pushed to Kibana and analyzed without an ingestion and indexing pipeline. The company would need to develop or operate a subscriber that processes messages and writes them to a supported backend. Although Pub/Sub can be used to stream logs to external security platforms, this proposed design is incomplete and substantially more complicated than managed log-based metrics and alerts.

**D is incorrect** because VPC firewall rules logging records network connections that are allowed or denied by firewall rules. It is intended to help analyze firewall rule usage and the traffic affected by those rules. It does not record administrative actions that create, modify, or delete firewall rules. Those configuration changes are recorded in Cloud Audit Logs. VPC firewall rules logging also does not detect Compute Engine VM creation, so this option fails to address both monitoring requirements. Alerts for insert, update, and delete operations should be based on audit log entries rather than firewall traffic logs.

**Reference links**

- [docs.cloud.google.com/logging/docs/audit](https://docs.cloud.google.com/logging/docs/audit)
- [docs.cloud.google.com/logging/docs/logs-based-metrics/charts-and-alerts](https://docs.cloud.google.com/logging/docs/logs-based-metrics/charts-and-alerts)
- [docs.cloud.google.com/firewall/docs/vpc-firewall-rules-logging-overview](https://docs.cloud.google.com/firewall/docs/vpc-firewall-rules-logging-overview)

**Related notes:** [Cloud Logging](../07-operations-cost/products/cloud-logging.md)

</details>

[Back to index](#index)

---

### Q12

> HarborTrack runs inventory applications on Compute Engine and in its private data center. Its Google Cloud Virtual Private Cloud network is connected to the corporate WAN through Cloud VPN. HarborTrack must deploy a new Compute Engine VM that remains reachable from the private WAN but cannot be reached directly from the public internet. What should the cloud administrator do?  

- **A.** Create the VM with an internal IP address and do not assign it an external IP address.
- **B.** Create the VM in a subnet where Private Google Access is enabled.
- **C.** Create a deny-all egress VPC firewall rule and apply it to the VM.
- **D.** Add a 0.0.0.0/0 custom route that uses the Cloud VPN tunnel as its next hop.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a Compute Engine VM requires an external IPv4 or external IPv6 address to be directly addressable from the public internet. Creating the VM with only an internal IP address prevents internet hosts from routing traffic directly to the VM’s network interface. The VM can still communicate privately with other resources in the VPC network and with HarborTrack’s on-premises systems through the Cloud VPN connection, assuming the necessary routes and ingress firewall rules exist. This satisfies both requirements: the VM remains available through private connectivity while having no direct public internet exposure. An administrator should also ensure that the VM is not exposed indirectly through a public load balancer, proxy, or another internet-facing service, but among the provided choices, omitting the external IP address is the appropriate action.

**B is incorrect** because Private Google Access controls whether VMs that have only internal IP addresses can reach supported Google APIs and services. It does not prevent public internet traffic from reaching a VM, and it does not replace the need to omit an external IP address. Private Google Access is normally enabled for a subnet rather than directly on an individual VM. A VM created in such a subnet could still be publicly accessible if an external IP address were assigned to its network interface and an applicable ingress firewall rule allowed the traffic. Therefore, Private Google Access addresses private access to Google services, not protection from direct public internet exposure.

**C is incorrect** because an egress firewall rule applies to traffic leaving the VM, not traffic entering it. A deny-all egress rule would prevent the VM from initiating connections to other destinations, potentially including systems in the VPC network and the on-premises environment. It would not prevent unsolicited public internet traffic from reaching the VM if the VM had an external IP address and an ingress firewall rule allowed that traffic. An ingress rule could restrict inbound connections, but relying only on firewall rules would still leave the VM with a public address. Removing the external IP address is the more direct way to ensure that the VM is not directly routable from the public internet.

**D is incorrect** because a custom route with 0.0.0.0/0 as its destination controls where IPv4 traffic originating from resources in the VPC network is forwarded. Sending the default route through the Cloud VPN tunnel could direct outbound traffic toward HarborTrack’s on-premises network, depending on route priorities and the VPN configuration. However, it does not remove an external IP address from the VM or prevent inbound public internet traffic from reaching that external address. It could also create unintended routing problems if the on-premises network is not configured to process or forward the traffic. Routes determine forwarding paths, whereas preventing direct public reachability is accomplished by creating the VM without an external IP address.

**Reference links**

- [docs.cloud.google.com/compute/docs/ip-addresses](https://docs.cloud.google.com/compute/docs/ip-addresses)
- [docs.cloud.google.com/vpc/docs/private-google-access](https://docs.cloud.google.com/vpc/docs/private-google-access)
- [docs.cloud.google.com/firewall/docs/firewalls](https://docs.cloud.google.com/firewall/docs/firewalls)

**Related notes:** [Compute Engine](../03-compute-containers/products/compute-engine.md) · [VPC, Subnets, and IPs](../06-networking/products/vpc-subnets-and-ips.md)

</details>

[Back to index](#index)

---

### Q13

> BlueOrbit Logistics developed a shipment-tracking application on a developer workstation. The application uses Application Default Credentials to access Google Cloud services and operates correctly in the local environment. The company is moving the application to a Compute Engine VM and wants authentication to continue working with minimal application changes while following Google-recommended security practices. What should you do?  

- **A.** Grant the required IAM roles to the service account attached to the Compute Engine VM.
- **B.** Create a service account with the required IAM roles and modify the application to authenticate explicitly as that service account.
- **C.** Download a key for a service account with the required IAM roles, store the key in an application configuration file, and deploy the file with the application.
- **D.** Export credentials for a developer’s user account, store them in an application configuration file, and deploy the file with the application.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Application Default Credentials automatically detects the execution environment and obtains credentials from the service account attached to a Compute Engine VM by using the metadata server. Therefore, the application can continue using its existing Application Default Credentials code without embedding credentials or changing its authentication logic. The administrator only needs to ensure that the VM has an appropriate service account attached and that this service account has the minimum IAM roles required to access the necessary Google Cloud resources. Google recommends using a dedicated user-managed service account for production workloads, granting it least-privilege IAM roles, attaching it to the VM, and using the cloud-platform access scope while controlling effective access through IAM. This approach provides automatically managed, short-lived credentials and avoids distributing service account keys.

**B is incorrect** because explicitly configuring the application to use a newly created service account would introduce unnecessary application-level configuration when the application already uses Application Default Credentials. A dedicated user-managed service account can be a recommended VM identity, but it should be attached to the Compute Engine VM so that Application Default Credentials can retrieve its short-lived credentials automatically. The option instead suggests modifying the application to authenticate explicitly as the new account, which is not the minimal-change approach. Granting the required roles to the service account attached to the VM allows the existing authentication code to continue working.

**C is incorrect** because downloading service account credentials and deploying them in a configuration file creates a long-lived private key that must be securely stored, distributed, audited, and rotated. Anyone who obtains the file could authenticate as the service account and use its permissions. Google recommends avoiding service account keys whenever the workload runs on a Google Cloud resource that supports an attached service account. Compute Engine can provide short-lived credentials through its metadata server, so no credential file is required. Embedding or deploying a key also increases operational work and is less secure than using the VM’s attached identity.

**D is incorrect** because a user account represents a human identity and should not be used as the permanent identity of a production workload. User credentials can expire, be revoked, require reauthentication, or become unavailable when the employee changes roles or leaves the organization. Deploying a developer’s credentials also makes accountability and least-privilege access more difficult and exposes sensitive personal credentials on the VM. Production applications running on Compute Engine should authenticate through an attached service account rather than through a developer’s user account or a credential file.

**Reference links**

- [cloud.google.com/docs/authentication/application-default-credentials](https://cloud.google.com/docs/authentication/application-default-credentials)
- [cloud.google.com/compute/docs/access/service-accounts](https://cloud.google.com/compute/docs/access/service-accounts)
- [cloud.google.com/iam/docs/best-practices-for-managing-service-account-keys](https://cloud.google.com/iam/docs/best-practices-for-managing-service-account-keys)

**Related notes:** [Application Default Credentials (ADC)](../02-identity-security/products/application-default-credentials.md)

</details>

[Back to index](#index)

---

### Q14

> BrightCart runs its customer portal on Compute Engine VMs in the storefront-services project. The VMs use a service account and must read customer analytics tables stored in BigQuery datasets in the loyalty-warehouse project. You want to follow Google-recommended least-privilege practices when configuring the service account. What should you do?  

- **A.** Grant the Owner role to the storefront-services project and grant appropriate roles in the loyalty-warehouse project.
- **B.** Grant the Owner role in both the loyalty-warehouse and storefront-services projects.
- **C.** Grant the Owner role in the loyalty-warehouse project and grant roles/bigquery.dataViewer in the storefront-services project.
- **D.** Grant roles/bigquery.dataViewer in the loyalty-warehouse project and grant only the appropriate required roles in the storefront-services project.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because IAM roles must be granted to a principal, such as the service account used by the Compute Engine VMs, rather than to another project. In addition, granting the basic Owner role would give the service account extensive administrative permissions, including the ability to manage many project resources and IAM policies. The service account only needs permission to read specific BigQuery data in the loyalty-warehouse project and the permissions required to perform its application tasks in the storefront-services project. Granting Owner violates the principle of least privilege.

**B is incorrect** because granting the Owner role to the service account in both projects provides far more access than the application requires. The service account could potentially modify or delete resources, change project configurations, and manage access policies. Cross-project access does not require ownership of either project. Google recommends using predefined roles that contain only the permissions necessary for the workload. The required BigQuery data permissions should be granted in the project or dataset containing the data, while any permissions needed to run the workload should be granted separately in the application project.

**C is incorrect** because the roles are assigned at the wrong locations and the Owner role remains unnecessarily broad. The BigQuery datasets are located in the loyalty-warehouse project, so roles/bigquery.dataViewer must be granted to the VM service account on the relevant dataset or within that resource project. Granting roles/bigquery.dataViewer in the storefront-services project does not provide read access to datasets located in loyalty-warehouse. Giving the service account Owner access to loyalty-warehouse would technically include broad access, but it would expose the entire project to unnecessary risk and would not follow least-privilege recommendations.

**D is correct** because the service account should receive permissions where the protected resources exist. Granting roles/bigquery.dataViewer to the VM service account on the appropriate BigQuery datasets in the loyalty-warehouse project allows it to read tables, views, and other supported dataset resources without giving it administrative control over the project. The service account should separately receive only the roles required for its workload in the storefront-services project. For example, if the service account submits BigQuery query jobs in that project, it might also require roles/bigquery.jobUser there. This separates data access from job execution permissions, supports cross-project access, and follows the principle of least privilege. Where possible, roles/bigquery.dataViewer should be granted at the dataset level instead of the entire project to reduce the scope of access further.

**Reference links**

- [docs.cloud.google.com/bigquery/docs/access-control](https://docs.cloud.google.com/bigquery/docs/access-control)
- [docs.cloud.google.com/bigquery/docs/control-access-to-resources-iam](https://docs.cloud.google.com/bigquery/docs/control-access-to-resources-iam)
- [docs.cloud.google.com/iam/docs/using-iam-securely](https://docs.cloud.google.com/iam/docs/using-iam-securely)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q15

> DataForge Labs runs an Apache Hadoop analytics workload on a Dataproc cluster in one VPC network. The cluster uses a single subnet with the primary IPv4 range 10.40.8.128/25, and all available internal IP addresses have been allocated. The adjacent address space is unused. The company needs to add Compute Engine VMs that can communicate directly with the cluster while minimizing configuration steps. What should the network administrator do?  

- **A.** Expand the existing subnet’s primary IPv4 range to 10.40.8.0/24.
- **B.** Add a new secondary IPv4 range to the subnet and configure the new VMs to use addresses from that range.
- **C.** Create another VPC network for the new VMs and establish VPC Network Peering with the Dataproc cluster’s VPC network.
- **D.** Create another VPC network containing a 10.90.0.0/16 subnet, establish VPC Network Peering with the Dataproc cluster’s VPC network, and configure custom route exchange.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Google Cloud allows the primary IPv4 range of an existing subnet to be expanded, provided that the new range contains the original range and does not overlap with another allocated range. The existing 10.40.8.128/25 range is contained within 10.40.8.0/24, so expanding it to /24 makes additional primary internal IP addresses available. The existing Dataproc cluster and the new VMs remain in the same subnet and VPC network, allowing them to communicate through automatically created subnet routes, subject to applicable firewall rules. This requires fewer configuration steps than creating and peering another VPC network. A subnet’s primary range can be expanded but cannot later be reduced, so the expanded range should be planned carefully.

**B is incorrect** because a subnet’s secondary IPv4 ranges are used for alias IP ranges rather than the primary internal IP addresses assigned to VM network interfaces. A newly created Compute Engine VM still requires a primary internal IP address from the subnet’s primary IPv4 range. Because the primary range has no available addresses, merely adding a secondary range does not provide the primary IP addresses required to create the new VMs. Secondary ranges are commonly used for purposes such as assigning alias addresses to applications or allocating addresses to Google Kubernetes Engine Pods.

**C is incorrect** because creating a separate VPC network and configuring VPC Network Peering could provide private connectivity, but it introduces unnecessary resources and administrative steps. The administrator would need to create a new network and subnet, configure peering from both networks, verify route exchange, and create suitable firewall rules. Because the existing subnet can be expanded, keeping the VMs in the same VPC network is simpler. VPC Network Peering is more appropriate when resources must remain in independently administered or intentionally separated VPC networks.

**D is incorrect** because both the additional VPC network and custom route exchange are unnecessary. VPC Network Peering automatically exchanges eligible subnet routes, so custom route exchange is not required merely to enable communication between VMs using the networks’ subnet ranges. Custom route import and export are relevant when static or dynamic custom routes must be shared across a peering connection. This option creates the most operational complexity and does not satisfy the requirement to use the minimum number of steps.

**Reference links**

- [docs.cloud.google.com/vpc/docs/subnets](https://docs.cloud.google.com/vpc/docs/subnets)
- [docs.cloud.google.com/vpc/docs/alias-ip](https://docs.cloud.google.com/vpc/docs/alias-ip)
- [docs.cloud.google.com/vpc/docs/vpc-peering](https://docs.cloud.google.com/vpc/docs/vpc-peering)

**Related notes:** [VPC, Subnets, and IPs](../06-networking/products/vpc-subnets-and-ips.md)

</details>

[Back to index](#index)

---

### Q16

> TripSphere is developing a global travel-booking service that will store reservation and payment records submitted by its mobile app and website. The service expects very high transaction volumes after launch. Business analysts must be able to query the operational data using SQL. The database must remain highly available and scale across regions. What should TripSphere do?  

- **A.** Create a multi-region Spanner instance and design the schema to distribute the workload efficiently.
- **B.** Create a multi-region Firestore database and use aggregation queries for reporting.
- **C.** Create a multi-region Cloud SQL for PostgreSQL database and add optimized indexes.
- **D.** Create a multi-region BigQuery dataset and optimize its tables.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Spanner is a fully managed, distributed relational database designed for high-volume transactional workloads that require horizontal scalability, strong consistency, high availability, and SQL support. A multi-region Spanner configuration synchronously replicates data across multiple regions and can continue serving the application despite certain zonal or regional failures. Spanner supports ACID transactions and GoogleSQL or the PostgreSQL interface, making it appropriate for reservation and payment records that require reliable transactional behavior. An optimized schema is important because monotonically increasing primary keys or poorly distributed keys can create hotspots. Selecting keys that distribute writes across splits enables Spanner to scale as global traffic increases.

**B is incorrect** because Firestore is primarily a document-oriented NoSQL database rather than a relational SQL database. It offers multi-region configurations, transactions, automatic scaling, and aggregation operations such as count, sum, and average, but these aggregation queries do not provide the flexible SQL analytics requested by the business team. Firestore queries depend heavily on indexes and do not support the same joins, relational modeling, and broad SQL querying capabilities as Spanner. Firestore could be suitable for globally distributed mobile and web application data when a document model is appropriate, but it does not satisfy the stated requirement for SQL-based analysis of relational transaction data as effectively as Spanner.

**C is incorrect** because Cloud SQL for PostgreSQL is a managed relational database that supports SQL and transactions, but its built-in high-availability configuration is regional rather than multi-region. A highly available Cloud SQL instance maintains a primary and standby in different zones of the same region. Cross-region read replicas can support disaster recovery and read scaling, but they do not convert the database into a synchronously replicated, horizontally scalable, multi-region transactional database. Cloud SQL generally scales vertically for write workloads and remains constrained by the capacity of its primary instance. Optimized indexes can improve query performance, but they do not provide the global horizontal scalability required for a very large volume of worldwide transactions.

**D is incorrect** because BigQuery is a serverless analytical data platform and data warehouse optimized for scanning and analyzing large datasets using SQL. It is excellent for business intelligence, reporting, and historical transaction analysis, but it is not designed to serve as the primary operational database for an ecommerce or booking application. Application transactions commonly require low-latency point reads, frequent row-level changes, and multi-record ACID transactions. A multi-region BigQuery dataset controls where analytical data is stored and processed, but it does not make BigQuery equivalent to a globally distributed online transaction processing database. A suitable architecture could store operational records in Spanner and later export or replicate them to BigQuery for extensive analytics.

**Reference links**

- [docs.cloud.google.com/spanner/docs](https://docs.cloud.google.com/spanner/docs)
- [docs.cloud.google.com/sql/docs/postgres/high-availability](https://docs.cloud.google.com/sql/docs/postgres/high-availability)
- [docs.cloud.google.com/bigquery/docs/introduction](https://docs.cloud.google.com/bigquery/docs/introduction)

**Related notes:** [Spanner](../05-storage-databases-data/products/spanner.md)

</details>

[Back to index](#index)

---

### Q17

> Northstar Analytics uses Workforce Identity Federation to give consultants from partner company BrightPath access to Google Cloud. A BrightPath consultant completes the engagement, and Northstar Analytics wants the consultant’s access revoked through BrightPath’s normal identity lifecycle without checking individual Google Cloud projects for a separate account. What should Northstar Analytics do?  

- **A.** Disable the consultant’s identity in BrightPath’s external identity provider and verify that the identity or group-membership change is reflected in subsequent federated authentication.
- **B.** Delete all service accounts from every project the consultant previously accessed.
- **C.** Rotate every Cloud KMS key used by Northstar Analytics.
- **D.** Disable the Compute Engine API in the project most recently accessed by the consultant.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Workforce Identity Federation allows external users, including partners and contractors, to authenticate to Google Cloud by using identities managed by an external identity provider. The external identity provider remains the authoritative system for the consultant’s identity and lifecycle status. Disabling or deleting the consultant in that provider prevents the consultant from obtaining new federated Google Cloud credentials after the change has propagated. When authorization depends on external group membership or mapped identity attributes, those assignments must also be removed or updated so that future tokens no longer contain the attributes required by the applicable IAM allow policies. This approach centralizes offboarding in the supplier’s existing identity-management process and avoids creating or locating a separate Google-managed user account in every project. Previously issued short-lived credentials or active sessions can remain usable until they expire, so organizations should configure suitable workforce-pool session durations and verify that the identity-provider change has taken effect.

**B is incorrect** because service accounts are identities intended primarily for applications, workloads, automation, and other non-human processes. They are not local copies of every workforce identity that accesses a project through Workforce Identity Federation. Deleting all service accounts would therefore not be the proper way to revoke the consultant’s federated identity and could cause major outages by removing credentials used by applications, virtual machines, deployment processes, and scheduled jobs. A service account would require separate action only if the consultant possessed its key or had permission to impersonate it, but indiscriminately deleting every service account is unnecessary and disruptive.

**C is incorrect** because Cloud KMS key rotation manages the cryptographic material used to encrypt, decrypt, sign, or verify data. It does not disable a workforce identity, remove IAM role bindings, invalidate the consultant’s external identity-provider account, or prevent the consultant from completing a new federated sign-in. Rotating every key would also create significant operational work and might affect applications that depend on particular key versions. Key rotation could be relevant after suspected key compromise, but an ordinary contractor offboarding event should be handled through the external identity lifecycle and federation configuration.

**D is incorrect** because disabling the Compute Engine API affects the availability of Compute Engine functionality in one project rather than revoking the consultant’s identity. It would not prevent access to other projects or to services such as Cloud Storage, BigQuery, or Secret Manager. It could also interrupt legitimate workloads and administrators that rely on Compute Engine. Workforce Identity Federation access should be terminated at the identity source, or through the relevant IAM policies when necessary, instead of disabling an unrelated service API.

**Reference links**

- [cloud.google.com/iam/docs/workforce-identity-federation](https://cloud.google.com/iam/docs/workforce-identity-federation)
- [cloud.google.com/iam/docs/configuring-workforce-identity-federation](https://cloud.google.com/iam/docs/configuring-workforce-identity-federation)
- [cloud.google.com/iam/docs/best-practices-workforce-identity-federation](https://cloud.google.com/iam/docs/best-practices-workforce-identity-federation)

</details>

[Back to index](#index)

---

### Q18

> HarborCart, an online retail platform, has acquired a delivery application named SwiftParcel. Each company currently has a separate Google Cloud organization. HarborCart uses an organization-level custom IAM role for its platform engineering team, and you need an equivalent role with the same permissions in the SwiftParcel organization. What should you do?  

- **A.** In the HarborCart organization’s Google Cloud console, select the custom role, choose Create custom role from selection, and specify the SwiftParcel organization as the destination.
- **B.** In the SwiftParcel organization’s Google Cloud console, choose Create custom role from selection and use the SwiftParcel organization as the source of the role.
- **C.** Run the gcloud iam roles copy command, specifying the HarborCart custom role as the source and the SwiftParcel Organization ID with the --dest-organization flag.
- **D.** Run the gcloud iam roles copy command separately for every SwiftParcel project, specifying each project ID with the --dest-project flag.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Create custom role from selection in the Google Cloud console creates the new custom role in the organization or project currently selected in the console. It does not provide a cross-organization destination mechanism that copies a custom role directly from the selected HarborCart organization into the SwiftParcel organization. Custom roles are scoped to the organization or project in which they are created, so creating the role while HarborCart is selected would not make that role available within SwiftParcel’s resource hierarchy.

**B is incorrect** because the source role containing the required permissions exists in the HarborCart organization, not in the SwiftParcel organization. Selecting SwiftParcel as both the working organization and the source would not retrieve HarborCart’s custom role definition. Although an administrator could manually create a new role in SwiftParcel and reproduce every permission, that approach is more error-prone and is not the direct role-copying method provided by the Google Cloud CLI.

**C is correct** because gcloud iam roles copy is specifically designed to create a custom IAM role from an existing role. For an organization-level custom role, the command can identify the original role with --source and --source-organization and create the equivalent role in another organization by using --destination and --dest-organization. Creating the copied role at the SwiftParcel organization level makes it available for IAM bindings on that organization and on eligible folders, projects, and resources beneath it. The role-copy operation copies the role definition and its included permissions; the SRE or platform engineering group must then be granted the copied role at the appropriate organization, folder, or project scope because IAM policy bindings are not automatically copied.

**D is incorrect** because using --dest-project creates a project-level custom role in an individual project. Repeating the command for every project would create separate role definitions that must be maintained independently, increasing administrative effort and the risk of permission differences between projects. A project-level custom role also cannot contain certain permissions that are valid only at the organization or folder level. Because the requirement applies across the acquired company’s organization, creating one organization-level custom role with --dest-organization is the more scalable and consistent solution.

**Reference links**

- [cloud.google.com/sdk/gcloud/reference/iam/roles/copy](https://cloud.google.com/sdk/gcloud/reference/iam/roles/copy)
- [cloud.google.com/iam/docs/creating-custom-roles](https://cloud.google.com/iam/docs/creating-custom-roles)
- [cloud.google.com/iam/docs/roles-overview](https://cloud.google.com/iam/docs/roles-overview)

</details>

[Back to index](#index)

---

### Q19

> VoxLoom, a customer-research platform, stores newly uploaded interview recordings in a Cloud Storage bucket. Each recording must be sent to the Speech-to-Text API immediately after the upload is completed. The solution must be fully managed, serverless, event-driven, and use authenticated Google Cloud service identities. What should you do?  

- **A.** Deploy an App Engine standard environment application that receives Cloud Storage events and submits each uploaded recording’s URI to the Speech-to-Text API.
- **B.** Schedule a Google Kubernetes Engine job to inspect the bucket periodically and submit every unprocessed recording to the Speech-to-Text API.
- **C.** Configure a cron job on a Compute Engine virtual machine to inspect the bucket periodically and submit every unprocessed recording to the Speech-to-Text API.
- **D.** Deploy a Cloud Run function with a Cloud Storage object-finalization trigger that submits each uploaded recording’s URI to the Speech-to-Text API.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because App Engine standard environment is a fully managed application platform, but an App Engine application is not directly invoked by Cloud Storage object-finalization events in the simple event-driven manner required here. Additional components, such as Eventarc, Pub/Sub, or an HTTP endpoint, would be needed to route events to the application. This makes the design more complicated than necessary. App Engine is better suited to hosting web applications and APIs that receive requests rather than implementing a small function that executes automatically for every new object uploaded to a bucket.

**B is incorrect** because a Google Kubernetes Engine job requires a Kubernetes cluster or an Autopilot environment and introduces unnecessary operational complexity for a simple event-processing workload. The job would also need to poll the bucket repeatedly, track which objects have already been processed, handle duplicate processing, and remain scheduled even when no files are arriving. Although Google Kubernetes Engine can use service accounts and Workload Identity Federation for GKE to authenticate securely, it is not the simplest fully managed serverless solution for responding immediately to individual Cloud Storage events.

**C is incorrect** because Compute Engine requires management of a virtual machine, including its operating system, security updates, availability, monitoring, and capacity. A cron job would poll the bucket rather than react immediately to new-object events. The script would also need custom state-management logic to identify unprocessed files and prevent duplicate transcription requests. A VM can authenticate by using an attached service account, but this design is neither serverless nor aligned with the recommended event-driven architecture for this requirement.

**D is correct** because a Cloud Run function is a fully managed, serverless compute resource that can execute in response to Cloud Storage events. An object-finalization trigger invokes the function when a new object is successfully created in the bucket. The event provides information such as the bucket name and object name, allowing the function to construct the gs://bucket-name/object-name URI and submit it to the Speech-to-Text API. The function can use its runtime service account and Application Default Credentials to authenticate to Cloud Storage and the Speech-to-Text API without storing service account keys. It scales automatically when multiple recordings arrive, incurs no compute charge while inactive beyond applicable platform billing rules, and eliminates bucket polling and infrastructure administration. Because event delivery can occur more than once, the implementation should also be idempotent, such as by recording the object generation number or transcription request state.

**Reference links**

- [cloud.google.com/run/docs/triggering/storage-triggers](https://cloud.google.com/run/docs/triggering/storage-triggers)
- [cloud.google.com/run/docs/tutorials/trigger-functions-storage](https://cloud.google.com/run/docs/tutorials/trigger-functions-storage)
- [cloud.google.com/speech-to-text/docs/batch-recognize](https://cloud.google.com/speech-to-text/docs/batch-recognize)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md)

</details>

[Back to index](#index)

---

### Q20

> NimbusCart operates an online marketplace using Google Cloud resources across several projects. Each project is connected to a separate Cloud Billing account. The finance team needs one automatically updated dashboard that combines actual cost data from every billing account so that it can analyze spending trends and forecast future expenses. What should the cloud administrator do?  

- **A.** Enable Cloud Billing data export to BigQuery for each billing account, consolidate the exported data with a BigQuery view or query, and visualize it in Data Studio.
- **B.** Download a CSV file from the Cost table for each billing account and upload the files to Data Studio.
- **C.** Recreate every deployed resource in the Google Cloud Pricing Calculator and use the calculated totals as the dashboard.
- **D.** Open the Reports page in the Cloud Billing console and select all projects from the available project filter.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Cloud Billing data export sends detailed usage and cost information from a Cloud Billing account to BigQuery automatically throughout the day. Because NimbusCart uses multiple independent billing accounts, the administrator should enable the export separately for each account. The exported tables can then be queried together, such as by using a UNION ALL query or a consolidated BigQuery view, provided the required permissions are configured. Data Studio can connect directly to the resulting BigQuery data and present it as one dashboard containing costs from all billing accounts. This approach is automated, scalable, customizable, and suitable for trend analysis and forecasting. It also allows new cost records to appear in the dashboard as the billing exports are updated, without requiring repeated manual file downloads. The exports contain useful dimensions such as billing account ID, project, service, SKU, location, usage, cost, credits, adjustments, and currency, which makes them appropriate for detailed financial analysis.

**B is incorrect** because the Cost table is designed primarily to examine invoice or statement details for one selected Cloud Billing account. A CSV downloaded from this page is a static snapshot. The administrator would need to select each billing account, download its data, combine the files, and repeatedly upload updated files whenever new charges were reported. This process is manual, does not automatically incorporate newly available cost data, and is prone to missing records or producing inconsistent reporting periods. Although Data Studio can visualize uploaded data, manually exported CSV files do not provide the continuously updated consolidated reporting solution required by NimbusCart.

**C is incorrect** because the Google Cloud Pricing Calculator produces projected costs based on manually entered resource configurations and expected usage. It does not import actual resource usage or incurred charges from Cloud Billing accounts. Its estimates might also differ from billed costs because actual charges can be affected by changing usage levels, committed use discounts, sustained use discounts, promotional credits, negotiated pricing, taxes, adjustments, and other billing factors. Manually entering every existing and future resource would also be difficult to maintain. The Pricing Calculator is useful for planning a proposed architecture or estimating the cost of a future workload, but it is not an automated reporting system for consolidating actual costs already incurred across multiple billing accounts.

**D is incorrect** because the Cloud Billing Reports page displays costs and trends for the Cloud Billing account currently being viewed. Its project filter can combine multiple projects only when those projects are associated with that selected billing account and the user has the necessary permissions. It does not provide a single standard report that aggregates unrelated projects from several independent Cloud Billing accounts. The administrator would need to switch between billing accounts and view separate reports. Reports can provide useful charts and forecasts within an individual billing account, but they do not satisfy the requirement for one consolidated visualization covering all of NimbusCart’s billing accounts. Exporting the data to BigQuery provides the flexibility required to combine those separate sources.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery)
- [docs.cloud.google.com/billing/docs/how-to/cost-table](https://docs.cloud.google.com/billing/docs/how-to/cost-table)
- [docs.cloud.google.com/billing/docs/how-to/reports](https://docs.cloud.google.com/billing/docs/how-to/reports)

**Related notes:** [Looker Studio](../05-storage-databases-data/products/looker-studio.md)

</details>

[Back to index](#index)

---

### Q21

> Northstar Books operates a public ecommerce website on Compute Engine virtual machines in a managed instance group that scales according to average CPU utilization. To improve response times, the company stores images, style sheets, and other static files in a Cloud Storage bucket. The website must use HTTPS, and requests for dynamic and static content must use the same domain. Which configuration should Northstar Books use to distribute incoming traffic?  

- **A.** Configure a global external Application Load Balancer with a Google-managed certificate, a backend service for the managed instance group, a backend bucket for Cloud Storage, and a URL map that routes static-content paths to the backend bucket.
- **B.** Configure an external passthrough Network Load Balancer for the managed instance group, and configure the web servers to retrieve static files from Cloud Storage when requested.
- **C.** Configure an internal Application Load Balancer with Identity-Aware Proxy to accept HTTPS requests from public internet users and route static-content requests to Cloud Storage.
- **D.** Configure a global external Application Load Balancer with a backend bucket and a URL map, but install the website’s TLS certificates directly on every Compute Engine instance.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a global external Application Load Balancer is designed to accept public HTTP and HTTPS traffic and perform Layer 7 routing based on hostnames and URL paths. A URL map can send requests such as /images/\*, /css/\*, or /static/\* to a backend bucket that references the Cloud Storage bucket, while sending other requests to a backend service connected to the managed instance group. The managed instance group can independently scale its Compute Engine instances according to CPU utilization. A Google-managed certificate is associated with the load balancer’s HTTPS frontend or target HTTPS proxy, allowing Google Cloud to provision and renew the certificate automatically. This architecture provides one secure public endpoint for both dynamic application traffic and static Cloud Storage content. Cloud CDN can also be enabled on the backend bucket to further reduce latency and backend traffic.

**B is incorrect** because an external passthrough Network Load Balancer operates primarily at Layer 4 and distributes TCP, UDP, ESP, GRE, ICMP, or ICMPv6 traffic without providing HTTP-specific URL-map routing. It cannot inspect a request path and route static-content requests directly to a Cloud Storage backend bucket. Requiring the Compute Engine web servers to receive every request and then fetch or redirect static content adds unnecessary processing, increases load on the instances, and reduces the performance benefits of serving static files directly through the load balancer. It also does not provide the integrated HTTPS termination and content-based routing offered by an external Application Load Balancer.

**C is incorrect** because an internal Application Load Balancer has an internal IP address and is intended for clients that can reach the associated VPC network, such as internal workloads or clients connected through Cloud VPN or Cloud Interconnect. It is not the appropriate frontend for a publicly accessible ecommerce website. Identity-Aware Proxy controls access to supported applications by authenticating users, but it does not convert an internal load balancer into a general public website endpoint or serve as a replacement for a public HTTPS frontend. Public users should connect through an external Application Load Balancer.

**D is incorrect** because TLS certificates for an external Application Load Balancer must be configured on the load balancer’s HTTPS frontend, specifically through the target HTTPS proxy or Certificate Manager integration. Installing certificates only on the backend Compute Engine instances does not enable the external load balancer to terminate HTTPS connections from users. It also creates unnecessary certificate distribution and renewal work across autoscaled instances, including newly created instances. With a Google-managed certificate attached to the load balancer, Google Cloud manages certificate provisioning and renewal centrally, while backend communication can use the protocol configured for the backend service.

**Reference links**

- [cloud.google.com/load-balancing/docs/https/setup-global-ext-https-buckets](https://cloud.google.com/load-balancing/docs/https/setup-global-ext-https-buckets)
- [cloud.google.com/load-balancing/docs/https](https://cloud.google.com/load-balancing/docs/https)
- [cloud.google.com/certificate-manager/docs/deploy-google-managed-lb-auth](https://cloud.google.com/certificate-manager/docs/deploy-google-managed-lb-auth)

**Related notes:** [Cloud Load Balancing](../06-networking/products/cloud-load-balancing.md)

</details>

[Back to index](#index)

---

### Q22

> AtlasStream Media has installed the gcloud CLI on an administrator’s workstation and authenticated it with a Google Account. Most Compute Engine instances in the active project are located in the asia-south1-b zone. The administrator wants gcloud compute commands to use this zone automatically whenever the --zone flag is omitted. What should the administrator do?  

- **A.** Run gcloud config set compute/zone asia-south1-b in the active gcloud CLI configuration.
- **B.** Select asia-south1-b as the default zone on the Compute Engine Settings page without reinitializing the local gcloud CLI.
- **C.** Create a default.conf file in the gcloud CLI installation directory containing zone=asia-south1-b.
- **D.** Add project metadata with the key compute/zone and the value asia-south1-b.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because gcloud config set compute/zone asia-south1-b sets the compute/zone property in the active local gcloud CLI configuration. After this property is configured, zone-dependent gcloud compute commands use asia-south1-b when the administrator does not explicitly provide the --zone flag. The setting applies to the active named configuration, so it is especially useful when an administrator regularly manages resources in one zone. The configured value can be verified by running gcloud config get-value compute/zone or by reviewing the active configuration with gcloud config list. An explicitly supplied --zone flag can still override the default for an individual command.

**B is incorrect** because setting a default zone on the Compute Engine Settings page changes the project-level default stored in Compute Engine project metadata, but it does not automatically and immediately replace the compute/zone property in an already initialized local gcloud CLI configuration. The local client normally receives the project-level default when gcloud init is run. In addition, a zone configured directly in the local gcloud CLI takes precedence over the project metadata default. Because the requirement specifically concerns avoiding repeated flags on the administrator’s existing CLI installation, directly setting compute/zone with gcloud config set is the simpler and more precise solution.

**C is incorrect** because the gcloud CLI does not support configuring its active default zone by placing an arbitrary default.conf file in the installation directory. gcloud CLI properties are managed through named configurations, environment variables, or supported initialization commands. The configuration data is generally stored in the user’s gcloud configuration directory rather than the software installation directory, and users should manage it through commands such as gcloud config set instead of manually inventing configuration files. Therefore, this file would not establish the default Compute Engine zone.

**D is incorrect** because compute/zone is the name of a local gcloud CLI configuration property, not the correct Compute Engine project metadata key. The supported project metadata key for a default zone is google-compute-default-zone. Even when that correct metadata key is used, the existing local client generally must be reinitialized with gcloud init to import the project-level setting. Adding metadata with the key compute/zone would therefore not configure the desired CLI default.

**Reference links**

- [docs.cloud.google.com/compute/docs/gcloud-compute](https://docs.cloud.google.com/compute/docs/gcloud-compute)
- [docs.cloud.google.com/sdk/docs/configurations](https://docs.cloud.google.com/sdk/docs/configurations)
- [docs.cloud.google.com/compute/docs/regions-zones/changing-default-zone-region](https://docs.cloud.google.com/compute/docs/regions-zones/changing-default-zone-region)

</details>

[Back to index](#index)

---

### Q23

> ConnectSphere operates a real-time messaging gateway on a Compute Engine managed instance group. The gateway receives unencrypted TCP connections on port 5222 and must obtain the original source IP address directly from each incoming packet. You need to make the gateway publicly accessible through Cloud Load Balancing. What should you do?  

- **A.** Expose the gateway by using a regional external passthrough Network Load Balancer.
- **B.** Expose the gateway by using an external proxy Network Load Balancer with a target TCP proxy.
- **C.** Expose the gateway by using an external proxy Network Load Balancer with a target SSL proxy.
- **D.** Expose the gateway by using an internal passthrough Network Load Balancer.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a regional external passthrough Network Load Balancer is a public, Layer 4 load balancer that forwards the original TCP packets directly to backend virtual machines without terminating or proxying the client connection. Because it is a passthrough load balancer, the source IP address in each packet remains the client’s original IP address. It supports TCP traffic on ports such as 5222 and can use a managed instance group as its backend. This satisfies both requirements: exposing the service to the internet and preserving the client source IP address directly at the application.

**B is incorrect** because an external proxy Network Load Balancer terminates the client’s TCP connection at the Google Front End or Envoy proxy and establishes a separate TCP connection to the backend. Consequently, the source IP address observed at the network layer by the backend is associated with the proxy infrastructure rather than being the original client IP address. A proxy Network Load Balancer can optionally pass client connection information through the PROXY protocol, but the backend application must explicitly support and parse that protocol. This is different from preserving the client IP address in the original packet, which a passthrough Network Load Balancer provides directly.

**C is incorrect** because a target SSL proxy is intended for encrypted TCP traffic where the load balancer terminates the TLS connection before forwarding traffic to the backend. The messaging gateway in this scenario accepts unencrypted TCP traffic, so SSL termination is unnecessary. Like a target TCP proxy, an SSL proxy also creates a separate connection to the backend and does not preserve the original client source IP address at the packet level. Client details can be relayed through the PROXY protocol when supported, but that does not meet the requirement to receive the client’s original source IP directly from the forwarded packets.

**D is incorrect** because an internal passthrough Network Load Balancer can preserve the client source IP address and forward TCP packets without proxying them, but it uses an internal IP address. It is designed for clients in the same VPC network or clients that can reach the VPC through mechanisms such as Cloud VPN, Cloud Interconnect, or VPC Network Peering. It does not directly expose the application to clients on the public internet. Therefore, it satisfies the source IP preservation requirement but not the public accessibility requirement.

**Reference links**

- [docs.cloud.google.com/load-balancing/docs/passthrough-network-load-balancer](https://docs.cloud.google.com/load-balancing/docs/passthrough-network-load-balancer)
- [docs.cloud.google.com/load-balancing/docs/choosing-load-balancer](https://docs.cloud.google.com/load-balancing/docs/choosing-load-balancer)
- [docs.cloud.google.com/load-balancing/docs/proxy-network-load-balancer](https://docs.cloud.google.com/load-balancing/docs/proxy-network-load-balancer)

**Related notes:** [Cloud Load Balancing](../06-networking/products/cloud-load-balancing.md)

</details>

[Back to index](#index)

---

### Q24

> BluePeak Solutions is organizing the Google Cloud environment for a new online education platform. The platform team wants projects and their resources that require the same access permissions to be grouped together so that common IAM policies can be managed centrally. What should the team do?  

- **A.** Apply labels to resources that require the same IAM policies.
- **B.** Place the projects in folders based on their common IAM policy requirements.
- **C.** Create separate Cloud Billing accounts to group resources with common IAM policies.
- **D.** Use a standardized project naming convention to group resources with common IAM policies.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because labels are key-value metadata used primarily to organize, filter, and report on Google Cloud resources. They are useful for purposes such as identifying environments, teams, applications, and cost centers, but they do not create nodes in the Google Cloud resource hierarchy. Applying the same label to several resources does not cause those resources to inherit a common IAM policy. Labels also cannot be used as a central IAM policy attachment point. Although labels can help administrators locate related resources, IAM access would still need to be configured at an appropriate resource hierarchy level. Google Cloud tags can be used with IAM Conditions in certain scenarios, but tags and labels are different features, and neither changes the fact that folders are the standard hierarchical mechanism for grouping projects that require shared policies.

**B is correct** because folders are Resource Manager resources designed to organize projects and other folders within a Google Cloud organization. An IAM allow policy applied to a folder is inherited by the projects, nested folders, and supported resources beneath that folder. For example, the company could create separate folders for production, development, finance, and analytics workloads. It could then grant a production operations group the required IAM roles on the production folder, allowing the projects inside that folder to inherit those permissions. This approach reduces repetitive project-level IAM configuration and makes access administration more consistent. Folders can also be nested to represent departments, environments, business units, or compliance boundaries. Because the requirement is to group resources according to shared IAM policies, organizing their projects under appropriate folders and applying policies at the folder level is the correct solution.

**C is incorrect** because Cloud Billing accounts control how Google Cloud usage is paid for and how billing-related access is administered. Multiple projects can be linked to the same Cloud Billing account, but this billing relationship does not place the projects into a shared IAM inheritance hierarchy. IAM policies attached to a Cloud Billing account control access to billing functions such as viewing costs, managing payments, linking projects, or administering the billing account. They do not automatically grant operational permissions on Compute Engine instances, Cloud Storage buckets, BigQuery datasets, or other resources in the linked projects. Billing account design should reflect payment, invoicing, and financial administration requirements, while folders should be used to group projects that need common resource access policies.

**D is incorrect** because project names and project IDs are identifiers rather than policy-management boundaries. A naming convention can help administrators recognize which department, application, or environment owns a project, but Google Cloud does not automatically apply or inherit IAM policies based on matching project names. For example, projects named production-web, production-api, and production-data would not receive common permissions merely because each name contains the word production. Administrators would still have to configure policies separately or use additional automation. Placing these projects inside a production folder and applying the IAM policy to that folder provides actual policy inheritance and centralized access management.

**Reference links**

- [docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy](https://docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)
- [docs.cloud.google.com/iam/docs/resource-hierarchy-access-control](https://docs.cloud.google.com/iam/docs/resource-hierarchy-access-control)
- [docs.cloud.google.com/billing/docs/concepts](https://docs.cloud.google.com/billing/docs/concepts)

</details>

[Back to index](#index)

---

### Q25

> RouteWave is deploying a shipment-tracking service to Google Kubernetes Engine (GKE). The service must send requests to an external logistics provider that accepts connections only from approved source IP addresses. RouteWave needs highly available, scalable outbound connectivity and must ensure that the approved addresses do not unexpectedly change. What should RouteWave do?  

- **A.** Create a single-node GKE cluster, assign a static external IP address to the node, disable cluster autoscaling, and give the node address to the logistics provider.
- **B.** Create a GKE cluster with private nodes, configure a Cloud NAT gateway with manually allocated static external IP addresses, and give those addresses to the logistics provider.
- **C.** Create a GKE cluster with private nodes, configure a Cloud NAT gateway with automatically allocated IP addresses, and give the current addresses to the logistics provider.
- **D.** Create a GKE cluster with public nodes and schedule a Cloud Run function to collect and email the nodes’ external IP addresses to the logistics provider each day.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because relying on the external IP address of a single GKE node is neither highly available nor scalable. A one-node cluster creates a single point of failure, and disabling cluster autoscaling prevents GKE from adding capacity when application demand increases. GKE manages the Compute Engine instances that serve as nodes, and nodes can be repaired, upgraded, recreated, or replaced during routine cluster operations. Building a solution that depends on the identity and external address of an individual managed node is therefore fragile and conflicts with recommended GKE operational practices. Assigning public IP addresses directly to nodes also increases their exposure to the internet. A managed Cloud NAT gateway provides a more secure and resilient method for controlling outbound source addresses.

**B is correct** because private GKE nodes have only internal IP addresses and are not directly exposed to the public internet. A Public Cloud NAT gateway can provide outbound internet connectivity for workloads running on these nodes without permitting unsolicited inbound connections to them. By configuring manual NAT IP address allocation and assigning reserved static regional external IP addresses to the gateway, RouteWave controls the exact source addresses used for outbound traffic. These addresses remain stable until an administrator intentionally modifies the Cloud NAT configuration, so they can safely be supplied to the external provider for its firewall allowlist. Cloud NAT is a distributed, fully managed service rather than a proxy virtual machine or single appliance, which eliminates the need to maintain NAT instances and avoids a single point of failure. Multiple static addresses can be assigned when additional source ports or outbound capacity are required, allowing the design to scale while retaining a predictable set of allowlisted addresses.

**C is incorrect** because automatically allocated Cloud NAT addresses are managed by Google Cloud rather than explicitly reserved and controlled as part of a manual NAT IP configuration. Cloud NAT can automatically add addresses when more NAT capacity is required and remove automatically allocated addresses when they are no longer needed. Although an automatically allocated address remains static while it is assigned to the gateway, the set of addresses can change as Cloud NAT scales or as the configuration changes. Giving the vendor only the addresses visible at one point in time could therefore cause traffic to be rejected when a different automatically allocated address is used. Manual allocation of reserved static external IP addresses is the recommended choice when a third party requires a stable and predictable source-IP allowlist.

**D is incorrect** because public GKE nodes can be replaced during upgrades, repairs, scaling operations, or other lifecycle events, causing their external IP addresses to change. Collecting the current addresses once per day would not prevent an interruption because a node replacement could occur at any time, and outbound traffic could begin using a new address before the vendor updates its firewall. Emailing frequently changing addresses also creates an unreliable manual operational process and requires the vendor to continually modify its allowlist. Public node addresses additionally increase the cluster’s external exposure. Private nodes combined with Cloud NAT and manually allocated static external IP addresses provide stable egress identities without requiring ongoing address discovery or manual coordination.

**Reference links**

- [docs.cloud.google.com/nat/docs/overview](https://docs.cloud.google.com/nat/docs/overview)
- [docs.cloud.google.com/nat/docs/gke-example](https://docs.cloud.google.com/nat/docs/gke-example)
- [docs.cloud.google.com/kubernetes-engine/docs/best-practices/networking](https://docs.cloud.google.com/kubernetes-engine/docs/best-practices/networking)

**Related notes:** [Cloud NAT](../06-networking/products/cloud-nat.md)

</details>

[Back to index](#index)

---

### Q26

> NovaLedger is moving its public documentation website and a monthly billing process to Google Cloud. The website contains only static HTML files and must serve users from multiple regions while automatically scaling with demand. The billing process is an asynchronous task initiated through an HTTP request and produces customer statements once each month. NovaLedger wants managed services that have no active compute charges while idle and require minimal infrastructure administration. What should NovaLedger do?  

- **A.** Deploy the website to Google Kubernetes Engine (GKE), and deploy the billing process as a Cloud Run function.
- **B.** Deploy both the website and the billing process to Compute Engine.
- **C.** Deploy the website as a Cloud Run service, and deploy the billing process by using Cloud Run.
- **D.** Deploy the website to Google Kubernetes Engine (GKE), and deploy the billing process to Compute Engine.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a Cloud Run function can receive an HTTP request, automatically scale, and avoid active compute charges while it is idle, so it could be suitable for initiating the billing process. However, Google Kubernetes Engine is unnecessarily complex for a website containing only static HTML. Hosting the website on GKE requires Kubernetes resources such as Deployments, Services, Pods, ingress configuration, and potentially load-balancing resources. Because the website must remain available, serving capacity must also be maintained, and the company must manage more infrastructure than necessary. Although GKE provides extensive orchestration capabilities, those capabilities are not required for a simple static website. Cloud Run provides a more direct serverless deployment model with automatic scaling and less operational overhead.

**B is incorrect** because Compute Engine requires the company to provision and manage virtual machines, operating systems, software updates, instance templates, health checks, and scaling policies. Virtual machines that remain running to keep the website available continue to generate compute charges even during periods with no traffic. A managed instance group can provide autoscaling and geographic redundancy, but it introduces significantly more configuration and administration than a serverless platform. Compute Engine is also inefficient for a monthly background process because the company would either keep a virtual machine running between executions or implement additional automation to create and remove compute resources. Therefore, this option does not best satisfy the requirements for minimal operations and no active compute charges while workloads are idle.

**C is correct** because Cloud Run is a fully managed serverless platform that can host HTTP-based applications and execute containerized jobs without requiring the company to manage servers or Kubernetes clusters. NovaLedger can package the static HTML website with a lightweight web server and deploy it as a Cloud Run service. Cloud Run automatically adds instances when requests increase and, with the minimum instance count left at zero, scales the service to zero when there is no traffic. For geographic availability, the company can deploy the same service in multiple Google Cloud regions and place the regional services behind a global external Application Load Balancer. The monthly billing process can be implemented as a Cloud Run job, which runs its containerized tasks to completion and consumes compute resources only during an execution. The job can be initiated through an authenticated HTTP POST request to the Cloud Run Admin API. Alternatively, an HTTP-facing Cloud Run service can validate the request and initiate the job asynchronously. This architecture provides automatic scaling, multi-region website delivery, scale-to-zero behavior, and minimal infrastructure management.

**D is incorrect** because this option uses infrastructure-oriented services for both workloads even though neither workload requires dedicated servers or Kubernetes orchestration. Hosting static HTML on GKE introduces unnecessary cluster, workload, networking, and deployment management. Running the monthly billing process on Compute Engine requires virtual machine lifecycle management and can generate charges while the VM is idle unless additional automation is implemented. The company would also need to design its own mechanism for safely accepting the HTTP request, starting the process, monitoring its completion, retrying failures, and shutting down resources afterward. Cloud Run provides these serverless execution and scaling characteristics with substantially less operational effort.

**Reference links**

- [docs.cloud.google.com/run/docs/overview/what-is-cloud-run](https://docs.cloud.google.com/run/docs/overview/what-is-cloud-run)
- [docs.cloud.google.com/run/docs/multiple-regions](https://docs.cloud.google.com/run/docs/multiple-regions)
- [docs.cloud.google.com/run/docs/execute/jobs](https://docs.cloud.google.com/run/docs/execute/jobs)

</details>

[Back to index](#index)

---

### Q27

> BrightCart, an online retail company, is preparing to migrate its data-center applications to Google Cloud. Before the migration, the cloud team must build a landing zone that allows production VMs in different projects to communicate by using internal IP addresses. The security team also needs to centrally permit inbound connections to all applicable VMs on TCP ports 8443 and 9443 across the organization. BrightCart wants to follow Google-recommended practices while minimizing networking complexity and ongoing operational costs. What should the cloud team do?  

- **A.** Create a separate VPC network in every production project, connect all the VPC networks by using VPC Network Peering, and apply organization policies at the organization level.
- **B.** Create a separate VPC network in every production project, connect all the VPC networks by using VPC Network Peering, and apply hierarchical firewall policies at the organization level.
- **C.** Configure a host project containing a Shared VPC network, attach every production project as a service project, and apply organization policies at the organization level.
- **D.** Configure a host project containing a Shared VPC network, attach every production project as a service project, and apply hierarchical firewall policies at the organization level.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because creating a separate VPC network for every project and connecting every network through VPC Network Peering introduces unnecessary networking and administrative complexity. VPC Network Peering relationships must be created and maintained between the participating networks, and peering is not transitive. As the number of projects grows, the organization might need to manage many individual peering relationships, routing configurations, overlapping IP address concerns, and network-level security controls. This increases operational effort and cost compared with using a centrally managed Shared VPC. Additionally, organization policies do not define network traffic rules or allow connections on specific TCP ports. Organization Policy Service constraints govern which resource configurations are permitted or restricted, such as whether certain resource features may be used. They are not a replacement for firewall rules or firewall policies.

**B is incorrect** because hierarchical firewall policies are the correct mechanism for centrally allowing or denying traffic on specific protocols and ports across an organization, but the proposed VPC architecture is unnecessarily complex. Creating an individual VPC network for each production project and fully connecting the networks through VPC Network Peering requires the cloud team to create, monitor, and maintain multiple peering relationships. Because VPC Network Peering does not provide transitive routing, a project cannot automatically reach another project through an intermediate peered network. The team would therefore need direct peerings between networks that must communicate. Although the organization-level hierarchical firewall policy would provide centralized security enforcement, the separate peered VPC design does not minimize operational costs and is less suitable than a Shared VPC for centrally managed production workloads across multiple projects.

**C is incorrect** because a Shared VPC is the appropriate networking architecture, but organization policies cannot satisfy the firewall requirement. A Shared VPC allows resources in multiple service projects to use subnets from a common VPC network located in a host project. VMs in those service projects can communicate through internal IP addresses, subject to routes and firewall controls. This design centralizes network administration, simplifies connectivity, separates workload ownership from network ownership, and avoids maintaining a large collection of VPC Network Peering connections. However, organization policies are used to restrict or enforce resource configuration choices, not to allow inbound TCP connections. Because this option does not configure hierarchical firewall policies or another suitable firewall mechanism, it cannot centrally permit the required TCP ports.

**D is correct** because it combines the appropriate centralized network architecture with the appropriate centralized security control. A Shared VPC lets BrightCart place the VPC network, subnets, routes, and other shared networking resources in a dedicated host project while attaching the production workload projects as service projects. VMs created in the service projects can use the Shared VPC subnets and communicate through internal IP addresses without requiring a full mesh of VPC Network Peering connections. This approach supports centralized network governance, reduces duplicated network resources, simplifies administration, and follows common Google Cloud landing-zone practices. Hierarchical firewall policies can be associated with the organization and inherited by folders, projects, VPC networks, and applicable VM interfaces beneath that organization. The organization can create ingress allow rules for TCP ports 8443 and 9443 and enforce them consistently across the production environment. The rules should use appropriately restricted source ranges, targets, and priorities rather than exposing the ports more broadly than necessary. Together, Shared VPC and organization-level hierarchical firewall policies provide private connectivity, centralized policy enforcement, scalability, and lower ongoing operational overhead.

**Reference links**

- [docs.cloud.google.com/vpc/docs/shared-vpc](https://docs.cloud.google.com/vpc/docs/shared-vpc)
- [docs.cloud.google.com/firewall/docs/firewall-policies](https://docs.cloud.google.com/firewall/docs/firewall-policies)
- [docs.cloud.google.com/architecture/landing-zones/implement-network-design](https://docs.cloud.google.com/architecture/landing-zones/implement-network-design)

**Related notes:** [VPC Network Peering and Shared VPC](../06-networking/products/vpc-network-peering-and-shared-vpc.md)

</details>

[Back to index](#index)

---

### Q28

> AeroPulse, a flight analytics company, has several application teams that create Google Cloud environments for new services. The platform team has established mandatory standards for networking, labels, encryption, logging, and IAM. Application teams must be able to deploy resources independently without needing to understand how every standard is technically implemented. What should the platform team do?  

- **A.** Configure organization policies for the required standards, and instruct application teams to create their resources manually through the Google Cloud console.
- **B.** Create a service account for each application team, grant each service account the Editor role, and instruct the teams to deploy resources with the Google Cloud CLI while impersonating their assigned service account.
- **C.** Develop reusable Terraform modules that implement the company’s required standards, and instruct application teams to provision their infrastructure by using those modules.
- **D.** Train every application team on the required standards, and allow each team to design and provision its Google Cloud infrastructure independently.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because organization policies provide centralized guardrails that restrict how resources can be configured, but they do not provide complete, reusable infrastructure implementations for engineering teams. For example, an organization policy can prevent prohibited configurations, restrict resource locations, or require specific security characteristics, but it does not automatically create a compliant VPC network, subnet, service account, logging configuration, or application environment. Teams using the Google Cloud console would still need to understand the company’s implementation details and manually configure each component correctly. Manual provisioning also increases the likelihood of inconsistent environments, configuration drift, and deployment errors. Organization policies can complement the recommended solution by enforcing mandatory constraints, but they do not replace reusable infrastructure-as-code modules.

**B is incorrect** because service account impersonation controls which identity and permissions are used when commands are executed, but it does not abstract or automatically implement the company’s infrastructure standards. Engineers would still need to know the correct Google Cloud CLI commands, resource settings, networking design, labels, encryption options, and security configurations. Granting the basic Editor role is also excessively broad because it provides extensive permissions to create and modify resources across a project and does not follow the principle of least privilege. Service account impersonation is preferable to distributing long-lived service account keys, but it is an authentication mechanism rather than a standardized infrastructure deployment solution. This approach would therefore neither encode the required practices nor ensure consistent deployments.

**C is correct** because reusable Terraform modules allow the platform team to encode the company’s approved architecture and configuration standards into predefined infrastructure components. A module can contain the required networking configuration, labels, IAM bindings, encryption settings, logging controls, naming conventions, and other mandatory settings. Engineering teams can deploy these components by supplying only the documented input variables relevant to their workloads, without needing to understand every underlying implementation detail. This provides a self-service deployment model while producing consistent and repeatable environments. The modules can be version-controlled, reviewed, tested, updated centrally, and reused by multiple teams. Terraform also provides declarative infrastructure management, execution plans, repeatability, and reduced configuration drift. Organization policies can still be applied as preventive guardrails, but the Terraform modules provide the reusable implementation layer requested in the scenario.

**D is incorrect** because training can improve engineers’ awareness of organizational standards, but it does not automatically apply those standards or hide their implementation details. Every team could interpret the requirements differently, resulting in inconsistent architectures, duplicated work, configuration errors, and security gaps. The platform team would also need to repeat training whenever standards or personnel changed. Allowing teams to provision resources according to their own interpretations does not provide a controlled and repeatable deployment mechanism. Training can support the adoption of a standardized platform, but it should not replace reusable Terraform modules that encode the approved practices directly.

**Reference links**

- [docs.cloud.google.com/docs/terraform/best-practices/reusable-modules](https://docs.cloud.google.com/docs/terraform/best-practices/reusable-modules)
- [docs.cloud.google.com/docs/terraform/blueprints/terraform-blueprints](https://docs.cloud.google.com/docs/terraform/blueprints/terraform-blueprints)
- [docs.cloud.google.com/resource-manager/docs/organization-policy/overview](https://docs.cloud.google.com/resource-manager/docs/organization-policy/overview)

**Related notes:** [Terraform](../08-iac-platform-ai/products/terraform.md)

</details>

[Back to index](#index)

---

### Q29

> BrightLedger runs a payment-processing service on a Compute Engine instance named ledger-prod-07. The security team must be able to review detected operating system vulnerabilities and related vulnerability-report information for this VM while receiving only the permissions required for that task. What should you do?  

- **A.** Verify that the Ops Agent is installed on ledger-prod-07, publish vulnerability information as a custom Cloud Monitoring metric, and grant the security analyst access to the monitoring dashboard.
- **B.** Verify that the Ops Agent is installed on ledger-prod-07 and grant the security analyst the roles/osconfig.inventoryViewer IAM role.
- **C.** Verify that the OS Config agent is installed and enabled on ledger-prod-07 and grant the security analyst the roles/osconfig.vulnerabilityReportViewer IAM role.
- **D.** Verify that the OS Config agent is installed on ledger-prod-07, export its logs to a BigQuery dataset through a log sink, and grant the security analyst access to the dataset.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the Ops Agent collects telemetry such as logs, metrics, and traces for Cloud Logging and Cloud Monitoring. It does not generate the VM Manager vulnerability reports used to identify operating system package vulnerabilities and associated Common Vulnerabilities and Exposures information. A custom Cloud Monitoring metric would also require an additional mechanism to obtain, transform, and publish vulnerability data. Giving the security analyst access to a dashboard therefore does not provide the native vulnerability-report capability required by the policy.

**B is incorrect** because roles/osconfig.inventoryViewer is intended for viewing OS inventory information, including operating system details, installed packages, available package updates, and related inventory metadata. However, it does not contain the osconfig.vulnerabilityReports.get and osconfig.vulnerabilityReports.list permissions required to retrieve vulnerability reports. The Ops Agent is also the wrong agent for VM Manager OS inventory and vulnerability reporting. The OS Config agent performs the inventory scans that supply this information to the OS Config service. Current Google Cloud console workflows can require both OS Inventory Viewer and OS Config Vulnerability Report Viewer permissions when displaying inventory and vulnerability information together, but this option provides only the inventory role and does not enable the correct agent.

**C is correct** because VM Manager uses the OS Config agent to collect OS inventory data and generate vulnerability reports for supported Compute Engine instances. The agent identifies installed operating system packages, sends inventory information to the OS Config service, and enables Google Cloud to compare that information with known vulnerability data. The roles/osconfig.vulnerabilityReportViewer predefined IAM role provides read-only permissions such as osconfig.vulnerabilityReports.get and osconfig.vulnerabilityReports.list, allowing the security analyst to inspect vulnerability reports without receiving permissions to modify the VM or execute remediation actions. This follows the principle of least privilege and is the option that directly enables access to vulnerability-report information. The OS Config API and the necessary VM Manager functionality must also be enabled and configured for the instance. When the analyst must use Google Cloud console pages that combine vulnerability reports with complete OS inventory details, roles/osconfig.inventoryViewer might additionally be required, but among the listed choices, this is the correct implementation for viewing vulnerability reports.

**D is incorrect** because exporting OS Config agent logs to BigQuery provides log records, not the structured VM Manager vulnerability-report resources maintained by the OS Config service. Log sinks route matching Cloud Logging entries to a destination, but they do not automatically convert those entries into an authoritative inventory of installed packages and detected vulnerabilities. This approach would introduce unnecessary storage, query, IAM, and log-filter management while potentially providing either incomplete information or excessive access. The security analyst should instead receive the predefined read-only vulnerability-report role.

**Reference links**

- [docs.cloud.google.com/compute/vm-manager/docs/setup](https://docs.cloud.google.com/compute/vm-manager/docs/setup)
- [docs.cloud.google.com/compute/vm-manager/docs/os-inventory/vulnerability-reports](https://docs.cloud.google.com/compute/vm-manager/docs/os-inventory/vulnerability-reports)
- [docs.cloud.google.com/iam/docs/roles-permissions/osconfig](https://docs.cloud.google.com/iam/docs/roles-permissions/osconfig)

**Related notes:** [OS Config / VM Manager](../02-identity-security/products/os-config-vm-manager.md)

</details>

[Back to index](#index)

---

### Q30

> HarborTrack Logistics runs a Java shipment-processing application in its private data center. The application must consume delivery events from Pub/Sub. HarborTrack’s infrastructure can obtain identity tokens from an OIDC-compatible identity provider, but company policy prohibits creating or downloading service account keys. The developers also want the Pub/Sub client library to discover credentials automatically through Application Default Credentials. What should HarborTrack Logistics configure?  

- **A.** Generate a Workload Identity Federation credential configuration file and set GOOGLE_APPLICATION_CREDENTIALS to the file’s location.
- **B.** Sign in on the production server by running gcloud auth login with a shared platform administrator account.
- **C.** Save a service account JSON key in Secret Manager and retrieve the key whenever the application starts.
- **D.** Configure Workforce Identity Federation because the Java application is operated by members of the infrastructure team.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Workload Identity Federation is designed for applications and other workloads running outside Google Cloud that can authenticate through an external identity provider. HarborTrack can create a workload identity pool, configure an OIDC provider that trusts its data center’s identity provider, map and validate the required token claims, and authorize the resulting federated principal to access Pub/Sub directly or impersonate a least-privileged service account. The generated credential configuration file is an external-account configuration rather than a service account private key. It tells the Google authentication library how to obtain the external OIDC token, exchange it through Google Cloud’s Security Token Service, and optionally obtain short-lived service account credentials. By setting GOOGLE_APPLICATION_CREDENTIALS to this file, Application Default Credentials discovers the configuration automatically, allowing the existing Java Pub/Sub client code to continue using ADC without embedding authentication logic or storing a downloadable service account key.

**B is incorrect** because gcloud auth login is primarily an interactive authentication method for the gcloud CLI and normally uses a human user identity. A shared administrator account on a production server would weaken accountability, grant unnecessarily broad privileges, create an operational dependency on a human login session, and make credential lifecycle management difficult. The application requires unattended workload authentication, not interactive administrator authentication. Additionally, credentials configured for the gcloud CLI are distinct from Application Default Credentials unless ADC is separately configured. Workload Identity Federation provides an automated and identity-provider-backed authentication flow that is more appropriate for a production Java process.

**C is incorrect** because storing a service account key in Secret Manager does not eliminate the key. The application would still download a persistent private credential that could be copied, logged, cached, or extracted from the production server. Anyone who obtained the key could authenticate as the service account until the key was disabled or deleted, regardless of whether the request came from the authorized data center. This approach directly violates the requirement prohibiting downloadable service account keys. Secret Manager can protect sensitive values at rest, but it does not convert a long-lived service account key into a short-lived federated credential. Workload Identity Federation avoids creating the private key and exchanges the application’s OIDC identity for temporary Google Cloud credentials.

**D is incorrect** because Workforce Identity Federation is intended for human users, including employees, contractors, partners, and other workforce members who authenticate through an external identity provider. The Java application is a non-human workload, even though human members of the infrastructure team operate and maintain it. Identity federation must be selected according to the identity accessing Google Cloud, not the department responsible for the software. Workload Identity Federation is the appropriate mechanism for an on-premises process that programmatically accesses Pub/Sub, while Workforce Identity Federation would be appropriate for an individual administrator who needs interactive access to Google Cloud resources.

**Reference links**

- [docs.cloud.google.com/docs/authentication/set-up-adc-on-premises](https://docs.cloud.google.com/docs/authentication/set-up-adc-on-premises)
- [docs.cloud.google.com/iam/docs/workload-identity-federation-with-other-providers](https://docs.cloud.google.com/iam/docs/workload-identity-federation-with-other-providers)
- [docs.cloud.google.com/docs/authentication/application-default-credentials](https://docs.cloud.google.com/docs/authentication/application-default-credentials)

**Related notes:** [Application Default Credentials (ADC)](../02-identity-security/products/application-default-credentials.md)

</details>

[Back to index](#index)

---

### Q31

> HarborLink Media is connecting a new Google Cloud VPC network to its corporate data center. The VPC must use the IPv4 subnet range 10.42.8.0/22, exchange routes dynamically with the on-premises router, and preserve the same usable tunnel capacity when one VPN path fails. The network team wants to follow Google-recommended practices for a highly available Cloud VPN connection. What should the team do?  

- **A.** Create a custom mode VPC network, configure static routes, and use active-passive routing.
- **B.** Create an auto mode VPC network, configure static routes, and use active-active routing.
- **C.** Create a custom mode VPC network, configure Cloud Router with Border Gateway Protocol routes, and use active-passive routing.
- **D.** Create an auto mode VPC network, configure Cloud Router with Border Gateway Protocol routes, and use policy-based routing.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a custom mode VPC network is appropriate when the organization needs direct control over subnet ranges such as 10.42.8.0/22, and active-passive routing is appropriate for a two-tunnel HA VPN configuration that should maintain consistent capacity during failover. However, static routing does not meet the requirement for dynamic route exchange. HA VPN tunnels require dynamic routing through Cloud Router and Border Gateway Protocol. Static or policy-based routing is associated with Classic VPN configurations and should be considered only when BGP and HA VPN cannot be used. Therefore, this option includes the correct VPC network mode and routing preference but uses the wrong route-management method.

**B is incorrect** because an auto mode VPC network automatically creates subnets in every Google Cloud region using predefined IP ranges. It does not provide the same level of address-planning control as a custom mode network and can create unnecessary subnets or overlap concerns when connecting to an existing remote network. This option also uses static routes, which do not satisfy the dynamic routing requirement and are not supported by HA VPN. Active-active routing can distribute traffic across both tunnels, but the combined normal throughput can be reduced by half when one tunnel fails. That behavior does not meet the requirement to preserve the same observed capacity during failover without designing around the loss of one active path.

**C is correct** because a custom mode VPC network allows HarborLink Media to create only the required subnets and assign the specified 10.42.8.0/22 address range instead of accepting the predefined ranges and automatically created regional subnets of an auto mode network. Cloud Router provides dynamic route exchange between Google Cloud and the remote site by establishing BGP sessions over the HA VPN tunnels. It automatically learns, advertises, adds, and removes routes as network reachability changes, eliminating the need to maintain static routes manually. For a single HA VPN gateway with two tunnels, Google recommends active-passive routing. Both tunnels and their BGP sessions remain established, but different route priorities cause normal traffic to prefer one tunnel while the second tunnel serves as the failover path. Because normal operation uses one tunnel and failover also uses one tunnel, the observed bandwidth capacity remains consistent when the preferred tunnel fails. This avoids the capacity reduction that can occur when an active-active configuration changes from two traffic-carrying tunnels to one.

**D is incorrect** because Cloud Router and BGP provide the required dynamic routing, but the other parts of the configuration are unsuitable. An auto mode VPC network automatically creates regional subnets from predefined ranges and is not the recommended choice when the organization must control its subnet address plan precisely. More importantly, policy-based routing is a static-routing option for Classic VPN, not an HA VPN routing model. HA VPN requires dynamic BGP routing and supports active-active or active-passive routing by adjusting route priorities. Combining Cloud Router BGP routes with policy-based VPN routing does not represent a valid recommended HA VPN design.

**Reference links**

- [docs.cloud.google.com/network-connectivity/docs/vpn/concepts/topologies](https://docs.cloud.google.com/network-connectivity/docs/vpn/concepts/topologies)
- [docs.cloud.google.com/network-connectivity/docs/vpn/concepts/best-practices](https://docs.cloud.google.com/network-connectivity/docs/vpn/concepts/best-practices)
- [docs.cloud.google.com/network-connectivity/docs/vpn/concepts/choosing-networks-routing](https://docs.cloud.google.com/network-connectivity/docs/vpn/concepts/choosing-networks-routing)

**Related notes:** [Cloud Router, Cloud VPN, and Cloud Interconnect](../06-networking/products/cloud-router-cloud-vpn-and-cloud-interconnect.md)

</details>

[Back to index](#index)

---

### Q32

> MarketWave operates an online retail platform through an existing Cloud Run service. The engineering team needs to release an updated checkout feature while limiting the number of shoppers affected if the new revision fails. The deployment must not require customers to change how they access the service or take any additional action. What should the team do?  

- **A.** Instruct shoppers to retry failed requests with exponential backoff after the new revision is released.
- **B.** Gradually deploy the new revision by splitting traffic between the existing and new revisions, and retain the ability to roll back.
- **C.** Immediately direct all production traffic to the new revision and restore the previous revision only after errors are detected.
- **D.** Deploy the updated application as a separate Cloud Run service and instruct shoppers to access the new service URL.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because exponential backoff is a useful client-side technique for handling transient failures, throttling, and temporary service unavailability, but it does not reduce the number of customers initially exposed to a defective Cloud Run revision. All customers could still encounter the problem after deployment. It would also require customers or client application developers to implement retry behavior, which introduces development effort and pushes operational responsibility onto customers. Google-recommended Cloud Run revision management instead limits exposure by controlling how much traffic reaches the new revision.

**B is correct** because Cloud Run creates an immutable revision when a new application version or revision-level configuration is deployed. Cloud Run traffic splitting allows the development team to send a small percentage of production traffic to the new revision while the stable revision continues handling the remaining requests. The team can monitor errors, latency, logs, and other telemetry and gradually increase the new revision’s traffic allocation as confidence grows. If the new revision causes problems, traffic can be reassigned to the previous stable revision without requiring customers to change URLs, retry requests manually, or perform any other action. This gradual rollout, also commonly called a canary rollout, minimizes the potential impact of an outage and provides a straightforward rollback path.

**C is incorrect** because sending 100% of production traffic to an unproven revision immediately exposes every customer to any defects or outages in that revision. Although Cloud Run supports rolling traffic back to a previous revision, the team might not detect and reverse the problem before many customers are affected. This approach has a larger failure domain than a gradual rollout and does not satisfy the requirement to reduce the number of customers who could be affected.

**D is incorrect** because deploying the application to a second Cloud Run service creates a different service endpoint and requires separate configuration, access control, monitoring, and operational management. Asking customers to use another service URL transfers deployment complexity to them and may require changes to clients, bookmarks, integrations, or documentation. A second service can be useful when applications need independent domains, permissions, scaling settings, or lifecycles, but it is unnecessary for safely releasing a new version of the same application. Cloud Run revisions and traffic splitting provide the required functionality within the existing service and URL.

**Reference links**

- [docs.cloud.google.com/run/docs/managing/revisions](https://docs.cloud.google.com/run/docs/managing/revisions)
- [docs.cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration](https://docs.cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration)
- [docs.cloud.google.com/run/docs/overview/what-is-cloud-run](https://docs.cloud.google.com/run/docs/overview/what-is-cloud-run)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md)

</details>

[Back to index](#index)

---

### Q33

> NovaCart Labs is creating a new online ordering platform and needs a Jenkins server to build, test, and deploy its source code. The development team wants to provision Jenkins on Google Cloud with the least installation effort and as quickly as possible. What should NovaCart Labs do?  

- **A.** Select a preconfigured Jenkins solution from Google Cloud Marketplace and deploy it.
- **B.** Create a Compute Engine VM, install Java, download Jenkins, and configure Jenkins manually.
- **C.** Create a Google Kubernetes Engine cluster and deploy a container containing the Jenkins image.
- **D.** Build an instance template containing Jenkins and use it to create a managed instance group.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Google Cloud Marketplace provides ready-to-deploy software solutions with much of the required infrastructure and application configuration already defined. Deploying a Jenkins solution from Google Cloud Marketplace can automatically provision the necessary Compute Engine resources and provide a preconfigured Jenkins environment. This minimizes manual installation, dependency management, infrastructure configuration, and setup time. Because NovaCart Labs needs a Jenkins installation as quickly and easily as possible, using a prepackaged Marketplace solution directly satisfies the requirement.

**B is incorrect** because manually creating a Compute Engine VM and installing Jenkins requires several additional administrative steps. The team would need to select an operating system, configure networking and firewall rules, install a supported Java runtime, download and install Jenkins, configure storage, initialize Jenkins, install plugins, and manage security settings. This approach provides greater control over the environment, but it is not the quickest or easiest installation method when a preconfigured solution is available through Google Cloud Marketplace.

**C is incorrect** because running Jenkins on Google Kubernetes Engine introduces unnecessary complexity for this requirement. The team would first need to create or configure a GKE cluster, prepare Kubernetes manifests, deploy the Jenkins container, configure persistent storage, expose the Jenkins service, manage credentials, and maintain the cluster. Kubernetes can be appropriate when an organization already operates containerized workloads or needs dynamically scalable Jenkins build agents, but creating an entire cluster solely to obtain a basic Jenkins installation is more complicated than deploying a preconfigured Marketplace solution.

**D is incorrect** because an instance template and managed instance group are designed primarily for creating and operating groups of consistently configured VM instances. Jenkins controllers generally maintain persistent configuration, job history, plugins, credentials, and other state, so simply creating multiple identical Jenkins VMs does not produce a coordinated or highly available Jenkins installation. The team would also have to create and maintain the Jenkins image or startup configuration before building the template. A managed instance group therefore adds substantial configuration and operational complexity without meeting the requirement for the fastest and easiest initial deployment.

**Reference links**

- [docs.cloud.google.com/marketplace/docs/deploy-through-CLI](https://docs.cloud.google.com/marketplace/docs/deploy-through-CLI)
- [docs.cloud.google.com/compute/docs/instances/create-start-instance](https://docs.cloud.google.com/compute/docs/instances/create-start-instance)
- [docs.cloud.google.com/kubernetes-engine/docs/deploy-app-cluster](https://docs.cloud.google.com/kubernetes-engine/docs/deploy-app-cluster)

**Related notes:** [Cloud Marketplace](../08-iac-platform-ai/products/cloud-marketplace.md)

</details>

[Back to index](#index)

---

### Q34

> MetroFleet Scooters rents electric delivery scooters to businesses across several cities. Each scooter contains sensors that report battery charge, motor temperature, speed, and distance traveled every two seconds. MetroFleet uses these readings to calculate customer invoices. The platform must handle a very large stream of events, retrieve readings efficiently in event-time order, and write each sensor event atomically. What should MetroFleet do?  

- **A.** Create one Cloud Storage object for each scooter and continuously append new sensor readings to that object.
- **B.** Create one file in Filestore for each scooter and append every sensor reading to the corresponding file.
- **C.** Store the readings in Firestore in Datastore mode and place all readings from the same scooter in one entity group.
- **D.** Store the readings in Bigtable and use a row key that combines a distributed scooter identifier with the event timestamp.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Cloud Storage is object storage, and Cloud Storage objects are immutable after they are successfully created. An application cannot continuously append individual sensor readings to an existing object in the same way that it appends records to a local file. It would need to replace the entire object, create separate objects, or use compose operations, making this design inefficient for sensor events arriving every few seconds. Keeping all readings for a scooter in one increasingly large object would also make it difficult to retrieve individual readings or efficiently scan a specific event-time range. Cloud Storage is better suited to storing files, archives, exports, backups, and aggregated sensor data than serving as the primary database for high-frequency event ingestion.

**B is incorrect** because Filestore provides managed network file storage through protocols such as NFS. Although an application can append data to files stored in Filestore, a file-per-scooter design does not provide database-level indexing, scalable event-time queries, or atomic storage and retrieval of individual sensor records. Multiple application workers appending to the same file would also require file locking, coordination, record-boundary management, and failure recovery. As the fleet and ingestion rate grow, large append-only files would become difficult to search and process efficiently. Filestore is intended primarily for applications that require a shared POSIX-compatible file system, not for a high-throughput operational time-series database.

**C is incorrect** because storing every reading for one scooter in a single Firestore in Datastore mode entity group concentrates that scooter’s write activity into the same logical data hierarchy. Entity groups are useful when related entities must participate in strongly consistent transactional operations, but grouping a continuous high-volume event stream this way can introduce unnecessary transactional contention and scaling constraints. Each sensor event is independent, so a transaction spanning the scooter’s entire event history is not required. Firestore in Datastore mode can store and query event records, but this entity-group design is less appropriate than Bigtable for a large, continuously growing time-series workload requiring predictable low-latency access at very high throughput.

**D is correct** because Bigtable is designed for massive, high-throughput, low-latency workloads such as telemetry, Internet of Things data, financial records, and time-series events. Bigtable stores rows in lexicographic order by row key, so a composite key containing a suitably distributed scooter identifier followed by an event timestamp enables efficient retrieval of readings for a particular scooter over a specified time range. Each event can be stored in a separate row, and Bigtable mutations are atomic at the row level, satisfying the requirement that an individual sensor signal be written atomically. The scooter identifier or another distribution component should appear before the timestamp because using a timestamp alone, or placing it at the beginning of every row key, can direct sequential writes to a narrow key range and create a hotspot. A carefully designed composite key distributes writes while preserving efficient event-time scans.

**Reference links**

- [docs.cloud.google.com/bigtable/docs/schema-design-time-series](https://docs.cloud.google.com/bigtable/docs/schema-design-time-series)
- [docs.cloud.google.com/bigtable/docs/overview](https://docs.cloud.google.com/bigtable/docs/overview)
- [docs.cloud.google.com/storage/docs/objects](https://docs.cloud.google.com/storage/docs/objects)

**Related notes:** [Bigtable](../05-storage-databases-data/products/bigtable.md)

</details>

[Back to index](#index)

---

### Q35

> NovaArcade Studios operates RealmRush, a real-time multiplayer strategy game used by players in several continents. The application must store player profiles, match results, rankings, and other game data. As traffic grows, NovaArcade needs a managed database that provides scalable performance, low-latency access for worldwide players, and consistent data without requiring the operations team to manage separate regional databases. What should NovaArcade do?  

- **A.** Store the game data in Cloud SQL and create cross-region read replicas in North America, Europe, and Asia.
- **B.** Store player and match data in a multi-region Cloud Spanner database.
- **C.** Store match data in BigQuery and place a Memorystore for Redis instance in front of it for globally consistent access.
- **D.** Store match data in Bigtable and use the player username as the row key.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Cloud SQL cross-region read replicas are primarily used to offload read traffic, support regional migration, or provide disaster-recovery capabilities. These replicas are read-only and are updated from the primary instance through asynchronous replication, which means a replica can temporarily lag behind the primary database. Writes must normally be directed to the primary instance, so players located far from that primary region could experience higher write latency. The application would also need logic for routing reads and writes, handling replication lag, promoting replicas during failures, and managing the behavior of multiple regional instances. Although Cloud SQL is a managed relational database, this architecture does not provide the transparent, globally distributed, strongly consistent database required by the scenario.

**B is correct** because Cloud Spanner is a fully managed, horizontally scalable relational database designed for applications that need global distribution, transactional consistency, and high availability. A multi-region Spanner configuration automatically replicates data across regions while maintaining strong consistency and ACID transaction guarantees. Players can therefore access a single logical database instead of the development team operating independent regional databases and resolving conflicting updates. Spanner can automatically distribute and rebalance data as the number of players and game transactions increases. It is particularly suitable for globally available gaming workloads involving player profiles, inventories, rankings, match results, and other related records that must remain consistent during concurrent updates. This provides scalable global performance while keeping operational complexity low.

**C is incorrect** because BigQuery is primarily an analytics data platform optimized for scanning and analyzing large datasets rather than serving latency-sensitive transactional requests from a real-time gaming application. Operations such as frequently updating player statistics, recording match events, modifying inventories, or maintaining live rankings require an operational database with efficient point reads, writes, and transactions. Memorystore for Redis can accelerate access by caching frequently requested data, but a cache does not convert BigQuery into a transactional database or provide global consistency. Memorystore instances are regional resources, and using Redis in front of BigQuery would also require the application team to implement cache population, expiration, invalidation, failure handling, and synchronization with the underlying data. This increases management complexity and does not provide a single globally consistent source of truth.

**D is incorrect** because Bigtable is a scalable wide-column NoSQL database suited to high-throughput, low-latency workloads such as time-series data, telemetry, event streams, and large key-based datasets. However, it does not provide the same globally consistent relational transaction model as Cloud Spanner. Bigtable transactions are limited to operations within a single row, and replicated instances using multi-cluster routing normally provide eventual consistency. Using the username as the row key might support direct lookups, but it does not address transactions involving several related records, such as simultaneously updating a player profile, match result, team score, inventory, and leaderboard. Concentrating all activity for a heavily used account in one row can also limit workload distribution. Bigtable can store game events effectively in some architectures, but it is not the best choice for the globally consistent operational data described here.

**Reference links**

- [docs.cloud.google.com/spanner/docs/best-practices-gaming-database](https://docs.cloud.google.com/spanner/docs/best-practices-gaming-database)
- [docs.cloud.google.com/sql/docs/mysql/replication](https://docs.cloud.google.com/sql/docs/mysql/replication)
- [docs.cloud.google.com/bigtable/docs/routing](https://docs.cloud.google.com/bigtable/docs/routing)

**Related notes:** [Spanner](../05-storage-databases-data/products/spanner.md)

</details>

[Back to index](#index)

---

### Q36

> LedgerNest runs a stateful transaction-processing service on Google Kubernetes Engine (GKE). The service is deployed as a single-replica Deployment because multiple replicas could process the same transaction concurrently. During end-of-month traffic spikes, the container becomes unstable because its configured CPU request is insufficient. LedgerNest wants GKE to adjust the CPU resources assigned to the workload as demand changes while avoiding unnecessary resource allocation during quieter periods. What should LedgerNest do?  

- **A.** Enable node pool auto-creation on the GKE cluster.
- **B.** Configure a Vertical Pod Autoscaler for the Deployment.
- **C.** Configure a Horizontal Pod Autoscaler for the Deployment.
- **D.** Enable cluster autoscaling for the GKE cluster.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because node pool auto-creation, formerly commonly described as node auto-provisioning, is an infrastructure-level scaling feature that creates new node pools when pending Pods have resource or hardware requirements that existing node pools cannot satisfy. It does not modify the CPU request or limit configured for an existing container. If the Deployment continues to request too little CPU, Kubernetes might consider the Pod successfully scheduled even though the application is CPU-constrained during peak periods. Node pool auto-creation therefore cannot identify that the container needs a larger CPU allocation or vertically resize the application. It can complement workload autoscaling when the cluster lacks suitable node capacity, but it does not solve the workload-sizing problem described here.

**B is correct** because a Vertical Pod Autoscaler analyzes the workload’s CPU and memory consumption and recommends or automatically adjusts its container resource requests. When the application requires more CPU, the Vertical Pod Autoscaler can increase the CPU request so that Kubernetes schedules the Pod with sufficient resources. When sustained resource requirements decrease, it can reduce an oversized request, improving bin-packing and cost efficiency during off-peak periods. Vertical scaling is particularly appropriate because the application cannot add replicas and must instead provide more resources to its single Pod. Depending on the GKE version and Vertical Pod Autoscaler update mode, applying a new recommendation might require evicting and recreating the Pod. Because this workload has only one replica, LedgerNest should account for a possible interruption by using an appropriate maintenance strategy, graceful shutdown behavior, and persistent storage. Nevertheless, among the available choices, Vertical Pod Autoscaling is the mechanism designed to adjust the CPU resources of the existing single-replica workload.

**C is incorrect** because a Horizontal Pod Autoscaler responds to metrics such as CPU utilization by increasing or decreasing the number of Pod replicas. The application is explicitly restricted to one replica, so horizontal scaling cannot provide additional processing capacity without violating the application’s design requirement. Configuring both the minimum and maximum replica counts as one would prevent the Horizontal Pod Autoscaler from taking meaningful action. A Horizontal Pod Autoscaler also does not directly increase the CPU request assigned to the existing Pod. It is appropriate for stateless or safely replicated workloads that can distribute demand across multiple Pods, but not for this single-replica application.

**D is incorrect** because GKE cluster autoscaling changes the number of nodes in a node pool according to the resource requests of Pods that need to be scheduled. It does not adjust the CPU request of an already running container based on the container’s actual peak utilization. Because the application’s manifest currently requests too little CPU, the cluster autoscaler might see no unschedulable Pod and therefore have no reason to add a node. Adding nodes would also not guarantee that the existing Pod receives more CPU because the Pod remains governed by its configured resource request and limit. Cluster autoscaling can provide supporting node capacity after a Vertical Pod Autoscaler increases a Pod’s request, but cluster autoscaling by itself does not solve the incorrect workload resource configuration.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/verticalpodautoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/verticalpodautoscaler)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/horizontalpodautoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/horizontalpodautoscaler)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler)

**Related notes:** [HPA, VPA, and cluster autoscaler](../03-compute-containers/products/hpa-vpa-and-cluster-autoscaler.md)

</details>

[Back to index](#index)

---

### Q37

> NimbusSketch, a collaborative design platform, allows developers to create experimental resources in multiple Google Cloud sandbox projects. The organization has allocated a combined monthly testing budget of $1,250 and wants the appropriate billing team notified when spending reaches 85% of that amount. The solution should require minimal ongoing administration. What should NimbusSketch do?  

- **A.** Create a dedicated Cloud Billing account for the sandbox projects, attach a payment card with a $1,250 transaction limit, and link every sandbox project to that account.
- **B.** Place all sandbox projects in a Google Cloud Folder, create a $1,250 Cloud Billing budget scoped to that Folder, and configure an 85% actual-spend threshold that emails Billing Account Administrators and Billing Account Users.
- **C.** Create an email reminding developers to review their spending, deploy a Cloud Run function that sends the message to project owners, and invoke the function daily with Cloud Scheduler in every sandbox project.
- **D.** Export Cloud Billing data to BigQuery, create a dashboard showing the costs of the sandbox projects, and grant all developers access to the dashboard.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because creating a separate Cloud Billing account could help isolate the sandbox projects’ costs, but attaching a payment card with a transaction or credit limit is not a dependable Google Cloud cost-notification mechanism. Google Cloud does not use the card’s limit as a Cloud Billing budget threshold, and a declined payment could occur only after charges have already accumulated. This approach also does not automatically send an alert when spending approaches the planned amount. A dedicated billing account could still be combined with a Cloud Billing budget, but the option does not configure one, so it fails the notification requirement.

**B is correct** because Cloud Billing budgets can be scoped to one or more organizations, folders, projects, services, or labeled resources associated with a Cloud Billing account. Placing the sandbox projects in a Folder provides a centralized resource hierarchy boundary, allowing one budget to monitor their combined costs. Setting the budget amount to $1,250 and adding an 85% actual-spend threshold automatically generates an email when tracked costs cross $1,062.50. Role-based notifications can be sent to Billing Account Administrators and Billing Account Users, so the organization does not need to build or maintain custom scheduling, data-processing, or notification code. A Cloud Billing budget provides monitoring and notifications rather than a strict spending cap, which is appropriate because the requirement is to notify the team as the budget is approached.

**C is incorrect** because sending a fixed daily reminder does not evaluate actual Cloud Billing costs or determine whether spending has reached 85% of the budget. Project owners would receive messages regardless of whether spending was low, near the limit, or already above it. Deploying and maintaining a Cloud Run function and Cloud Scheduler job in every sandbox project would also introduce unnecessary operational overhead, duplicated resources, additional permissions, and possible execution costs. Google Cloud already provides native budget thresholds and automated email notifications, making this custom solution unnecessarily complex and less accurate.

**D is incorrect** because exporting Cloud Billing data to BigQuery is useful for detailed cost analysis, historical reporting, cost allocation, and dashboard creation, but a dashboard is passive. Engineers must open and review it to discover that spending is approaching the budget. This option does not configure an automated threshold-based notification. It also requires administration of the billing export, BigQuery dataset, queries, dashboard, and access permissions. BigQuery billing export could supplement a cost-management solution, but it does not replace a Cloud Billing budget alert when the primary requirement is automatic notification.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/budgets](https://docs.cloud.google.com/billing/docs/how-to/budgets)
- [docs.cloud.google.com/billing/docs/how-to/budgets-notification-recipients](https://docs.cloud.google.com/billing/docs/how-to/budgets-notification-recipients)
- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery)

**Related notes:** [Cloud Billing](../07-operations-cost/products/cloud-billing.md)

</details>

[Back to index](#index)

---

### Q38

> BrightCart operates an online marketplace with several services running across multiple Google Cloud projects. The finance team needs granular cost and usage analysis and wants a single dashboard containing tables, time-series charts, and category-based visualizations. Which solution should the cloud administrator implement?  

- **A.** Open the Cloud Billing cost breakdown report and use its built-in filters to create all required visualizations.
- **B.** Enable detailed Cloud Billing data export to BigQuery and connect Looker Studio to the exported dataset.
- **C.** Query resource metrics in Cloud Monitoring and create Cloud Monitoring dashboards for cost analysis.
- **D.** Export Cloud Monitoring metrics to BigQuery and connect Looker to the exported monitoring data.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because the Cloud Billing cost breakdown report is a predefined report designed primarily to explain how usage charges, negotiated pricing, credits, discounts, taxes, and adjustments contribute to the final cost. Its filters can narrow the displayed information by attributes such as project, service, or location, but it does not provide the flexible data-modeling and dashboard-authoring capabilities required for detailed analysis with several independently configured visualization types on the same dashboard. It is useful for reviewing summarized billing components and savings, but it is not the best solution for building a customized cost analytics dashboard.

**B is correct** because Cloud Billing export automatically sends detailed billing information to a BigQuery dataset. Depending on the enabled export types, the dataset can contain project, service, SKU, resource, location, usage, cost, credit, pricing, and label information. Analysts can use SQL in BigQuery to aggregate costs, allocate shared expenses, identify trends, compare projects, examine individual resources, or create reusable views. Looker Studio can connect directly to BigQuery and display the resulting data through multiple components on the same report, including scorecards, tables, pivot tables, bar charts, pie charts, and time-series charts. This combination provides both the detailed cost data and the flexible visualization functionality required by BrightCart.

**C is incorrect** because Cloud Monitoring is intended primarily for operational telemetry such as resource utilization, request counts, latency, error rates, uptime, and application performance. Its dashboards visualize time-series metrics and observability data, but Cloud Monitoring does not serve as the detailed Cloud Billing cost database. Querying monitoring metrics would not provide the comprehensive billing records, SKU-level costs, credits, discounts, and invoice-related fields needed for granular financial analysis. Cloud Monitoring dashboards are therefore appropriate for workload health and performance analysis, not detailed cloud cost analysis.

**D is incorrect** because exporting Cloud Monitoring metrics does not replace Cloud Billing export and would provide operational measurements rather than authoritative billing cost records. Metrics such as CPU utilization, storage consumption, or request counts might help explain resource behavior, but they do not contain the complete calculated charges, credits, pricing adjustments, discounts, and billing-account dimensions required for accurate cost reporting. Looker can visualize data stored in BigQuery, but using the wrong source data would not meet the requirement. The appropriate source is Cloud Billing data exported directly to BigQuery, and Looker Studio provides a straightforward way to create the requested multi-visualization dashboard.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery)
- [docs.cloud.google.com/bigquery/docs/visualize-looker-studio](https://docs.cloud.google.com/bigquery/docs/visualize-looker-studio)
- [docs.cloud.google.com/billing/docs/how-to/cost-breakdown](https://docs.cloud.google.com/billing/docs/how-to/cost-breakdown)

**Related notes:** [Looker Studio](../05-storage-databases-data/products/looker-studio.md)

</details>

[Back to index](#index)

---

### Q39

> StreamForge Studios maintains a large collection of production footage on its on-premises file servers. Individual files range from 250 MB to 80 GB, and the company currently stores 180 TB of footage with little remaining capacity. StreamForge Studios needs to regularly move files that have not been modified for at least 18 months to Cloud Storage and remove successfully transferred files from the local systems. The solution must limit the effect on production network traffic and avoid unnecessary infrastructure costs. What should the company do?  

- **A.** Use Storage Transfer Service agents to transfer the selected files from the on-premises file systems to a Cloud Storage bucket.
- **B.** Order a Transfer Appliance, copy the selected files to the appliance, and return it to Google for ingestion into Cloud Storage.
- **C.** Provision Cloud Interconnect, configure private connectivity to Filestore, and copy the files from the on-premises NFS systems to Filestore.
- **D.** Create a Cloud Storage bucket, grant the required IAM permissions, and run gcloud storage commands from an on-premises server to copy the files directly.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Storage Transfer Service is designed for large-scale, managed transfers from on-premises file systems to Cloud Storage. StreamForge Studios can deploy transfer agents close to the source file systems, group those agents in an agent pool, and configure the transfer job to move files into the required Cloud Storage bucket. Storage Transfer Service supports modification-time filters, so the company can select only files that have not been modified for at least 18 months instead of transferring the complete 180 TB dataset. It can also delete source files after they have been transferred successfully, which helps release on-premises capacity while reducing the risk that an unsuccessful transfer causes premature deletion. Most importantly, the company can apply a bandwidth limit to the agent pool. This prevents the migration from consuming all available network capacity and interfering with active video production workloads. Transfer jobs can be scheduled and repeated, making the service suitable not only for the initial migration but also for continuously archiving files as they become old enough. The destination bucket can additionally use an appropriate Cloud Storage class, such as Coldline or Archive storage, based on the expected retrieval frequency and retention period. This provides a scalable solution without purchasing dedicated connectivity or repeatedly handling physical appliances.

**B is incorrect** because Transfer Appliance is primarily intended for offline migration when transferring a large dataset over the available network would take too long or would be impractical. It can reduce wide-area network consumption because data is copied locally to a physical appliance and shipped to Google. However, this scenario requires a controlled and potentially recurring process that identifies files based on their modification age, transfers them, and frees local capacity as new files are created. Transfer Appliance introduces appliance ordering, delivery, local loading, shipping, ingestion, and verification steps each time another migration is required. It also has appliance usage and shipping costs and does not provide the same straightforward recurring-job automation, modification-time filtering, and agent-pool bandwidth controls as Storage Transfer Service. Transfer Appliance could be considered if StreamForge Studios had extremely limited or unreliable network connectivity, but the question does not state that an online transfer is impossible. The requirement to control bandwidth is directly addressed by Storage Transfer Service bandwidth limits, so an offline appliance is not the best overall solution.

**C is incorrect** because Filestore is a managed NFS file storage service, not the required Cloud Storage destination. Moving the footage to Filestore would relocate the files to another file system but would not satisfy the explicit requirement to archive them in Cloud Storage. Provisioning Cloud Interconnect would also add connectivity setup, capacity planning, networking configuration, and ongoing port and attachment costs. Dedicated connectivity may be appropriate for sustained hybrid-cloud traffic with predictable high throughput, but establishing it solely for an archival migration would add unnecessary infrastructure and expense. Filestore is generally intended for applications that require shared file-system semantics and NFS access, whereas old, infrequently accessed video objects are better suited to scalable Cloud Storage. This option therefore uses both the wrong storage service and a more expensive connectivity architecture than the scenario requires.

**D is incorrect** because gcloud storage commands can copy or synchronize files from a local file system to a Cloud Storage bucket, and IAM permissions can authorize the uploads. However, manually operating command-line transfers is not the best approach for a managed 180 TB migration that must be filtered by file age, repeated over time, monitored centrally, and constrained to a defined amount of network bandwidth. The company would need to create and maintain its own scripts for discovering eligible files, handling retries, recording completed transfers, verifying results, controlling aggregate bandwidth across multiple workers, scheduling future runs, and safely deleting source files. A direct command-line process also places more operational responsibility on administrators and can become difficult to manage across several source file systems. Storage Transfer Service provides managed transfer jobs, scalable agents, integrity handling, scheduling, modification-time filters, source-deletion options, monitoring, and agent-pool bandwidth limits. Therefore, direct gcloud storage commands are technically capable of copying files but are less reliable and operationally efficient for this requirement.

**Reference links**

- [docs.cloud.google.com/storage-transfer/docs/create-transfers/agent-based/file-system-to-cloud-storage](https://docs.cloud.google.com/storage-transfer/docs/create-transfers/agent-based/file-system-to-cloud-storage)
- [docs.cloud.google.com/storage-transfer/docs/filter-by-last-modified](https://docs.cloud.google.com/storage-transfer/docs/filter-by-last-modified)
- [docs.cloud.google.com/storage-transfer/docs/obtaining-bandwidth-on-prem](https://docs.cloud.google.com/storage-transfer/docs/obtaining-bandwidth-on-prem)

**Related notes:** [Storage Transfer Service, Transfer Appliance, and BigQuery Data Transfer Service](../05-storage-databases-data/products/storage-transfer-service-transfer-appliance-and-bigquery-dat.md)

</details>

[Back to index](#index)

---

### Q40

> NexaFleet manages Linux Compute Engine instances across dozens of Google Cloud projects. The security team wants administrators’ SSH access to be controlled centrally through corporate identities, revoked automatically when permissions change, and recorded for compliance reviews. The company also wants to avoid manually distributing and removing SSH keys. What should NexaFleet do?  

- **A.** Attach a service account to every instance and use the service account to distribute shared SSH keys.
- **B.** Store administrator SSH keys in project metadata and use the metadata entries to control sudo privileges.
- **C.** Enforce the Require OS Login organization policy across the Google Cloud resource hierarchy.
- **D.** Enable OS Login with two-factor authentication for users in the company’s domain.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a service account attached to a Compute Engine instance is primarily a workload identity that applications on the instance use to authenticate to Google Cloud APIs. It is not an appropriate centralized identity mechanism for granting human administrators SSH access. Giving a service account permission to modify project or instance metadata and using it to distribute shared SSH keys would retain the administrative burden and security risks associated with manual key management. Administrators would still need processes to create, distribute, rotate, track, and remove keys. Shared keys also make it more difficult to determine which individual accessed a VM, weakening accountability and audit compliance. Compromising the service account or shared private key could potentially expose many instances. OS Login instead maps each administrator’s Google identity to a Linux account and evaluates that person’s IAM permissions whenever a login is attempted.

**B is incorrect** because metadata-based SSH keys require administrators to manage public keys in project or instance metadata. Project-level keys can grant access to every compatible VM in the project unless individual instances block project-wide SSH keys, which can unintentionally provide broader access than required. Metadata keys also require manual lifecycle management, including adding, rotating, expiring, and removing credentials. Furthermore, metadata SSH keys do not directly provide centralized management of sudo privileges. With OS Login, the roles/compute.osLogin role grants login access without sudo permissions, while roles/compute.osAdminLogin grants login access with sudo permissions. This allows SSH and administrative privileges to be controlled through IAM rather than through metadata keys and manually maintained Linux account configurations.

**C is correct** because OS Login integrates Compute Engine SSH access with Google Cloud IAM. Administrators can receive roles/compute.osLogin for standard operating-system access or roles/compute.osAdminLogin when sudo access is required. IAM permissions are evaluated during login, so removing a user’s applicable IAM role automatically revokes that user’s access without requiring an administrator to locate and delete SSH keys from every project or VM. Enforcing the Require OS Login organization policy creates a company-wide standard and prevents users from disabling OS Login through project, zonal, or instance metadata. Applying the policy at the organization or appropriate folder level also allows descendant projects to inherit the requirement, reducing configuration work and preventing inconsistent project-level implementations. When OS Login is enabled, Compute Engine ignores metadata-based SSH keys, eliminating much of the risk and operational overhead associated with manually managed keys. OS Login also integrates with audit logging, enabling the security team to review relevant authentication, authorization, and SSH-key management activities for compliance purposes.

**D is incorrect** because OS Login with two-factor authentication adds an important authentication layer, but enabling two-factor authentication for domain users does not by itself establish or enforce a company-wide SSH access standard across all Google Cloud projects and VM instances. The company would still need to enable OS Login on the relevant projects or instances and prevent administrators from disabling it. Two-factor authentication addresses how users prove their identity during SSH authentication, whereas the organization policy addresses consistent enforcement of OS Login throughout the resource hierarchy. OS Login with two-factor authentication can be added after OS Login is enforced when stronger authentication is required, but it does not replace the Require OS Login organization policy and is not the most complete answer to the stated management and compliance requirements.

**Reference links**

- [docs.cloud.google.com/compute/docs/oslogin/manage-oslogin-in-an-org](https://docs.cloud.google.com/compute/docs/oslogin/manage-oslogin-in-an-org)
- [docs.cloud.google.com/compute/docs/oslogin](https://docs.cloud.google.com/compute/docs/oslogin)
- [docs.cloud.google.com/compute/docs/oslogin/view-audit-logs](https://docs.cloud.google.com/compute/docs/oslogin/view-audit-logs)

**Related notes:** [OS Login](../02-identity-security/products/os-login.md) · [Organization Policy Service](../02-identity-security/products/organization-policy-service.md)

</details>

[Back to index](#index)

---

### Q41

> HarborCart, an online retail company, uses Terraform to manage its Google Cloud infrastructure. A developer asks Gemini CLI to generate a configuration change that exposes a new customer service through a public endpoint. The organization requires every infrastructure change to pass technical review and automated checks before deployment. Which approach provides the quickest compliant path to production?  

- **A.** Apply the Terraform configuration immediately because code produced by Gemini CLI is automatically approved.
- **B.** Push the generated configuration directly to the default branch and turn off Terraform plan checks.
- **C.** Review the generated configuration, run formatting and validation checks, examine the Terraform plan, and submit the change through the standard code-review pipeline.
- **D.** Create the public endpoint manually in the Google Cloud console instead of managing it with Terraform.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Terraform code generated by Gemini CLI is a proposed implementation and is not automatically trusted, tested, secure, or approved for production use. Generative AI can accelerate authoring, but a developer remains responsible for checking resource settings, network exposure, IAM permissions, variable values, dependencies, and compliance with organizational policies. Immediately running terraform apply would bypass the required review and testing controls. This is especially risky for a public endpoint because an incorrect firewall rule, load balancer setting, IP configuration, or IAM policy could unintentionally expose services or data.

**B is incorrect** because committing directly to the default branch and disabling plan checks removes important engineering safeguards. The Terraform plan shows which resources Terraform intends to create, modify, replace, or destroy before any deployment occurs. Skipping this step can allow unexpected infrastructure changes to reach production. Directly updating the protected branch also prevents peers and automated systems from reviewing the proposed configuration. Although this approach might appear faster, it violates the stated company policy and increases the risk of outages, security vulnerabilities, configuration drift, and difficult rollbacks.

**C is correct** because it combines Gemini CLI’s development speed with the organization’s established infrastructure governance. The developer should first inspect the generated Terraform code to confirm that the public endpoint, networking rules, IAM permissions, variables, and resource dependencies match the intended design. Running terraform fmt produces consistently formatted configuration, while terraform validate checks whether the configuration is syntactically valid and internally consistent. The developer should then run terraform plan and inspect the proposed resource changes without applying them. Finally, the change should be submitted through the normal pull-request or code-review pipeline, where peer review, policy validation, security checks, and automated tests can run before an approved deployment. This is the fastest option that preserves reviewability, repeatability, auditability, and separation between code generation and production authorization.

**D is incorrect** because manually creating resources in the Google Cloud console bypasses the Terraform workflow and creates a difference between the deployed environment and the infrastructure configuration stored in source control. This configuration drift makes future plans less predictable and can cause Terraform to modify, replace, or remove manually created resources during a later deployment. Console-created resources are also harder to reproduce consistently across environments and may not pass the organization’s automated review and testing pipeline. The generated Terraform should be reviewed and improved rather than replaced with unmanaged manual changes.

**Reference links**

- geminicli.com/docs/reference/tools/
- [docs.cloud.google.com/docs/terraform/best-practices/operations](https://docs.cloud.google.com/docs/terraform/best-practices/operations)
- [developer.hashicorp.com/terraform/cli/commands/validate](https://developer.hashicorp.com/terraform/cli/commands/validate)

**Related notes:** [Gemini CLI](../08-iac-platform-ai/products/gemini-cli.md)

</details>

[Back to index](#index)

---

### Q42

> BlueOrbit Health is planning a patient scheduling application with a web interface, an API service, and a managed database. The platform engineering team must review the proposed architecture, publish it as an approved reusable template, and allow development teams to deploy separate instances into their own Google Cloud projects. Because the application has not been deployed, no operational data is available for troubleshooting. Which Google Cloud tool should the team use?  

- **A.** Cloud Hub
- **B.** Gemini Cloud Assist investigations
- **C.** VPC Flow Logs
- **D.** Application Design Center

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Cloud Hub provides a centralized, application-focused view of operational information for Google Cloud applications and resources. It helps operations and SRE teams examine health, incidents, costs, utilization, alerts, and other insights associated with deployed resources. It is not primarily an architecture-design workspace for assembling frontend, backend, and database components or publishing those designs as reusable deployment templates. Because the application does not yet exist, Cloud Hub would also have no running resources or operational signals to summarize.

**B is incorrect** because Gemini Cloud Assist investigations is intended for diagnosing problems in existing applications and infrastructure. It performs root-cause analysis by evaluating available operational information such as logs, metrics, configurations, alerts, and recent changes. In this scenario, the team is designing a new application rather than investigating a production incident, and the application has not produced any telemetry. Therefore, an investigation workflow cannot satisfy the requirements for visual architecture design, platform review, reusable template publication, and repeated deployment.

**C is incorrect** because VPC Flow Logs records sampled network-flow information for traffic handled by supported network interfaces. The resulting telemetry can help teams analyze network activity, troubleshoot connectivity, monitor traffic patterns, and support security investigations after resources are running. VPC Flow Logs does not provide an application-design canvas, architectural review workflow, reusable application templates, generated infrastructure as code, or repeated deployment into different projects. It is an observability feature rather than an application architecture and deployment tool.

**D is correct** because Application Design Center is designed for creating, reviewing, standardizing, and deploying application architectures on Google Cloud. The development team can model the frontend, backend, database, and their connections, while the platform team can review the design and incorporate organizational standards. The approved design can then be published as a reusable application template. Development teams can customize permitted properties and repeatedly deploy applications from that template into separate projects. Application Design Center can also generate Terraform configuration for the application, making it the best fit for a new application that is still in the design and deployment-planning stage.

**Reference links**

- [docs.cloud.google.com/application-design-center/docs/overview](https://docs.cloud.google.com/application-design-center/docs/overview)
- [docs.cloud.google.com/application-design-center/docs/design-application-templates](https://docs.cloud.google.com/application-design-center/docs/design-application-templates)
- [docs.cloud.google.com/application-design-center/docs/quickstart-create-template](https://docs.cloud.google.com/application-design-center/docs/quickstart-create-template)

**Related notes:** [Application Design Center](../08-iac-platform-ai/products/application-design-center.md)

</details>

[Back to index](#index)

---

### Q43

> LumenFleet Systems wants to deploy a Compute Engine VM for a new route-planning service. The destination Google Cloud project, lumenfleet-routing-prod, has not been created yet. You want to complete the deployment by using the Google Cloud CLI. What should you do?  

- **A.** Use the Google Cloud CLI to create lumenfleet-routing-prod, enable the Compute Engine API in the project, and then create the VM by specifying lumenfleet-routing-prod.
- **B.** Enable the Compute Engine API in the Google Cloud console, use the Google Cloud CLI to create the VM, and specify the nonexistent lumenfleet-routing-prod project with the --project flag.
- **C.** Run the Google Cloud CLI command to create the VM with the --project flag set to lumenfleet-routing-prod, and approve the prompt to enable the Compute Engine API.
- **D.** Enable the Compute Engine API in the Google Cloud console, open the Compute Engine VM creation page, and select an option to create the VM in a new project.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a Compute Engine VM must belong to an existing Google Cloud project. You must first create lumenfleet-routing-prod by using a command such as gcloud projects create. After completing required project setup, including linking an active billing account when necessary, you must enable the Compute Engine API for that project. You can then run gcloud compute instances create and use the --project flag to explicitly create the VM in lumenfleet-routing-prod. This option follows the required resource-creation order: create the project, enable the service, and create the resource.

**B is incorrect** because the Compute Engine API is enabled within a specific existing project. You cannot enable the API for lumenfleet-routing-prod before that project has been created. In addition, the --project flag only identifies the project in which a Google Cloud CLI command should operate; it does not create a missing project. The VM creation request would fail because the specified destination project does not exist.

**C is incorrect** because gcloud compute instances create cannot create a VM in a nonexistent project. For an existing project, the Google Cloud CLI might offer to enable a required API in some interactive situations, but it does not create the missing project as part of the VM creation command. The --project flag selects an existing project and is not a project-provisioning option. You must explicitly create the project before enabling the Compute Engine API and deploying the VM.

**D is incorrect** because the Compute Engine API must be enabled for an existing selected project, and the Compute Engine VM creation form does not provide a Create In A New Project option that creates a project during VM deployment. Project creation is a separate Resource Manager operation. After creating and configuring the project, you can select it in the Google Cloud console and create the VM, but the sequence described in this option is not valid.

**Reference links**

- [docs.cloud.google.com/resource-manager/docs/creating-managing-projects](https://docs.cloud.google.com/resource-manager/docs/creating-managing-projects)
- [docs.cloud.google.com/service-usage/docs/enable-disable](https://docs.cloud.google.com/service-usage/docs/enable-disable)
- [docs.cloud.google.com/sdk/gcloud/reference/compute/instances/create](https://docs.cloud.google.com/sdk/gcloud/reference/compute/instances/create)

**Related notes:** [Compute Engine](../03-compute-containers/products/compute-engine.md)

</details>

[Back to index](#index)

---

### Q44

> SkyRoute Logistics operates applications across Google Cloud projects Fleet-Core, Dispatch-Services, and Analytics-Hub. The company needs one Cloud Monitoring view for CPU, memory, and disk metrics from resources in all three projects. The Ops Agent is installed where guest operating system metrics are required. What should the operations team do?  

- **A.** Enable the Cloud Monitoring API and share separate charts created in Fleet-Core, Dispatch-Services, and Analytics-Hub.
- **B.** Enable the Cloud Monitoring API and grant the Monitoring Viewer role to the other projects.
- **C.** Enable the Cloud Monitoring API and open each project’s default dashboards one after another.
- **D.** Enable the Cloud Monitoring API, use Fleet-Core as the scoping project, and add Dispatch-Services and Analytics-Hub to its metrics scope.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because sharing charts from three independent projects does not create a unified monitoring environment. Each chart remains associated with the project and metrics scope in which it was created. Although shared charts might help users access specific visualizations, they do not automatically combine CPU, memory, and disk time-series data from all three projects into one centrally managed dashboard, alerting configuration, or Metrics Explorer view.

**B is incorrect** because the Monitoring Viewer role, roles/monitoring.viewer, grants a principal permission to view monitoring information, but it does not add one project’s metric data to another project’s monitoring scope. IAM roles control who can access resources; metrics scopes control which projects’ time-series data is visible from a scoping project. Granting the role alone would therefore not provide the required consolidated view across all three projects.

**C is incorrect** because opening the projects’ default dashboards sequentially requires operators to switch between projects. This does not provide a single pane of glass, and it makes cross-project comparisons, consolidated dashboards, and centralized alerting more difficult. Default dashboards are automatically generated for supported resources, but their visible data is determined by the selected scoping project and its metrics scope.

**D is correct** because a Cloud Monitoring metrics scope determines which projects’ time-series data can be viewed and monitored from a scoping project. By using Fleet-Core as the scoping project and adding Dispatch-Services and Analytics-Hub to its metrics scope, the operations team can create dashboards, charts, and alerting policies that use metrics from all three projects. CPU and infrastructure disk metrics are generally available from Google Cloud services automatically, while guest memory usage and guest file-system utilization typically require the Ops Agent. The term Workspace was used in older Cloud Monitoring designs, but the current model uses a scoping project that hosts a multi-project metrics scope.

**Reference links**

- [docs.cloud.google.com/monitoring/settings/multiple-projects](https://docs.cloud.google.com/monitoring/settings/multiple-projects)
- [docs.cloud.google.com/monitoring/settings](https://docs.cloud.google.com/monitoring/settings)
- [docs.cloud.google.com/monitoring/api/metrics_opsagent](https://docs.cloud.google.com/monitoring/api/metrics_opsagent)

**Related notes:** [Cloud Monitoring](../07-operations-cost/products/cloud-monitoring.md)

</details>

[Back to index](#index)

---

### Q45

> BrightPath Retail operates a sales forecasting portal that queries BigQuery. An external research agency has 65 consultants who require access for a three-month project. The consultants already sign in through the agency’s SAML 2.0-compatible identity provider. BrightPath Retail does not want to provision or maintain Cloud Identity accounts, and its audit records must identify the individual consultant who performed each action. Which configuration should BrightPath Retail use?  

- **A.** Create one service account key and share it with all agency consultants
- **B.** Configure Workload Identity Federation for the consultants’ workstations
- **C.** Configure Workforce Identity Federation with the agency’s identity provider
- **D.** Create one generic agency user, add it to a Google Group, and share its credentials with the consultants

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a service account represents an application or workload rather than an individual human user. Sharing one service account key among all consultants would cause their BigQuery requests to appear as actions performed by the same service account, preventing reliable attribution to a specific consultant. It would also introduce a long-lived credential that could be copied, leaked, or retained after the engagement ends. Revoking one consultant’s access would generally require rotating the shared key and redistributing the replacement to everyone. Google Cloud recommends avoiding service account keys when more secure, short-lived authentication methods are available.

**B is incorrect** because Workload Identity Federation is intended primarily for non-Google Cloud workloads, such as applications running on-premises, in another cloud provider, or in external CI/CD systems. It enables workloads to exchange credentials issued by an external identity provider for short-lived Google Cloud credentials without storing service account keys. The consultants are human workforce users, and treating their laptops as workloads would authenticate machines or workload identities rather than provide the appropriate user-focused sign-in and authorization model. The similar names are important: Workload Identity Federation is for workloads and machine identities, whereas Workforce Identity Federation is for employees, contractors, partners, and other human users.

**C is correct** because Workforce Identity Federation is specifically designed to let external human users access Google Cloud resources by authenticating through an existing external identity provider. BrightPath Retail can create a workforce identity pool and configure a SAML workforce identity pool provider that trusts assertions from the agency’s identity provider. Attributes from the SAML assertion, including a stable and unique user identifier, can be mapped to workforce identity attributes and used in IAM allow policies. Each consultant signs in with an individual agency identity and receives short-lived Google Cloud credentials, so BrightPath Retail does not need to create Cloud Identity accounts or distribute persistent keys. Because each federated principal remains distinct, BigQuery access and relevant audit activity can be associated with the individual consultant. IAM access can be granted to individual workforce principals, mapped groups, or attribute-based principal sets, allowing the organization to provide only the required dataset permissions and remove access centrally when the project ends.

**D is incorrect** because a single generic user account would make every consultant appear to Google Cloud as the same principal. This would defeat the requirement that actions remain attributable to individual human users and would make investigations, access reviews, and revocation more difficult. Sharing the account’s credentials could also expose multifactor authentication information or recovery methods and would create a significant security risk. Although Google Groups are useful for assigning IAM roles to collections of identities, placing one shared generic account in a group does not create separate identities for the consultants. A Google Group should contain individually identifiable principals where applicable, or Workforce Identity Federation can map external identity-provider groups and attributes without requiring one shared Google-managed account.

**Reference links**

- [docs.cloud.google.com/iam/docs/workforce-identity-federation](https://docs.cloud.google.com/iam/docs/workforce-identity-federation)
- [docs.cloud.google.com/iam/docs/workload-identity-federation](https://docs.cloud.google.com/iam/docs/workload-identity-federation)
- [docs.cloud.google.com/iam/docs/best-practices-for-managing-service-account-keys](https://docs.cloud.google.com/iam/docs/best-practices-for-managing-service-account-keys)

**Related notes:** [Workload Identity Federation and Workforce Identity Federation](../02-identity-security/products/workload-identity-federation-and-workforce-identity-federati.md)

</details>

[Back to index](#index)

---

### Q46

Choose 2.

> Northstar Analytics uses a GitHub Actions pipeline to publish application updates to a Cloud Run service. The company’s security standards prohibit uploading persistent Google Cloud credentials to external source-control platforms. Each workflow run must authenticate with GitHub’s OIDC token and obtain temporary credentials for a deployment identity that has only the required permissions. Which two configurations should Northstar Analytics implement? (Choose two.)  

- **A.** Configure a workload identity pool and an OIDC provider that trusts GitHub Actions, maps relevant token claims, and restricts access to the approved repository.
- **B.** Generate a user-managed key for the deployment service account and save the JSON key as an encrypted GitHub Actions secret.
- **C.** Allow the approved workload identity pool principal to impersonate a least-privileged service account used for Cloud Run deployments.
- **D.** Configure Workforce Identity Federation and register the GitHub Actions workflow as an external employee identity.
- **E.** Add an allUsers IAM binding that grants the Owner role to the GitHub repository.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A, C

**Explanation**

**A is correct** because Workload Identity Federation enables a workload running outside Google Cloud, including a GitHub Actions workflow, to authenticate by presenting an OIDC token issued by a trusted external identity provider. Northstar Analytics must create a workload identity pool and an OIDC workload identity pool provider that trusts GitHub’s token issuer. The provider maps GitHub OIDC claims, such as the repository owner, repository name, branch, tag, environment, or workflow identity, to Google Cloud attributes. An attribute condition should restrict authentication to the intended GitHub organization and repository so that unrelated repositories using the same public GitHub OIDC issuer cannot authenticate. Google Cloud can then exchange the GitHub OIDC token for short-lived federated credentials without requiring a stored service account key.

**B is incorrect** because a user-managed service account key is a persistent private credential. Encrypting the key as a GitHub secret reduces casual exposure but does not eliminate the security risks associated with creating, distributing, rotating, and potentially leaking a long-lived credential. Anyone who obtains the key can use it outside the intended GitHub Actions workflow until the key is disabled or deleted. This option also directly violates the requirement that no service account keys be stored in GitHub. Workload Identity Federation is the preferred approach because it establishes a trust relationship with GitHub’s OIDC issuer and produces temporary credentials for each authorized workflow execution.

**C is correct** because the GitHub workflow needs authorization to act as the deployment service account after its external identity has been authenticated. Northstar Analytics should grant the appropriate federated principal or principal set the Workload Identity User role, roles/iam.workloadIdentityUser, on the deployment service account. This permission allows only the approved GitHub workload identity to impersonate that service account and obtain short-lived Google Cloud credentials. The deployment service account should separately receive only the permissions required to deploy the Cloud Run service, rather than broad project-level privileges. For example, its required permissions might include the appropriate Cloud Run deployment role, access to the container image, and permission to act as the Cloud Run runtime service account. Separating the federated GitHub identity from the deployment service account also provides centralized control over authorization and supports the principle of least privilege.

**D is incorrect** because Workforce Identity Federation is designed for human users, such as employees, contractors, partners, and other members of an organization’s workforce who authenticate through an external identity provider. A GitHub Actions workflow is a machine workload rather than a human user. Workload Identity Federation is the appropriate service for federating an OIDC identity issued to a CI/CD pipeline. Registering the workflow through Workforce Identity Federation would apply the wrong identity model and would not represent the intended workload-to-service-account authentication pattern.

**E is incorrect** because allUsers is a special public principal that represents any authenticated or unauthenticated entity on the internet, not a specific GitHub repository. Granting the Owner role to allUsers would expose the project to unrestricted public administrative access and would violate the principle of least privilege. IAM does not treat a GitHub repository as a Google Cloud principal merely because an allUsers binding exists. The repository’s workflow must first be authenticated as a federated workload identity through a workload identity pool, and only that restricted principal should be authorized to impersonate the deployment service account.

**Reference links**

- [docs.cloud.google.com/iam/docs/workload-identity-federation-with-deployment-pipelines](https://docs.cloud.google.com/iam/docs/workload-identity-federation-with-deployment-pipelines)
- [docs.cloud.google.com/iam/docs/best-practices-for-using-service-accounts-in-deployment-pipelines](https://docs.cloud.google.com/iam/docs/best-practices-for-using-service-accounts-in-deployment-pipelines)
- github.com/google-github-actions/auth

**Related notes:** [Workload Identity Federation and Workforce Identity Federation](../02-identity-security/products/workload-identity-federation-and-workforce-identity-federati.md)

</details>

[Back to index](#index)

---

### Q47

> SilverLine Commerce uses Workforce Identity Federation to provide external incident-response specialists with access to Google Cloud. The specialists’ external identity provider issues a claim named team, and only users whose team value is operations should be able to view logs in the incident-management project. SilverLine Commerce wants access permissions to update automatically when the identity provider changes a user’s team assignment. What should the company do?  

- **A.** Generate a service account key for the operations team and replace the key every six weeks.
- **B.** Map the external team claim to a custom attribute in the workforce identity pool provider and grant the Logs Viewer role to the principal set whose attribute value is operations.
- **C.** Grant roles/logging.viewer to allAuthenticatedUsers on the incident-management project.
- **D.** Create individual Google accounts for every external specialist and manually maintain their IAM role assignments.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because a shared service account key would authenticate all specialists as the same service account instead of preserving their individual workforce identities. This would reduce accountability in audit logs and make it difficult to determine which person viewed or accessed log data. Rotating the key periodically would not solve the underlying problems of shared identity, persistent credentials, or manual access management. It would also prevent access from automatically following changes made in the external identity provider. Workforce Identity Federation is designed to avoid service account keys and use short-lived credentials based on identities and attributes asserted by the trusted external provider.

**B is correct** because a workforce identity pool provider can map claims supplied by the external identity provider to Google Cloud attributes. SilverLine Commerce can map the external team claim to a custom attribute such as attribute.team and then create an IAM binding for a workforce principal set representing identities whose attribute.team value is operations. The company can grant roles/logging.viewer to that principal set on the incident-management project. When a specialist authenticates, Google Cloud evaluates the current claim from the external identity provider. A user whose team claim is operations becomes a member of the matching principal set and receives the logging permission. When the identity provider changes or removes that value, the user no longer matches the principal set during subsequent authentication, so access follows the externally managed assignment without requiring the company to maintain separate Google accounts or individual IAM bindings. The provider should also map google.subject to a stable, unique identifier so activity remains attributable to each individual user.

**C is incorrect** because allAuthenticatedUsers represents any user or service account that authenticates with a Google-recognized identity, not only specialists whose external team claim equals operations. Granting roles/logging.viewer to this broad principal could expose project logs to authenticated identities outside the intended support organization. It would not evaluate the external identity provider’s team attribute and therefore would not enforce the required membership rule. Access should be granted to a narrowly defined workforce principal set based on the mapped attribute rather than to a global special principal.

**D is incorrect** because creating local Google accounts would duplicate identities already managed by the external identity provider and create unnecessary account-provisioning, deprovisioning, and permission-maintenance work. Administrators would have to manually update IAM bindings whenever specialists joined, left, or changed teams, so access would not automatically follow the external provider’s assignments. It could also result in delayed revocation or inconsistent identities. Workforce Identity Federation allows the organization to retain the external identity provider as the authoritative identity source while using mapped attributes and principal sets for scalable authorization.

**Reference links**

- [docs.cloud.google.com/iam/docs/configuring-workforce-identity-federation](https://docs.cloud.google.com/iam/docs/configuring-workforce-identity-federation)
- [docs.cloud.google.com/iam/docs/principal-identifiers](https://docs.cloud.google.com/iam/docs/principal-identifiers)
- [docs.cloud.google.com/logging/docs/access-control](https://docs.cloud.google.com/logging/docs/access-control)

**Related notes:** [Workload Identity Federation and Workforce Identity Federation](../02-identity-security/products/workload-identity-federation-and-workforce-identity-federati.md)

</details>

[Back to index](#index)

---

### Q48

> BlueHarbor Media runs a content-processing application on GKE. The application needs to upload generated media files to one Cloud Storage bucket. The team currently provides credentials by mounting a service account key from a Kubernetes Secret. The security team requires the key to be removed, wants the Kubernetes workload to authenticate through Google Cloud IAM, and needs permissions restricted to the application’s Kubernetes identity. What should the team use?  

- **A.** Workforce Identity Federation
- **B.** OS Login
- **C.** A project-wide SSH key
- **D.** Workload Identity Federation for GKE

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Workforce Identity Federation is intended for human users, such as employees, contractors, partners, and administrators, who authenticate to Google Cloud through an external identity provider. The application running in a GKE Pod is a machine workload rather than a human workforce user. Workforce Identity Federation would therefore use the wrong identity model and would not provide the native mapping between a Kubernetes ServiceAccount and Google Cloud IAM that the application requires.

**B is incorrect** because OS Login controls SSH access to Compute Engine virtual machines by using IAM identities. It helps administrators manage operating-system-level logins and SSH keys for VM instances, but it does not authenticate GKE Pods to Google Cloud APIs. Enabling OS Login would not give the application a workload identity or allow it to write objects to the Cloud Storage bucket.

**C is incorrect** because a project-wide SSH key is used to authenticate human or automated SSH sessions to Compute Engine virtual machines. It is unrelated to Google Cloud API authentication from a GKE workload. A shared project-wide SSH key would also increase credential exposure and would not provide fine-grained authorization for a specific Kubernetes namespace and Kubernetes ServiceAccount. It cannot replace the service account key used by the Cloud Storage client library.

**D is correct** because Workload Identity Federation for GKE lets GKE workloads access Google Cloud APIs without storing service account key files. The team can enable Workload Identity Federation for GKE, create a dedicated Kubernetes ServiceAccount for the application, configure the Pod to run as that Kubernetes ServiceAccount, and grant the corresponding workload identity principal only the required IAM role on the target Cloud Storage bucket. For a workload that only needs to create new objects, the team can grant roles/storage.objectCreator at the bucket level, provided that the application does not need to read, delete, or overwrite existing objects. The GKE metadata server supplies short-lived credentials to the Pod, and supported Google Cloud client libraries can discover these credentials through Application Default Credentials. The IAM principal can include the workload identity pool, Kubernetes namespace, and Kubernetes ServiceAccount name, ensuring that access belongs only to the intended application workload. This removes the downloadable key, avoids mounting sensitive JSON credentials in a Kubernetes Secret, supports automatic credential rotation, and applies least-privilege access to a single bucket.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/workload-identity](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/workload-identity)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/workload-identity](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/workload-identity)
- [docs.cloud.google.com/storage/docs/access-control/iam-roles](https://docs.cloud.google.com/storage/docs/access-control/iam-roles)

**Related notes:** [Workload Identity Federation for GKE](../02-identity-security/products/workload-identity-federation-for-gke.md)

</details>

[Back to index](#index)

---

### Q49

> SkyForge Media operates an automated release pipeline in a third-party cloud platform. The pipeline must provision resources in four Google Cloud projects. SkyForge Media requires a single federation trust configuration, keyless authentication, a different least-privileged deployment identity for each project, and logs that preserve the identity of the external pipeline. What should SkyForge Media implement?  

- **A.** Create one service account with the Owner role, generate a key for it, and reuse the key across all four projects.
- **B.** Configure Workforce Identity Federation and have the pipeline authenticate through a shared human administrator account.
- **C.** Configure Workload Identity Federation for the external pipeline and allow it to impersonate a separate deployment service account in each project.
- **D.** Store the deployment manifests in publicly writable Cloud Storage buckets so that the external pipeline can update them without authentication.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a shared service account key is a long-lived credential that must be stored, distributed, rotated, monitored, and protected against theft. Reusing the same key across multiple projects increases the potential impact of a compromise, while granting the Owner role violates least privilege by giving the pipeline broad administrative control over project resources, IAM policies, and many other services. A single shared service account also prevents the organization from cleanly separating deployment permissions by project. Workload Identity Federation is specifically designed to replace service account keys for workloads running outside Google Cloud by exchanging credentials issued by a trusted external identity provider for short-lived Google Cloud credentials.

**B is incorrect** because Workforce Identity Federation is intended for human users and groups, such as employees, partners, contractors, and administrators who access Google Cloud through an external identity provider. The caller in this scenario is an automated build workload, not a human workforce user. Using a shared human administrator account would also weaken accountability because audit records would identify the shared account rather than reliably distinguish the external pipeline identity. It would introduce excessive privileges, complicate credential management, and conflict with the requirement for separate least-privileged deployment identities in each project.

**C is correct** because Workload Identity Federation is intended for workloads running outside Google Cloud, including build systems and deployment pipelines hosted in another cloud or an external CI/CD platform. The organization can create one workload identity pool and provider that trusts identity tokens issued by the external build platform. It can then create a separate deployment service account for each Google Cloud project and grant each service account only the roles required to deploy resources in that specific project. IAM bindings can permit the validated external pipeline principal to impersonate those service accounts by using short-lived credentials, eliminating the need to generate or store service account keys. Attribute mappings and attribute conditions can restrict access to a particular repository, pipeline, environment, branch, organization, or other trusted token claim. This design centralizes the external trust relationship while maintaining project-level identity and permission separation. Cloud Audit Logs can record service account impersonation and contain information about the federated caller, providing better traceability than a shared key or shared human account.

**D is incorrect** because publicly writable Cloud Storage buckets would allow unauthenticated or broadly authorized parties to modify deployment manifests. An attacker could replace legitimate manifests with malicious infrastructure definitions, alter application configurations, introduce unauthorized resources, or disrupt deployments. Public bucket access does not establish the identity of the external build system, provide separate permissions for each project, create short-lived credentials, or produce reliable caller attribution. Deployment manifests should be protected by IAM and accessed through an authenticated workload identity rather than exposed for anonymous modification.

**Reference links**

- [docs.cloud.google.com/iam/docs/workload-identity-federation](https://docs.cloud.google.com/iam/docs/workload-identity-federation)
- [docs.cloud.google.com/iam/docs/best-practices-for-using-service-accounts-in-deployment-pipelines](https://docs.cloud.google.com/iam/docs/best-practices-for-using-service-accounts-in-deployment-pipelines)
- [docs.cloud.google.com/iam/docs/audit-logging/examples-workload-identity](https://docs.cloud.google.com/iam/docs/audit-logging/examples-workload-identity)

</details>

[Back to index](#index)

---

### Q50

> BluePeak Insurance has a governance team that must view resources across all current and future Google Cloud projects in the company’s organization. Individual project administrators must not control the team’s membership or configure the same IAM role separately in every project. What should the organization administrator do?  

- **A.** Grant the governance group the Viewer role on the organization resource.
- **B.** Grant the governance group the Owner role on a dedicated compliance project.
- **C.** Create a service account key and distribute it among the governance team members.
- **D.** Add the Viewer role for the governance group separately to every existing project and repeat the configuration periodically for new projects.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Google Cloud IAM policies follow the resource hierarchy. When the Viewer role is granted to the governance group at the organization level, the binding is inherited by folders, projects, and supported resources below the organization. This gives the group read-only access across existing projects and automatically extends the same access to future projects created within the organization. The group’s membership can remain centrally managed through the organization’s identity provider or Google Groups, so project teams do not need permission to add or remove compliance personnel. This design avoids repeated project-level bindings, provides consistent access, and meets the requirement for centralized administration.

**B is incorrect** because an IAM role granted on one project applies only to that project and its descendant resources; it does not provide access to other projects in the organization. The Owner role is also far more privileged than required because it includes broad administrative permissions rather than read-only access. A dedicated audit project can host compliance tools, logs, or reports, but granting permissions there does not automatically authorize the group to inspect resources in unrelated projects.

**C is incorrect** because service account keys are long-lived credentials intended for programmatic authentication, not for sharing among human users. Sharing a key prevents reliable individual accountability because all users appear to act as the same service account. It also creates security risks involving credential storage, distribution, rotation, and revocation. A service account key would not automatically provide organization-wide access unless IAM permissions were separately granted, and it would not solve the requirement to manage compliance membership centrally.

**D is incorrect** because assigning the Viewer role independently in every project creates repetitive administrative work and increases the likelihood of inconsistent or missing permissions. New projects would not receive access automatically, requiring administrators to continually discover them and add another binding. Project-level bindings could also be modified by project teams with sufficient IAM permissions. Granting the role at the organization level is more scalable and ensures that inherited access applies consistently to both current and future projects.

**Reference links**

- [cloud.google.com/iam/docs/resource-hierarchy-access-control](https://cloud.google.com/iam/docs/resource-hierarchy-access-control)
- [cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy](https://cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)
- [cloud.google.com/iam/docs/understanding-roles](https://cloud.google.com/iam/docs/understanding-roles)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---
