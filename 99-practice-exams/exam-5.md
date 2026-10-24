# Practice Exam 5

[Previous](exam-4.md) · [All exams](README.md) · [Next](exam-6.md)

50 questions in the original English. Open "Show answer" under each question to see the correct answer and the explanation.

## Index

| Q | Question |
|---|---|
| [Q1](#q1) | GlobeRoute is preparing a new Google Cloud project for a worldwide logistics platform. The... |
| [Q2](#q2) | NovaForge Games maintains a development project in Google Cloud. Its DevOps group must be ... |
| [Q3](#q3) | PixelHarbor operates a photo-sharing platform on a Google Kubernetes Engine cluster. A thu... |
| [Q4](#q4) | LedgerNest has developed a containerized payment-reconciliation application that must run ... |
| [Q5](#q5) | ShopPulse hosts its customer-order portal on Compute Engine virtual machines. The operatio... |
| [Q6](#q6) | DataForge Labs runs an on-premises inventory-reconciliation program composed of several co... |
| [Q7](#q7) | TrailNest operates a hiking-route application on Google Kubernetes Engine (GKE). A backend... |
| [Q8](#q8) | NimbusCart operates two Google Kubernetes Engine (GKE) clusters created with the gcloud co... |
| [Q9](#q9) | BrightForge develops a mobile application, and its engineers currently use many user-manag... |
| [Q10](#q10) | Northstar Retail operates an online ordering platform on virtual machines with separate pr... |
| [Q11](#q11) | BlueHarbor Media uses GitHub Actions to deploy a standard three-tier content platform into... |
| [Q12](#q12) | FitPulse is building a health-tracking application that will run on Google Kubernetes Engi... |
| [Q13](#q13) | CloudForge Media operates a group of Compute Engine Linux virtual machines that host its i... |
| [Q14](#q14) | StreamCart operates a real-time order-processing platform that uses several Dataflow strea... |
| [Q15](#q15) | NovaRetail is migrating its online shopping platform from its data center to Compute Engin... |
| [Q16](#q16) | BrightRoute, a logistics software company, runs several containerized services and expects... |
| [Q17](#q17) | NexaRoute operates logistics applications in its private data centers and across multiple ... |
| [Q18](#q18) | BlueHarbor Financial operates Windows-based workloads in multiple Google Cloud projects. I... |
| [Q19](#q19) | Northwind Analytics has configured an egress firewall rule to deny connections from its Co... |
| [Q20](#q20) | PulseCart operates a retail analytics platform that continuously streams transaction recor... |
| [Q21](#q21) | Northstar Health is rebuilding its internal appointment-processing platform as containeriz... |
| [Q22](#q22) | PixelForge Labs is developing a web platform that automatically creates animated product p... |
| [Q23](#q23) | ParcelPilot operates an on-premises shipment-tracking platform composed of several Python ... |
| [Q24](#q24) | BluePeak Analytics runs a reporting service on a Compute Engine virtual machine. The servi... |
| [Q25](#q25) | PayWave Retail is replacing its VM-based order settlement platform with a serverless archi... |
| [Q26](#q26) | HarborLink Logistics operates several legacy warehouse applications that exchange document... |
| [Q27](#q27) | QuickBite Delivery has built an online food-ordering platform composed of separate catalog... |
| [Q28](#q28) | AsterPeak Manufacturing is migrating its global supply-chain planning platform to Google C... |
| [Q29](#q29) | BrightCart runs its catalog, payment, and reporting applications on separate Compute Engin... |
| [Q30](#q30) | TrendScope Media runs customer-facing services on several Compute Engine instances and nee... |
| [Q31](#q31) | Northstar Analytics uses an internal deployment tool to create Linux virtual machines in C... |
| [Q32](#q32) | NovaCart, an online retail company, has created a Google Cloud project named novacart-prod... |
| [Q33](#q33) | BrightCart operates an online retail platform that uses a Google Kubernetes Engine (GKE) c... |
| [Q34](#q34) | NovaCart stores private container images in Artifact Registry for its online ordering plat... |
| [Q35](#q35) | HealthBridge Systems is moving a patient-records application from its private data center ... |
| [Q36](#q36) | Northwind Media operates Bigtable, Cloud SQL, Memorystore, and Spanner resources for sever... |
| [Q37](#q37) | PixelNest runs a Cloud Run service that displays product media stored in an existing share... |
| [Q38](#q38) | StreamLoom is developing an AI application on Gemini Enterprise Agent Platform that consum... |
| [Q39](#q39) | QuantaFleet is developing a data-processing tool that will run in Google Cloud and access ... |
| [Q40](#q40) | SilverOak Analytics is deploying a licensed reporting application on a new Compute Engine ... |
| [Q41](#q41) | Northstar Games maintains 4.8 petabytes of historical player-event data in Apache Avro fil... |
| [Q42](#q42) | BrightCart operates an online grocery platform on Google Cloud. A new application engineer... |
| [Q43](#q43) | OrbitPay runs payment-processing workloads across many Google Cloud projects. The company ... |
| [Q44](#q44) | LumaDesk Technologies has built an AI support agent that must remain available to handle c... |
| [Q45](#q45) | NovaForge Solutions needs to provide browser-based development environments for 55 externa... |
| [Q46](#q46) | MetricHaven operates a monitoring agent in a Google Kubernetes Engine cluster. The agent m... |
| [Q47](#q47) | BrightCart Media stores product images in a Cloud Storage bucket that uses a customer-mana... |
| [Q48](#q48) | AsterPeak Commerce runs a customer-ordering platform in a production Google Cloud project.... |
| [Q49](#q49) | NovaRender Studios runs a large-scale visual-effects pipeline across several hundred Compu... |
| [Q50](#q50) | BrightCart operates an online retail platform on Google Cloud. During a least-privilege re... |

---

### Q1

> GlobeRoute is preparing a new Google Cloud project for a worldwide logistics platform. The application will store its transactional data in Spanner, and the engineering team is preparing to create its first Spanner instance. What should the team do first?  

- **A.** Enable the Cloud Spanner API in the Google Cloud project.
- **B.** Select a multi-region configuration for the Spanner instance.
- **C.** Create a VPC network with subnets in every region where the application operates.
- **D.** Grant the Cloud Spanner Admin IAM role to the engineer creating the instance.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the Cloud Spanner API must be enabled in the Google Cloud project before the project can create and manage Spanner resources through the Google Cloud console, Google Cloud CLI, REST API, or client libraries. Enabling the API activates the required Spanner service endpoint for that project. Because GlobeRoute has already created the project and is now preparing to create its first instance, enabling the Cloud Spanner API is the appropriate initial service-configuration step. Billing must also be enabled for the project, and the person creating the instance must possess the required IAM permissions, but among the listed choices, enabling the API is the first action directly required to make Spanner available in the new project.

**B is incorrect** because selecting a multi-region configuration is part of creating and configuring the Spanner instance, not the first project-preparation step. A multi-region configuration can be appropriate for a globally distributed application because it replicates data across multiple regions and can provide low-latency reads, regional-failure resilience, and a higher availability SLA. However, the team cannot proceed with normal Spanner instance creation until the Cloud Spanner API has been enabled. The instance configuration, edition, location, compute capacity, and scaling mode are selected during the instance creation process after the project has been prepared.

**C is incorrect** because Spanner does not require customers to create VPC subnets in each region where Spanner maintains replicas. Spanner is a fully managed database service, and Google manages its underlying infrastructure, replication topology, networking, storage, and server resources. The geographic placement of data is determined by the selected Spanner instance configuration rather than by the customer’s VPC subnet layout. A VPC might be needed for application resources such as Compute Engine instances or Google Kubernetes Engine clusters, but creating regional subnets is not a prerequisite for creating a Spanner instance.

**D is incorrect** because the engineer needs sufficient IAM permissions to create a Spanner instance, but granting the Cloud Spanner Admin role to yourself is not necessarily the first required action and might not be possible. Only a principal with permission to modify the project’s IAM policy can grant that role. The engineer might already have the required permissions through an existing project-level role, a Google Group, or a custom role. In addition, Cloud Spanner Admin is a broad administrative role and should only be granted when its full permissions are required. Enabling the Cloud Spanner API is the direct service-enablement step required for the new project before creating the instance.

**Reference links**

- [docs.cloud.google.com/spanner/docs/getting-started/set-up](https://docs.cloud.google.com/spanner/docs/getting-started/set-up)
- [docs.cloud.google.com/spanner/docs/create-manage-instances](https://docs.cloud.google.com/spanner/docs/create-manage-instances)
- [docs.cloud.google.com/spanner/docs/iam](https://docs.cloud.google.com/spanner/docs/iam)

**Related notes:** [Spanner](../05-storage-databases-data/products/spanner.md)

</details>

[Back to index](#index)

---

### Q2

> NovaForge Games maintains a development project in Google Cloud. Its DevOps group must be able to create, modify, and delete all Compute Engine resources, including VM instances, disks, images, networks, and firewall rules. The group may view other project resources but must not create or modify them. Following Google-recommended IAM practices, what should the administrator do?  

- **A.** Grant roles/viewer and the predefined roles/compute.admin role to the DevOps group.
- **B.** Create an IAM policy containing compute.instanceAdmin.\* permissions and assign the policy directly to the DevOps group.
- **C.** Create a custom role at the folder level containing compute.instanceAdmin.\* permissions and grant the custom role to the DevOps group.
- **D.** Grant the basic roles/editor role to the DevOps group.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because roles/compute.admin is the predefined Compute Admin role and provides full control of all Compute Engine resources. It allows the DevOps group to administer resources such as VM instances, instance templates, instance groups, disks, snapshots, images, networks, subnets, firewall rules, and load-balancing components that belong to Compute Engine. The roles/viewer role provides read-only access to resources elsewhere in the project but does not allow the group to create, update, or delete those other resources. Using a Google-managed predefined role is preferable when an existing predefined role already matches the required responsibilities, because Google maintains its permission set as Compute Engine evolves. A separate roles/iam.serviceAccountUser grant might also be required when the group must attach service accounts to VM instances, but that additional requirement does not change the best answer among the available choices.

**B is incorrect** because IAM policies do not directly grant arbitrary permission expressions to principals. An IAM allow policy contains role bindings that associate principals, such as a Google group, with IAM roles. Additionally, compute.instanceAdmin.\* is not a valid permission wildcard that can be placed in a policy. IAM permission names must refer to specific operations, and wildcard characters cannot be used when defining a custom role. The appropriate approach is to grant an existing predefined role such as roles/compute.admin rather than trying to construct and attach a policy containing an invalid permission pattern.

**C is incorrect** because Google Cloud custom roles can be created only at the project or organization level; they cannot be defined at the folder level. An organization-level custom role can later be granted on a folder, but the role itself is not created as a folder-level custom role. Furthermore, compute.instanceAdmin.\* is not a valid wildcard permission expression, and wildcard characters cannot be used in a custom role’s included permissions. Creating and maintaining a custom role is also unnecessary when the predefined roles/compute.admin role already provides the required full control of Compute Engine resources.

**D is incorrect** because roles/editor is a highly permissive basic role that grants create, update, and delete permissions across many Google Cloud services, not only Compute Engine. Granting it would allow the DevOps group to modify unrelated resources such as storage, application, database, and networking service resources, depending on the APIs and resources present in the project. This violates the requirement that the group must not create or update resources outside Compute Engine. Google recommends using the most limited predefined or custom role that satisfies the access requirement instead of broadly scoped basic roles such as Editor.

**Reference links**

- [docs.cloud.google.com/compute/docs/access/iam](https://docs.cloud.google.com/compute/docs/access/iam)
- [docs.cloud.google.com/iam/docs/roles-overview](https://docs.cloud.google.com/iam/docs/roles-overview)
- [docs.cloud.google.com/iam/docs/creating-custom-roles](https://docs.cloud.google.com/iam/docs/creating-custom-roles)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q3

> PixelHarbor operates a photo-sharing platform on a Google Kubernetes Engine cluster. A thumbnail-generation microservice performs CPU-intensive image transformations but consumes relatively little memory. The platform’s API, authentication, and notification microservices run efficiently on n2-standard machine types. You need to improve resource efficiency while keeping all microservices in the same cluster. What should you do?  

- **A.** Give the thumbnail-generation Pods a higher Kubernetes Pod priority than the other application Pods.
- **B.** Create a separate node pool that uses compute-optimized machine types for the thumbnail-generation microservice, and continue running the other microservices on the general-purpose n2-standard node pool.
- **C.** Run the thumbnail-generation microservice on the general-purpose n2-standard node pool, and create a compute-optimized node pool for the API, authentication, and notification microservices.
- **D.** Specify suitable CPU and memory requests only for the thumbnail-generation Deployment, and leave the resource requests of the other microservices at their default values.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Pod priority controls scheduling precedence and preemption rather than selecting hardware that matches a workload’s resource profile. A higher-priority thumbnail-generation Pod would be scheduled before lower-priority Pods and might cause lower-priority Pods to be evicted when cluster resources are insufficient. However, it would still run on the same general-purpose nodes and would not provide compute-optimized processors or improve the suitability of the node’s CPU-to-memory characteristics. Pod priority is useful when one workload is more operationally important than another, but the scenario requires efficient placement of CPU-intensive and general-purpose workloads on different machine types.

**B is correct** because GKE Standard clusters can contain multiple node pools, and each node pool can use a different Compute Engine machine type. The CPU-intensive thumbnail-generation workload should run on a node pool containing compute-optimized machines, which are designed for compute-bound workloads and provide high performance per core. The remaining microservices already perform efficiently on balanced n2-standard general-purpose machines, so they should remain on the existing general-purpose node pool. The team can label or taint the compute-optimized node pool and configure the thumbnail-generation Pods with a matching nodeSelector, node affinity rule, or toleration. This ensures that the CPU-intensive Pods are placed on the intended nodes instead of being scheduled randomly across the cluster. Appropriate CPU and memory requests should still be configured for every workload, and cluster autoscaling can be enabled independently for the node pools, but the essential optimization is matching each workload category to the appropriate node-pool machine type.

**C is incorrect** because it assigns the machine types to the opposite workloads. The thumbnail-generation microservice is the CPU-intensive workload and would benefit from compute-optimized nodes. The API, authentication, and notification services are already optimized for n2-standard machines, so moving them to compute-optimized nodes would not address the identified resource mismatch and could result in inefficient capacity use. The compute-optimized node pool should be dedicated to the image-processing workload, while the balanced general-purpose node pool should continue hosting the other microservices.

**D is incorrect** because resource requests tell the Kubernetes scheduler how much CPU and memory to reserve for a Pod, but they do not change the underlying machine type or guarantee placement on compute-optimized hardware. Correct requests are important for scheduling, autoscaling, resource isolation, and avoiding contention, but requests alone do not solve the need to use different hardware profiles for distinct workload categories. Leaving the other microservices at default resource requests is also poor practice. Containers without accurately configured requests can be scheduled inefficiently, interfere with cluster autoscaling decisions, and compete unpredictably for node resources. All microservices should have requests based on observed resource consumption, while a separate compute-optimized node pool should be used for the CPU-intensive workload.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/node-pools](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/node-pools)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/workload-separation](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/workload-separation)
- [docs.cloud.google.com/compute/docs/compute-optimized-machines](https://docs.cloud.google.com/compute/docs/compute-optimized-machines)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q4

> LedgerNest has developed a containerized payment-reconciliation application that must run on Kubernetes. Because the application processes critical financial transactions, the production environment must prioritize availability, security, and platform stability. The operations team wants Google Cloud to manage as much of the cluster infrastructure as possible while following Google-recommended practices. What should the team do?  

- **A.** Create a GKE Autopilot cluster and enroll it in the Rapid release channel.
- **B.** Create a GKE Autopilot cluster and enroll it in the Stable release channel.
- **C.** Create a zonal GKE Standard cluster and enroll it in the Stable release channel.
- **D.** Create a regional GKE Standard cluster and enroll it in the Rapid release channel.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because GKE Autopilot is an appropriate choice for a production application, but the Rapid release channel is not the best choice when stability is the primary requirement. Autopilot clusters are always regional, and Google manages the underlying nodes, scaling, security configurations, and many operational settings by applying built-in best practices. However, the Rapid channel receives new Kubernetes versions and GKE features earlier than the other channels. This makes Rapid useful for development, testing, validation, and applications that need early access to new capabilities, but it also gives organizations less time to validate version changes before they reach production. A business-critical financial application should generally use a channel that prioritizes maturity and stability over feature velocity.

**B is correct** because GKE Autopilot minimizes the operational burden of running Kubernetes while applying Google-recommended practices for availability, security, scaling, and resource management. Autopilot clusters are regional, which means the cluster control plane is replicated across multiple zones within a region. This provides greater resilience to a zonal disruption than a zonal Standard cluster. Google also manages the cluster’s worker-node infrastructure, node provisioning, node upgrades, repairs, and capacity scaling. Enrolling the cluster in the Stable release channel provides Kubernetes and GKE versions that have spent more time being validated in the Rapid and Regular channels. The Stable channel therefore prioritizes production stability and gives the team more time to evaluate changes before newer versions reach the cluster. This combination is the most suitable choice for a business-critical application when the team wants strong reliability and extensive Google-managed operations.

**C is incorrect** because the Stable release channel is appropriate for a workload that prioritizes stability, but a zonal GKE Standard cluster provides lower availability than an Autopilot cluster. A zonal cluster has a control plane associated with a single zone, and its default nodes can also be concentrated in that zone. A disruption affecting the zone can therefore affect cluster management or application availability unless the team implements additional architecture and redundancy measures. Standard mode also requires the team to make more infrastructure decisions, including node-pool configuration, machine selection, scaling, upgrades, and workload distribution. A zonal Standard cluster can be suitable for development, testing, or less critical workloads, but it is not the strongest Google-recommended option among these choices for a business-critical production application.

**D is incorrect** because a regional GKE Standard cluster provides strong availability by replicating the control plane across multiple zones and can distribute worker nodes across zones. It is therefore more reliable than a zonal Standard cluster. However, the Rapid release channel prioritizes early access to new Kubernetes versions and GKE functionality rather than maximum version stability. This is not the preferred release channel for a business-critical production application whose primary requirement is reliability. Standard mode also leaves more cluster infrastructure management to the team than Autopilot. A regional Standard cluster enrolled in the Stable channel could be appropriate when the organization requires direct control over nodes, machine types, or low-level cluster settings, but that combination is not provided as an answer option.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/release-channels](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/regional-clusters](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/regional-clusters)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q5

> ShopPulse hosts its customer-order portal on Compute Engine virtual machines. The operations team must be notified automatically when HTTP response latency remains above 1.8 seconds for at least 7 minutes. You need to implement the Google-recommended solution without developing or maintaining additional application code. What should you do?  

- **A.** Export the Cloud Monitoring metrics to BigQuery and create a Looker Studio dashboard that displays the portal’s response latency.
- **B.** Create a Cloud Monitoring metric-threshold alerting policy for HTTP response latency, configure a 7-minute retest window, and add the support team’s notification channel.
- **C.** Develop an App Engine service that periodically calls the Cloud Monitoring API and sends messages when it detects unusual latency.
- **D.** Create a Cloud Monitoring dashboard for response latency and ask the support team to monitor it continuously.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because exporting monitoring data to BigQuery and displaying it in Looker Studio provides historical analysis and visualization, but it does not directly satisfy the requirement to notify the support team automatically when latency remains above a threshold for a defined period. The team would need an additional alerting mechanism to examine the exported data and send notifications. This architecture would also add unnecessary configuration, data-storage costs, query costs, and operational complexity when Cloud Monitoring already provides native metric-based alerting.

**B is correct** because Cloud Monitoring alerting policies are the built-in, Google-recommended mechanism for automatically detecting metric conditions and notifying responders. The team can select the HTTP response latency metric, define a threshold such as 1.8 seconds, and set the retest window to 7 minutes. The condition is triggered only when the latency continues to violate the threshold throughout the configured window, which helps prevent alerts caused by brief latency spikes. The policy can use a notification channel such as email, SMS, the Google Cloud mobile application, Slack, PagerDuty, or a webhook to notify the support team. This solution requires configuration rather than application development and avoids operating a separate monitoring service.

**C is incorrect** because developing an App Engine service that invokes the Cloud Monitoring API introduces unnecessary development and maintenance work. The team would need to implement metric queries, threshold evaluation, scheduling, error handling, authentication, notification delivery, retries, and monitoring for the custom monitoring service itself. This duplicates functionality already provided by Cloud Monitoring alerting policies and directly conflicts with the requirement for no development cost.

**D is incorrect** because a Cloud Monitoring dashboard provides useful visualizations of latency metrics but does not automatically notify the support team when a threshold is violated. Team members would have to watch the dashboard continuously and take action manually, which is unreliable and does not meet the automatic-notification requirement. Dashboards can complement an alerting policy during investigation, but they are not a replacement for automated alerting.

**Reference links**

- [docs.cloud.google.com/monitoring/alerts](https://docs.cloud.google.com/monitoring/alerts)
- [docs.cloud.google.com/monitoring/alerts/using-alerting-ui](https://docs.cloud.google.com/monitoring/alerts/using-alerting-ui)
- [docs.cloud.google.com/monitoring/support/notification-options](https://docs.cloud.google.com/monitoring/support/notification-options)

**Related notes:** [Cloud Monitoring](../07-operations-cost/products/cloud-monitoring.md)

</details>

[Back to index](#index)

---

### Q6

> DataForge Labs runs an on-premises inventory-reconciliation program composed of several compiled executables. Every night at 1:30 a.m., the program loads data files into memory and processes them for approximately 75 minutes. Individual files range from 2 GiB to 18 GiB. The company wants to migrate the workload to Google Cloud with minimal operational effort and cost. What should the team do?  

- **A.** Package the executables in a container, deploy the container as a Cloud Run job with sufficient memory and task timeout settings, and use Cloud Scheduler to execute the job nightly.
- **B.** Package the executables in a container, deploy the container to Google Kubernetes Engine, and create a Kubernetes CronJob to execute the application nightly.
- **C.** Upload the executables to a Cloud Run function and use Cloud Scheduler to invoke the function nightly.
- **D.** Move the executables to a Compute Engine VM and attach an instance schedule that starts and stops the VM every night.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Cloud Run jobs are designed for containerized workloads that perform processing and exit when the work is complete. Unlike a Cloud Run service, a job does not need to listen for HTTP requests or continuously serve traffic. The existing executables can be packaged with their operating system libraries and dependencies in a container image, which minimizes changes to the application. Cloud Run jobs support task timeouts substantially longer than the 75-minute processing period, and a job can be configured with up to 32 GiB of memory, providing enough capacity for an 18 GiB input file plus the application and operating-system overhead. Cloud Scheduler can securely start the job at the required time each night. Because the compute resources are allocated for the job execution instead of requiring a continuously running server or Kubernetes cluster, this approach minimizes infrastructure administration and idle-resource cost.

**B is incorrect** because GKE can run the container and a Kubernetes CronJob can execute it on a schedule, but operating a Kubernetes cluster is unnecessary for a single nightly batch process. The team would need to provision and manage cluster capacity, node pools, upgrades, security, autoscaling, scheduling, and workload configuration. Nodes might also remain provisioned when the application is not running unless the team implements and manages additional scaling behavior. GKE is appropriate when an organization needs Kubernetes capabilities or operates many containerized workloads, but Cloud Run jobs provide a simpler serverless execution model for this standalone batch workload.

**C is incorrect** because Cloud Run functions are intended for function-oriented source code with a supported runtime, function entry point, and event or HTTP handler. Arbitrary compiled executables cannot simply be uploaded and executed as a function without creating wrapper code and adapting the application to the function execution model. The 75-minute processing duration also exceeds the maximum execution time of a Cloud Run function. In addition, large in-memory batch processing is better represented as a run-to-completion container job than as a request-driven function. This option would therefore require more development effort and would not meet the workload’s execution requirements.

**D is incorrect** because a Compute Engine VM can run the existing executables and an instance schedule can start and stop the VM automatically, but the team would remain responsible for selecting and maintaining the operating system, applying patches, installing dependencies, monitoring startup behavior, handling failures, and ensuring that the scheduled stop does not interrupt an execution that takes longer than expected. Storage and other attached resources can also continue to incur charges while the VM is stopped. Although this lift-and-shift approach is technically possible, it has more operational overhead than a Cloud Run job and does not provide the same serverless run-to-completion model.

**Reference links**

- [docs.cloud.google.com/run/docs/create-jobs](https://docs.cloud.google.com/run/docs/create-jobs)
- [docs.cloud.google.com/run/docs/execute-jobs-on-schedule](https://docs.cloud.google.com/run/docs/execute-jobs-on-schedule)
- [docs.cloud.google.com/run/docs/configuring/jobs/memory-limits](https://docs.cloud.google.com/run/docs/configuring/jobs/memory-limits)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md) · [Cloud Scheduler](../04-events-integration/products/cloud-scheduler.md)

</details>

[Back to index](#index)

---

### Q7

> TrailNest operates a hiking-route application on Google Kubernetes Engine (GKE). A backend workload running in Pods must read map data from a private Cloud Storage bucket. The organization prohibits service account key creation. You need to provide the workload with only the required bucket permissions by using a Google-recommended authentication method. What should you do?  

- **A.** -Enable Workload Identity Federation for GKE on the cluster.  
  -Grant the cluster’s default node service account access to the Cloud Storage bucket, and allow the application Pods to inherit the node service account’s permissions.
- **B.** -Enable Workload Identity Federation for GKE on the cluster.  
  -Create an IAM service account and a dedicated Kubernetes ServiceAccount.  
  -Link the Kubernetes ServiceAccount to the IAM service account, assign the Kubernetes ServiceAccount to the application Pods, and grant the required Cloud Storage permissions to the IAM service account.
- **C.** -Deploy the application to the GKE cluster and obtain an exception to create an IAM service account key.  
  -Configure the constraints/iam.serviceAccountKeyExpiryHours organization policy so that the key expires after 12 hours.
- **D.** -Deploy the application to the GKE cluster and obtain an exception to create an IAM service account key.  
  -Configure the constraints/iam.serviceAccountKeyExpiryHours organization policy so that the key expires after 6 hours.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because granting Cloud Storage access to the default node service account gives the permission to the identity used by the GKE nodes rather than to a dedicated identity for the application. Multiple workloads running on the same nodes could potentially use permissions associated with the node service account, which increases the scope of access and does not provide workload-level isolation. Workload Identity Federation for GKE is designed to let individual Kubernetes workloads use separate identities, so an application should use its own Kubernetes ServiceAccount and receive only the IAM permissions that it requires. Granting application permissions to the node service account creates an unnecessarily broad permission boundary and conflicts with the principle of least privilege.

**B is correct** because Workload Identity Federation for GKE provides keyless authentication between a Kubernetes workload and Google Cloud APIs. The application Pods run as the dedicated Kubernetes ServiceAccount, which is linked to an IAM service account through the Workload Identity Federation configuration. The GKE metadata server provides short-lived credentials to the Pods based on that workload identity, so no downloadable or stored service account key is required. The IAM service account can then be granted an appropriate role on the specific Cloud Storage bucket, such as Storage Object Viewer when the application only needs to read and list objects. This design isolates the application’s permissions from the node identity, supports least-privilege access, avoids persistent credentials, and complies with the organization policy that prohibits service account keys. GKE also supports granting IAM roles directly to a Kubernetes ServiceAccount principal in some configurations, but among the provided choices, linking the dedicated Kubernetes ServiceAccount to a dedicated IAM service account is the correct Google-recommended approach.

**C is incorrect** because requesting an exception to create an IAM service account key is unnecessary when Workload Identity Federation for GKE provides secure, keyless authentication. Setting a key expiration period reduces how long the key remains usable, but it does not eliminate the risks associated with creating, distributing, mounting, storing, and rotating a private key. The key could still be copied or exposed during its valid period, and the application would require additional key-rotation procedures to avoid outages. This approach also bypasses the organization’s intended security control instead of using the purpose-built GKE authentication mechanism.

**D is incorrect** because a shorter service account key lifetime does not make key-based authentication the recommended solution. Although a 6-hour expiration limits the duration of a compromised key, the key still exists as a portable credential that must be securely delivered to the Pods and repeatedly rotated. Frequent rotation also increases operational complexity and can cause application failures when credentials expire or are not replaced correctly. Workload Identity Federation for GKE automatically supplies short-lived credentials without creating service account keys, so requesting a policy exception remains unnecessary regardless of whether the proposed key expires after 6 hours, 12 hours, or another interval.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/workload-identity](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/workload-identity)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/workload-identity](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/workload-identity)
- [docs.cloud.google.com/storage/docs/access-control/iam-roles](https://docs.cloud.google.com/storage/docs/access-control/iam-roles)

**Related notes:** [Workload Identity Federation for GKE](../02-identity-security/products/workload-identity-federation-for-gke.md)

</details>

[Back to index](#index)

---

### Q8

> NimbusCart operates two Google Kubernetes Engine (GKE) clusters created with the gcloud container clusters command. These clusters are mentioned below. After running kubectl get nodes, the platform engineer sees only the nodes associated with sales-cluster. Which commands should the engineer run to view the node status for inventory-cluster?  
> -sales-cluster is a Standard cluster.  
> -inventory-cluster is an Autopilot cluster.  

- **A.** a. gcloud container clusters get-credentials inventory-cluster  
  b. kubectl get nodes
- **B.** a. gcloud container clusters update --generate-password inventory-cluster  
  b. kubectl get nodes
- **C.** a. kubectl config set-context inventory-cluster  
  b. kubectl cluster-info
- **D.** a. kubectl config set-credentials inventory-cluster  
  b. kubectl cluster-info

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because kubectl sends commands to the cluster selected by the current context in the kubeconfig file. The gcloud container clusters get-credentials inventory-cluster command retrieves the inventory-cluster control-plane endpoint and authentication information, adds or updates the corresponding cluster, user, and context entries in kubeconfig, and makes that context current. After this command completes, kubectl get nodes queries inventory-cluster and displays the status of its available nodes. The same kubeconfig and context-selection mechanism applies to both Standard and Autopilot clusters, even though Google manages the underlying nodes and infrastructure in Autopilot mode. In an actual environment, the command might also require --location and --project when those values cannot be determined from the active gcloud configuration.

**B is incorrect** because gcloud container clusters update modifies the configuration of an existing cluster; it is not the command used to retrieve access credentials or switch the active kubectl context. The --generate-password argument is not the mechanism for configuring kubectl access to a GKE cluster. Even if a valid cluster update operation were performed, it would not necessarily update kubeconfig or make inventory-cluster the current kubectl target. Cluster-management commands and kubectl authentication commands serve different purposes.

**C is incorrect** because kubectl config set-context creates or modifies a context definition, but it does not automatically make that context current. Selecting an existing context requires kubectl config use-context CONTEXT_NAME. In addition, the context generated by GKE commonly includes the project, location, and cluster name rather than using only the simple cluster name inventory-cluster. The command also does not retrieve the GKE endpoint and authentication information required to access the cluster. Finally, kubectl cluster-info displays control-plane and cluster-service information; it does not provide the node-status listing requested in the question.

**D is incorrect** because kubectl config set-credentials creates or changes a user credential entry in kubeconfig. It does not retrieve the GKE cluster endpoint, associate the credentials with the correct cluster, create a complete context, or switch kubectl to that context. A kubeconfig context combines a cluster, a user, and optionally a namespace, so configuring only a credential entry is insufficient. Additionally, kubectl cluster-info reports information about the currently selected cluster rather than listing node status. The required node-status command is kubectl get nodes.

**Reference links**

- [cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl)
- [cloud.google.com/sdk/gcloud/reference/container/clusters/get-credentials](https://cloud.google.com/sdk/gcloud/reference/container/clusters/get-credentials)
- [kubernetes.io/docs/reference/kubectl/generated/kubectl_config/kubectl_config_set-context/](https://kubernetes.io/docs/reference/kubectl/generated/kubectl_config/kubectl_config_set-context/)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q9

> BrightForge develops a mobile application, and its engineers currently use many user-managed service account keys. The security team plans to replace these keys with safer authentication methods later, but it needs an immediate control that enforces short-lived keys. The requirements are mentioned below. The solution should follow Google recommendations and minimize cost and operational effort. What should the security team do?  
> -Any service account that still requires a key must be created in a centralized project named identity-key-hub.  
> -Every newly created service account key must expire after 8 hours.  

- **A.** -Deploy a Cloud Run job that periodically replaces all service account keys in identity-key-hub.  
  -Enforce an organization policy that disables service account key creation everywhere except identity-key-hub.
- **B.** -Deploy a Kubernetes CronJob that periodically replaces all service account keys.  
  -Disable cross-project service account usage throughout the organization except for identity-key-hub.
- **C.** -Configure the service account key expiry organization policy constraint to allow an 8-hour lifetime in identity-key-hub.  
  -Enforce an organization policy that disables service account key creation everywhere except identity-key-hub.
- **D.** -Configure a DENY rule on the service account key expiry organization policy constraint for 8 hours.  
  -Disable cross-project service account usage throughout the organization except for identity-key-hub.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because running a Cloud Run job to rotate keys is a custom operational solution rather than the simplest Google-recommended control for temporary development keys. The team would need to develop, secure, schedule, monitor, and maintain the rotation logic. It would also need to distribute each replacement key safely before deleting or disabling the old key, and failures in this workflow could interrupt development. Although enforcing the Disable service account key creation constraint outside identity-key-hub correctly centralizes key creation, periodic rotation does not guarantee that every newly created key has an enforced maximum lifetime. Google Cloud provides the constraints/iam.serviceAccountKeyExpiryHours organization policy constraint specifically for this requirement, so a custom Cloud Run job introduces unnecessary cost and complexity.

**B is incorrect** because a Kubernetes CronJob also requires custom key-rotation logic and an active GKE environment, creating more infrastructure cost and administrative overhead than a native organization policy. More importantly, the Disable cross-project service account usage constraint controls whether a service account from one project can be attached to a resource in another project. It does not prevent developers from creating user-managed service account keys in other projects, does not centralize key creation, and does not limit key validity. Preventing cross-project attachment could also conflict with the centralized design because workloads in other projects might legitimately need to use service accounts located in identity-key-hub.

**C is correct** because constraints/iam.serviceAccountKeyExpiryHours is the native organization policy constraint for setting the maximum validity period of newly created user-managed service account keys. It is a list constraint that accepts supported ALLOW values, including 8h. Applying it to identity-key-hub ensures that every new key created there expires after eight hours. The constraints/iam.disableServiceAccountKeyCreation constraint can then be enforced throughout the organization with an exception for identity-key-hub, preventing key creation in other projects. Together, these policies centralize service accounts that require keys and enforce the required short lifetime without deploying or maintaining a rotation service. This minimizes cost and operational effort. The expiry constraint is not retroactive, so existing keys must be inventoried and removed or rotated separately; it governs keys created after the policy takes effect.

**D is incorrect** because constraints/iam.serviceAccountKeyExpiryHours accepts ALLOW values and does not support DENY values. Therefore, a DENY rule for 8 hours is not a valid configuration. In addition, disabling cross-project service account usage governs whether service accounts can be attached to resources in different projects; it does not stop key creation outside identity-key-hub. This option therefore fails both requirements and could prevent workloads in other projects from using the centralized service accounts.

**Reference links**

- [cloud.google.com/organization-policy/restrict-service-accounts](https://cloud.google.com/organization-policy/restrict-service-accounts)
- [cloud.google.com/iam/docs/service-account-creds](https://cloud.google.com/iam/docs/service-account-creds)
- [cloud.google.com/iam/docs/migrate-from-service-account-keys](https://cloud.google.com/iam/docs/migrate-from-service-account-keys)

**Related notes:** [Organization Policy Service](../02-identity-security/products/organization-policy-service.md)

</details>

[Back to index](#index)

---

### Q10

> Northstar Retail operates an online ordering platform on virtual machines with separate presentation, application, and database layers. The database uses MySQL. The infrastructure team plans to migrate the platform to Compute Engine and Cloud SQL for MySQL and needs an estimated monthly cost for the proposed Google Cloud environment. What should the team do?  

- **A.** -Create a Google Sheets workbook containing several Google Cloud resource configurations.  
  -Import current Google Cloud prices into another sheet and calculate the projected costs by using spreadsheet formulas.
- **B.** Use the Google Cloud Pricing Calculator and select a Cloud Operations Suite template to describe the complete application architecture.
- **C.** Deploy a smaller version of the architecture on Google Cloud, perform load testing, review the resulting Cloud Billing data, and extrapolate the cost for the platform’s normal production traffic.
- **D.** -Use the Google Cloud Pricing Calculator to estimate every Google Cloud resource that the architecture will require.  
  -Select Compute Engine machine types comparable to the existing application servers, and use the specifications and workload characteristics of the current MySQL servers to select Cloud SQL resources.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because maintaining a custom pricing spreadsheet requires the company to collect, import, validate, and continuously update prices for Compute Engine, Cloud SQL, storage, networking, load balancing, backups, and other resources. Google Cloud pricing can vary by region, machine type, resource configuration, usage duration, and applicable discounts. A spreadsheet can therefore become outdated or contain incorrect formulas and assumptions. Although a spreadsheet could theoretically calculate an estimate, the Google Cloud Pricing Calculator is the recommended purpose-built tool for estimating hypothetical workloads and already incorporates the relevant pricing models.

**B is incorrect** because the Google Cloud Pricing Calculator estimates costs by adding and configuring individual Google Cloud products and their expected usage. A Cloud Operations Suite template is not the appropriate mechanism for defining and pricing a complete three-tier application. Cloud Operations Suite provides observability capabilities such as monitoring, logging, and tracing; it does not represent a general application architecture template for estimating Compute Engine and Cloud SQL costs. The team must configure the expected Compute Engine, Cloud SQL, storage, networking, and other resources directly in the calculator.

**C is incorrect** because deploying an environment solely to produce an initial estimate introduces actual infrastructure charges, implementation effort, and operational overhead. A smaller-scale load test might also produce a misleading estimate because cloud costs and performance do not always scale linearly. Database caching, storage throughput, network traffic, high-availability configurations, backups, sustained resource use, and workload peaks can behave differently at production scale. Testing can be useful later for validating performance assumptions and refining the estimate, but it is unnecessary and less cost-effective when the immediate requirement is to prepare an estimated infrastructure cost.

**D is correct** because the Google Cloud Pricing Calculator is designed to estimate the cost of planned or hypothetical Google Cloud workloads. The team should identify every expected billable component, including Compute Engine instances, Cloud SQL for MySQL instances, persistent storage, database storage, backups, network data transfer, load balancing, and any monitoring or logging usage. It can then configure each component according to the expected region, machine type, operating hours, availability requirements, storage capacity, and traffic. Existing virtual-machine CPU and memory specifications provide a reasonable starting point for selecting comparable Compute Engine machine types. For Cloud SQL, the team should use the current MySQL server’s CPU, memory, storage, availability, and workload requirements to choose an appropriate Cloud SQL edition and machine configuration. The resulting calculation is still an estimate based on assumptions, but it is the recommended and most direct approach for producing an initial total cost projection.

**Reference links**

- [cloud.google.com/products/calculator](https://cloud.google.com/products/calculator)
- [docs.cloud.google.com/billing/docs/how-to/estimate-costs](https://docs.cloud.google.com/billing/docs/how-to/estimate-costs)
- [docs.cloud.google.com/sql/docs/mysql/instance-settings](https://docs.cloud.google.com/sql/docs/mysql/instance-settings)

**Related notes:** [Pricing Calculator](../07-operations-cost/products/pricing-calculator.md)

</details>

[Back to index](#index)

---

### Q11

Choose 2.

> BlueHarbor Media uses GitHub Actions to deploy a standard three-tier content platform into separate development, testing, and production Google Cloud projects. The platform engineering team wants every developer to deploy from a centrally governed architecture, and the workflows must authenticate without storing long-lived service account credentials. Which two actions should BlueHarbor Media take? (Choose two.)  

- **A.** Publish the approved architecture as an Application Design Center template.
- **B.** Save an encrypted service account key as a GitHub Actions repository secret.
- **C.** Assign the Owner role directly to the GitHub Actions deployment identity.
- **D.** Configure Workload Identity Federation to trust GitHub’s OIDC tokens.
- **E.** Instruct developers to create each application resource manually.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A, D

**Explanation**

**A is correct** because Application Design Center enables platform teams to design, manage, and share standardized application architectures. The platform engineering team can create a reusable template containing the approved application components, connections, configurations, and organizational best practices. Developers can then use that centrally governed template to create and deploy consistent application environments across multiple Google Cloud projects. This approach reduces configuration drift, discourages unapproved architecture changes, and provides developers with a self-service deployment experience. Application Design Center templates can also generate Terraform configurations, allowing the approved architecture to be integrated with infrastructure-as-code and automated deployment processes such as GitHub Actions.

**B is incorrect** because storing an encrypted service account key in a GitHub repository still introduces a long-lived credential. Repository secrets protect the key from being displayed directly in workflow files, but the key remains a persistent credential that could be copied, exposed, or misused until it is revoked. The organization would also need processes for key generation, distribution, auditing, rotation, and deletion. This option directly conflicts with the requirement that the deployment workflow must not store service account keys. Workload Identity Federation is the preferred approach because it uses temporary credentials derived from GitHub’s OIDC tokens rather than a downloaded private key.

**C is incorrect** because the Owner role provides extremely broad permissions, including the ability to create and delete many project resources and modify IAM policies. A deployment workflow should receive only the permissions required to deploy and manage the approved application components. Additionally, GitHub Actions should authenticate through a properly configured Workload Identity Federation provider rather than being treated as an unrestricted project administrator. After federation is configured, the external GitHub identity can be granted narrowly scoped roles directly or allowed to impersonate a dedicated deployment service account with least-privilege permissions. Granting Owner would create unnecessary security exposure and would not independently satisfy the keyless authentication requirement.

**D is correct** because Workload Identity Federation allows GitHub Actions to authenticate to Google Cloud by exchanging a GitHub-issued OIDC token for short-lived Google Cloud credentials. The organization configures a workload identity pool and provider that trusts appropriate claims from GitHub, such as the repository, organization, branch, tag, or deployment environment. IAM conditions and attribute mappings can restrict which workflows are permitted to access Google Cloud. The workflow can then access resources directly through the federated identity or impersonate a dedicated service account with limited deployment permissions. Because credentials are generated dynamically for each workflow run and expire automatically, no long-lived service account key needs to be stored in GitHub.

**E is incorrect** because requiring developers to create resources manually would undermine both standardization and deployment automation. Individual developers could select different services, settings, regions, network configurations, or security controls, resulting in inconsistent environments and configuration drift across projects. Manual provisioning is also difficult to review, reproduce, audit, and roll back. A centrally published Application Design Center template gives developers a controlled and repeatable architecture while preserving a self-service experience, and GitHub Actions can automate the resulting deployment through keyless authentication.

**Reference links**

- [docs.cloud.google.com/application-design-center/docs/overview](https://docs.cloud.google.com/application-design-center/docs/overview)
- [docs.cloud.google.com/application-design-center/docs/design-application-templates](https://docs.cloud.google.com/application-design-center/docs/design-application-templates)
- [docs.cloud.google.com/iam/docs/workload-identity-federation-with-deployment-pipelines](https://docs.cloud.google.com/iam/docs/workload-identity-federation-with-deployment-pipelines)

**Related notes:** [Application Design Center](../08-iac-platform-ai/products/application-design-center.md) · [Workload Identity Federation and Workforce Identity Federation](../02-identity-security/products/workload-identity-federation-and-workforce-identity-federati.md)

</details>

[Back to index](#index)

---

### Q12

> FitPulse is building a health-tracking application that will run on Google Kubernetes Engine. The application requires MongoDB, and the company wants a managed database service with commercial support and a support SLA. What should FitPulse do?  

- **A.** Provision a Cloud Bigtable cluster and connect to it through the HBase API.
- **B.** Subscribe to MongoDB Atlas through Google Cloud Marketplace and deploy it on Google Cloud.
- **C.** Install MongoDB directly on individual Compute Engine instances.
- **D.** Install MongoDB on Compute Engine instances managed by a Managed Instance Group.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Cloud Bigtable is a fully managed, highly scalable wide-column NoSQL database, but it is not a managed MongoDB environment. The HBase API provides client compatibility for applications designed for Apache HBase; it does not make Bigtable compatible with MongoDB drivers, MongoDB query syntax, the MongoDB document model, or MongoDB operational features. Selecting Bigtable would therefore require redesigning the application’s database integration instead of providing the required managed MongoDB service.

**B is correct** because MongoDB Atlas is MongoDB’s fully managed database-as-a-service and can be purchased through Google Cloud Marketplace. Atlas can deploy MongoDB clusters on Google Cloud while handling infrastructure provisioning, database configuration, monitoring, backups, maintenance, scaling, patching, and high-availability capabilities. Eligible commercial Atlas subscriptions and support plans provide defined support service levels, allowing FitPulse to obtain the managed MongoDB environment and support SLA required by the scenario. Purchasing through Google Cloud Marketplace also provides integrated procurement and billing through the organization’s Google Cloud Billing account.

**C is incorrect** because installing MongoDB packages on Compute Engine creates a self-managed MongoDB deployment. Compute Engine provides and supports the virtual machine infrastructure, but the customer remains responsible for installing, configuring, securing, patching, monitoring, backing up, scaling, and recovering MongoDB. Google Cloud does not provide a MongoDB database support SLA merely because MongoDB is running on Compute Engine. FitPulse would need to operate the database itself or arrange separate support, so this option does not satisfy the requirement for a managed MongoDB environment.

**D is incorrect** because a Managed Instance Group manages Compute Engine VM instances rather than the MongoDB database running inside them. It can maintain a specified number of VMs, recreate failed instances, perform autoscaling, and apply rolling VM updates, but it does not manage MongoDB replication, elections, sharding, backups, database upgrades, data consistency, or database recovery. Stateful databases also require careful handling of persistent disks, identities, and initialization, which a standard Managed Instance Group does not automatically solve. FitPulse would still be responsible for MongoDB administration and would not receive a managed MongoDB support SLA from Google Cloud.

**Reference links**

- [cloud.google.com/mongodb](https://cloud.google.com/mongodb)
- mongodb.com/docs/atlas
- [docs.cloud.google.com/bigtable/docs/hbase-bigtable](https://docs.cloud.google.com/bigtable/docs/hbase-bigtable)

**Related notes:** [Cloud Marketplace](../08-iac-platform-ai/products/cloud-marketplace.md)

</details>

[Back to index](#index)

---

### Q13

> CloudForge Media operates a group of Compute Engine Linux virtual machines that host its internal content-processing services. Every member of the platform engineering team requires SSH access to all virtual machines for maintenance and troubleshooting. The company wants access to be granted and revoked centrally with minimal administrative effort when engineers join or leave the team. What should the company do?  

- **A.** Generate one SSH key pair for the entire platform engineering team, and store the shared public key in project metadata.
- **B.** Generate a separate SSH key pair for every engineer, and manually store each public key in the metadata of every applicable virtual machine.
- **C.** Create a Google Group for the platform engineering team, and grant the group the Compute Viewer IAM role.
- **D.** Create a Google Group for the platform engineering team, enable OS Login for the project, and grant the appropriate OS Login IAM role to the group.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because sharing one SSH key pair among all engineers creates security, accountability, and access-revocation problems. Every engineer would possess the same private key, so SSH activity could not be reliably associated with a specific individual based on the key used. If the private key were exposed, the company would need to replace it for the entire team and update the project metadata. When an engineer leaves the company, removing that person’s access would require rotating the shared key and securely distributing a replacement private key to every remaining engineer. Storing the public key in project metadata would also make that shared credential valid for every virtual machine that accepts project-wide metadata SSH keys. Google Cloud recommends identity-based access management instead of sharing credentials between users.

**B is incorrect** because individual SSH keys are more secure than one shared key, but manually maintaining those keys in instance metadata creates significant operational overhead. Administrators would need to add an engineer’s key to every relevant virtual machine when the engineer joins and remove it from every virtual machine when the engineer leaves. This process becomes increasingly difficult as the number of engineers and virtual machines grows, and a missed instance could leave a former employee with continued access. Project-level metadata could reduce some duplication, but metadata-based SSH key management would still require administrators to maintain individual key entries and expiration or removal processes. OS Login provides a more centralized and scalable approach by linking SSH authorization to Google identities and IAM.

**C is incorrect** because the Compute Viewer IAM role provides read-only access to Compute Engine resources but does not grant permission to log in to Linux virtual machines through OS Login. Members of the group could view information about instances, disks, networks, and other Compute Engine resources, but they would not automatically receive an operating-system account or SSH authorization. SSH access through OS Login requires an OS Login-specific role, such as roles/compute.osLogin for standard user access or roles/compute.osAdminLogin when engineers require administrative access with sudo. Therefore, using a Google Group is operationally efficient, but granting only Compute Viewer does not satisfy the SSH access requirement.

**D is correct** because OS Login integrates Compute Engine SSH access with Google identities and IAM. The company should enable OS Login at the project level by setting the enable-oslogin metadata value to TRUE and grant the Google Group an appropriate OS Login IAM role. The roles/compute.osLogin role allows engineers to connect as standard operating-system users, while roles/compute.osAdminLogin allows SSH access with administrative sudo privileges when maintenance duties require elevated permissions. Every engineer uses an individual identity and SSH credential, which improves accountability and avoids shared private keys. Because the role is assigned to a Google Group, new engineers receive access when they are added to the group, and departing engineers lose access when they are removed. Administrators do not need to update SSH keys separately on every virtual machine. Enabling OS Login also causes compatible instances to use IAM-based authorization instead of accepting SSH keys stored in project or instance metadata, making this the most secure and operationally efficient option.

**Reference links**

- [docs.cloud.google.com/compute/docs/oslogin](https://docs.cloud.google.com/compute/docs/oslogin)
- [docs.cloud.google.com/compute/docs/oslogin/set-up-oslogin](https://docs.cloud.google.com/compute/docs/oslogin/set-up-oslogin)
- [docs.cloud.google.com/iam/docs/groups-best-practices](https://docs.cloud.google.com/iam/docs/groups-best-practices)

**Related notes:** [OS Login](../02-identity-security/products/os-login.md)

</details>

[Back to index](#index)

---

### Q14

> StreamCart operates a real-time order-processing platform that uses several Dataflow streaming jobs. A recent application-code defect caused some pipeline stages to stop making progress while the jobs continued running. This delayed inventory updates and order notifications. The engineering team fixed the defect, but now needs a managed solution that automatically detects similar pipeline stalls and notifies the on-call team with minimal operational effort. What should the company do?  

- **A.** Modify each Dataflow pipeline to publish a message to Pub/Sub when processing is delayed, run a secondary Dataflow job for delayed messages, and use Cloud Tasks to generate notifications.
- **B.** Create Cloud Monitoring alerting policies for the Dataflow data freshness metric, and configure notifications when the metric exceeds an acceptable threshold.
- **C.** Use Error Reporting to find stack traces associated with slow Dataflow processing, and configure alerts for those errors.
- **D.** Use the Personalized Service Health dashboard to monitor Dataflow availability in every region.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because this approach requires custom pipeline development and introduces several additional services and operational components. The team would need to define how each Dataflow job detects its own delay, modify and redeploy the pipeline code, publish custom messages, maintain a secondary processing pipeline, and prevent duplicate or out-of-order processing between the primary and backup jobs. Cloud Tasks is designed to manage asynchronous task execution against application endpoints; it is not the standard notification mechanism for messages published to Pub/Sub. A monitoring solution should detect the symptoms of a stalled pipeline independently of the application code, especially because defective code might also prevent the custom delay-notification logic from functioning. Cloud Monitoring already collects Dataflow job metrics and can generate incidents and notifications without requiring a backup pipeline or custom alerting workflow.

**B is correct** because an increasing Dataflow data freshness metric is a direct indication that the pipeline is taking longer to process incoming data. Data freshness represents the difference between the event time of the data and the pipeline’s output watermark or processing progress. When one or more work items are repeatedly failing, a transform is stuck, or a stage cannot make progress, older data remains unprocessed and the data freshness value continues to increase. Cloud Monitoring natively integrates with Dataflow and supports threshold-based alerting policies for Dataflow metrics. The company can establish a normal baseline, define an acceptable freshness threshold and duration, and configure notification channels such as email, SMS, Pub/Sub, Slack, PagerDuty, or a webhook. Cloud Monitoring then creates an incident and notifies the on-call team when the condition persists. This solution requires minimal management because it uses a managed metric and alerting service rather than custom monitoring code. The team can also monitor system latency and backlog metrics to provide additional evidence of a stalled pipeline, but alerting on data freshness is the option that most directly meets the requirement.

**C is incorrect** because Error Reporting is intended to aggregate and display application errors that contain exceptions and stack traces. Stack traces can help engineers diagnose the cause of a pipeline problem after an error has been logged, but they are not a reliable measurement of pipeline progress. A Dataflow streaming job can remain in a running state while repeatedly retrying a problematic work item, accumulating backlog, or processing data increasingly slowly. Such a condition might not produce a new or uniquely identifiable stack trace that Error Reporting can use to trigger an alert. Error Reporting also cannot directly determine whether the pipeline’s watermark has stopped progressing. Data freshness and system latency metrics are designed to reveal this operational behavior, making Cloud Monitoring metric-based alerting more appropriate for detecting stuck jobs.

**D is incorrect** because Personalized Service Health reports Google Cloud service events that might affect an organization’s projects, such as regional service disruptions, outages, or other infrastructure-level incidents. It can help determine whether a Dataflow problem is associated with a Google-managed service event, but it does not monitor the progress of an individual pipeline or detect defects in customer-written Apache Beam code. In this situation, the previous disruption was caused by an application-code error, and the Dataflow jobs remained stuck until that code was corrected. Personalized Service Health would not necessarily report such a customer-specific pipeline condition. Dataflow metrics in Cloud Monitoring provide job-level visibility and can alert when data freshness indicates that processing has stalled.

**Reference links**

- [docs.cloud.google.com/dataflow/docs/guides/using-cloud-monitoring](https://docs.cloud.google.com/dataflow/docs/guides/using-cloud-monitoring)
- [docs.cloud.google.com/dataflow/docs/guides/using-monitoring-intf](https://docs.cloud.google.com/dataflow/docs/guides/using-monitoring-intf)
- [docs.cloud.google.com/dataflow/docs/guides/troubleshoot-slow-streaming-jobs](https://docs.cloud.google.com/dataflow/docs/guides/troubleshoot-slow-streaming-jobs)

**Related notes:** [Dataflow](../05-storage-databases-data/products/dataflow.md) · [Cloud Monitoring](../07-operations-cost/products/cloud-monitoring.md)

</details>

[Back to index](#index)

---

### Q15

> NovaRetail is migrating its online shopping platform from its data center to Compute Engine. The internet-facing web servers must accept requests from customers, while the inventory and payment-processing servers must be reachable only through private IP addresses. The web servers and private application servers must communicate with each other only over approved ports and protocols. How should NovaRetail design its Google Cloud network?  

- **A.** -Create one VPC network with a public-facing subnet for the web servers and a private subnet for the application servers.  
  -Configure firewall rules that permit the required traffic between the two groups and an ingress firewall rule that permits approved internet traffic to the web servers.
- **B.** -Create one VPC network with a public-facing subnet for the web servers and a private subnet for the application servers.  
  -Configure firewall rules that permit the required traffic between the two groups and an egress firewall rule that permits approved internet traffic from the web servers.
- **C.** -Create one VPC network containing the public-facing subnet and a separate VPC network containing the private subnet.  
  -Configure firewall rules that permit the required traffic between the two subnets and an ingress firewall rule that permits approved internet traffic to the web servers.
- **D.** -Create one VPC network containing the public-facing subnet and a separate VPC network containing the private subnet.  
  -Configure firewall rules that permit the required traffic between the two subnets and an egress firewall rule that permits approved internet traffic from the web servers.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a single VPC network can contain multiple regional subnets and provides internal routing between those subnets. NovaRetail can place the internet-facing web servers in one subnet and the private application servers in another subnet while using VPC firewall rules to control communication between the server groups. The rules can allow only the necessary protocols and ports, such as HTTPS traffic to the web tier and specific application or database ports between the web and private tiers. An ingress firewall rule is required to allow approved inbound connections from the internet to the public-facing servers because ingress traffic is blocked by the VPC network’s implied deny-ingress rule unless a higher-priority allow rule applies. The public servers must also have an external IP address or be placed behind an external load balancer, while the private servers can be configured without external IP addresses. Network tags or secure service account-based firewall rule targets can further restrict each rule to the intended servers rather than applying it to every VM in a subnet.

**B is incorrect** because an egress firewall rule controls traffic leaving the network interfaces of the targeted Compute Engine instances. It does not permit customers on the internet to initiate connections to the web servers. Internet clients generate inbound traffic from the perspective of the web servers, so an ingress allow rule is required. Additionally, VPC networks include an implied allow-egress rule unless it is overridden by another rule, meaning a general public egress rule might be unnecessary. Although the single-VPC and two-subnet design is appropriate, the firewall direction specified for public access does not satisfy the requirement.

**C is incorrect** because firewall rules apply only to resources within the VPC network where the rules are created. Creating one VPC for the public servers and another VPC for the private servers does not automatically establish connectivity between them. Routes are not exchanged between independent VPC networks, and firewall rules alone cannot make the two VPCs communicate. NovaRetail would also need to configure a connectivity mechanism such as VPC Network Peering, Network Connectivity Center, or Cloud VPN and then configure the required firewall rules in the relevant networks. Because the option does not include any mechanism connecting the two VPC networks, the web and private servers would not be able to communicate as required. Using separate VPC networks could provide stronger administrative isolation in a more complex architecture, but it is unnecessary for the stated requirement and requires additional networking configuration.

**D is incorrect** because it has two separate problems. First, placing the public and private servers in independent VPC networks does not allow them to communicate automatically. Firewall rules cannot create network connectivity or exchange routes between separate VPC networks, so an additional connectivity mechanism such as VPC Network Peering would be required. Second, an egress firewall rule permits outbound traffic from the targeted servers rather than inbound internet requests to the public-facing servers. The web tier requires an ingress allow rule for the approved destination ports, together with an external IP address or external load balancer. Therefore, this option provides neither the required inter-VPC connectivity nor the correct firewall direction for public access.

**Reference links**

- [docs.cloud.google.com/vpc/docs/vpc](https://docs.cloud.google.com/vpc/docs/vpc)
- [docs.cloud.google.com/firewall/docs/firewalls](https://docs.cloud.google.com/firewall/docs/firewalls)
- [docs.cloud.google.com/vpc/docs/vpc-peering](https://docs.cloud.google.com/vpc/docs/vpc-peering)

</details>

[Back to index](#index)

---

### Q16

> BrightRoute, a logistics software company, runs several containerized services and expects development teams to deploy additional services regularly. The company plans to use a GKE Standard cluster and wants the cluster’s compute capacity to grow automatically whenever new workloads cannot be scheduled. The platform team also wants to define limits on how small or large the cluster can become. What should the team do?  

- **A.** Deploy the services to GKE and configure a HorizontalPodAutoscaler for each Deployment.
- **B.** Deploy the services to GKE and configure a VerticalPodAutoscaler for each Deployment.
- **C.** Enable cluster autoscaling on the GKE node pool and configure minimum and maximum node counts.
- **D.** Create a dedicated node pool for every service and manually deploy each service to its assigned node pool.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a HorizontalPodAutoscaler automatically changes the number of Pod replicas for an individual workload based on metrics such as CPU utilization, memory utilization, custom metrics, or external metrics. It does not add or remove worker nodes from a GKE Standard cluster. If the HorizontalPodAutoscaler creates additional Pods but the existing nodes do not have enough available CPU or memory, the new Pods can remain in the Pending state unless cluster autoscaling is also enabled. Horizontal Pod autoscaling is useful for adjusting application-level capacity in response to traffic, but it does not independently ensure that the cluster has enough node capacity for newly deployed applications.

**B is incorrect** because a VerticalPodAutoscaler adjusts or recommends the CPU and memory requests assigned to a workload’s containers. Depending on its configuration, it can automatically recreate Pods with updated resource requests, but it does not directly resize the GKE node pool. Increasing a Pod’s resource requests might even make that Pod unschedulable when the existing nodes lack sufficient capacity. Cluster autoscaling would still be required to add nodes in response to such unschedulable Pods. Vertical Pod autoscaling is therefore designed for workload resource optimization rather than automatic expansion of the cluster’s underlying compute capacity.

**C is correct** because the GKE cluster autoscaler automatically changes the number of nodes in a node pool according to the scheduling requirements of workloads. When newly deployed applications create Pods that cannot be scheduled because the current nodes lack sufficient requested CPU, memory, or other resources, the cluster autoscaler can add nodes to the node pool. It can also remove underutilized nodes when their workloads can be safely rescheduled elsewhere. Configuring minimum and maximum node counts establishes capacity and cost boundaries while allowing GKE to manage node capacity without manual intervention. The minimum preserves the required baseline capacity, while the maximum prevents the node pool from growing beyond the organization’s intended limit.

**D is incorrect** because creating a separate node pool for every application introduces continuing administrative work whenever a new application is deployed. The platform team would need to create, configure, secure, upgrade, and manage each additional node pool, which conflicts with the requirement to avoid manual intervention. Dedicated node pools can be appropriate when workloads require different machine families, accelerators, security boundaries, operating systems, or scheduling constraints, but they are not necessary merely to provide automatic capacity growth. Enabling cluster autoscaling on a shared node pool is the simpler and more appropriate solution for automatically accommodating additional workloads.

**Reference links**

- [cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler](https://cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler)
- [cloud.google.com/kubernetes-engine/docs/how-to/cluster-autoscaler](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-autoscaler)
- [cloud.google.com/kubernetes-engine/docs/concepts/horizontalpodautoscaler](https://cloud.google.com/kubernetes-engine/docs/concepts/horizontalpodautoscaler)

**Related notes:** [HPA, VPA, and cluster autoscaler](../03-compute-containers/products/hpa-vpa-and-cluster-autoscaler.md)

</details>

[Back to index](#index)

---

### Q17

> NexaRoute operates logistics applications in its private data centers and across multiple cloud providers. These applications authenticate to Google Cloud APIs by using several hundred service accounts and associated keys. As part of a credential-rotation review, the security team needs an organization-wide inventory of service account keys created more than 120 days ago. What should you do?  

- **A.** Execute the gcloud kms keys list --filter="createTime &lt; [DATE_120_DAYS_AGO]" command.
- **B.** Execute the gcloud iam service-accounts list --filter="createTime &lt; [DATE_120_DAYS_AGO]" command.
- **C.** Execute the gcloud asset search-all-resources --scope="organizations/[ORGANIZATION_ID]" --query="createTime &lt; [DATE_120_DAYS_AGO]" --asset-types="iam.googleapis.com/ServiceAccountKey" --order-by="createTime" command.
- **D.** Execute the gcloud asset search-all-resources --scope="organizations/[ORGANIZATION_ID]" --query="createTime &lt; [DATE_120_DAYS_AGO]" --asset-types="apikeys.googleapis.com/Key" --order-by="createTime" command.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because gcloud kms keys list queries resources managed by Cloud Key Management Service, such as cryptographic keys contained in Cloud KMS key rings. Cloud KMS keys are used for encryption, decryption, signing, and related cryptographic operations; they are not IAM service account keys used by external applications to authenticate to Google Cloud APIs. In addition, this command normally operates within a specific Cloud KMS location and key ring rather than searching all IAM service account keys throughout an organization. Filtering the creation time of Cloud KMS keys would therefore produce an inventory of the wrong resource type.

**B is incorrect** because gcloud iam service-accounts list returns service account identities, not the keys associated with those service accounts. The createTime filter would identify service accounts created before the specified date, but the age of a service account does not indicate the age of its keys. For example, a service account created several years ago might have a key created only a week ago, while a newer service account might still have its original key. Auditing hundreds of accounts by first listing the accounts and then separately listing every account’s keys would also require additional scripting and significantly more administrative effort.

**C is correct** because Cloud Asset Inventory can search resources across an entire organization and supports IAM service account keys as the iam.googleapis.com/ServiceAccountKey asset type. The organization scope searches accessible resources in projects and folders beneath that organization, providing a centralized inventory instead of requiring a separate query for every project or service account. The createTime query restricts the results to keys created before the calculated cutoff date, and --order-by="createTime" arranges the results by age, making the oldest keys easier to review first. This directly satisfies the requirement to identify service account keys older than the required rotation period. The administrator running the command must have permission to search resources at the organization scope, such as cloudasset.assets.searchAllResources. After identifying old keys, the organization should determine whether each key is still required and used before disabling, rotating, or deleting it. For applications running on-premises or in other clouds, Google recommends migrating from long-lived service account keys to Workload Identity Federation where possible because federation uses short-lived credentials and reduces the risks and operational burden associated with key storage and rotation.

**D is incorrect** because apikeys.googleapis.com/Key represents API keys managed by the API Keys API, not private keys belonging to IAM service accounts. API keys generally identify a calling project or application for API usage and quota purposes, whereas service account keys authenticate a workload as a service account and allow it to obtain OAuth 2.0 credentials. Although Cloud Asset Inventory can search both resource categories, selecting apikeys.googleapis.com/Key would return API key resources and omit the iam.googleapis.com/ServiceAccountKey resources that the security team needs to audit.

**Reference links**

- [docs.cloud.google.com/asset-inventory/docs/search-resources](https://docs.cloud.google.com/asset-inventory/docs/search-resources)
- [docs.cloud.google.com/sdk/gcloud/reference/asset/search-all-resources](https://docs.cloud.google.com/sdk/gcloud/reference/asset/search-all-resources)
- [docs.cloud.google.com/iam/docs/key-rotation](https://docs.cloud.google.com/iam/docs/key-rotation)

**Related notes:** [Cloud Asset Inventory](../02-identity-security/products/cloud-asset-inventory.md)

</details>

[Back to index](#index)

---

### Q18

> BlueHarbor Financial operates Windows-based workloads in multiple Google Cloud projects. Its security team must centrally deny inbound RDP connections on TCP port 3389 from all public internet addresses, including for projects created in the future. Application teams should retain control of less restrictive, workload-specific firewall rules within their projects. Which solution should the security team implement?  

- **A.** Create a VPC firewall deny rule separately in every existing project
- **B.** Attach a Cloud Armor security policy to each internet-facing application
- **C.** Associate an organization-level hierarchical firewall policy with the Google Cloud organization
- **D.** Configure a Cloud NAT gateway in every region used by the organization

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because VPC firewall rules are configured for individual VPC networks rather than being inherited automatically by every project and network in an organization. Creating a deny rule in each existing project would require the security team to identify every applicable VPC network, deploy the rule repeatedly, and continuously monitor for newly created projects and networks. A future project could temporarily or permanently lack the required rule if the central team’s deployment process did not detect it. Project administrators might also have permissions that allow them to modify or remove a locally managed rule. Although automation could reduce the administrative work, separate project-level VPC firewall rules do not provide the same centrally inherited organizational guardrail as a hierarchical firewall policy.

**B is incorrect** because Cloud Armor protects supported applications behind external Application Load Balancers and primarily evaluates HTTP, HTTPS, and certain other proxied application traffic. RDP uses TCP port 3389 and commonly connects directly to the external IP address of a Windows virtual machine. Such direct RDP traffic does not pass through a typical Cloud Armor-protected HTTP or HTTPS load-balancing path. Attaching a Cloud Armor policy to every application would therefore neither create an organization-wide network firewall control nor reliably block RDP access to virtual machines. It would also require configuration for each application and would not automatically protect future projects.

**C is correct** because a hierarchical firewall policy can be associated with the organization resource and inherited by the folders, projects, and VPC networks beneath it. The security team can create a high-priority ingress deny rule that blocks TCP port 3389 from the public source range 0.0.0.0/0. Because the policy is attached at the organization level, the rule applies consistently to current resources and to projects and VPC networks created later within the organization. Application teams can still manage lower-level hierarchical policies, network firewall policies, or VPC firewall rules for traffic that is not conclusively allowed or denied by the organization-level rules. The central policy can use appropriate rule priorities and goto_next behavior for other traffic, allowing evaluation to continue to lower-level rules while retaining an authoritative organization-wide RDP denial. This creates the required security guardrail without forcing the central team to manage every application-specific firewall decision.

**D is incorrect** because Cloud NAT provides outbound network address translation for resources that do not have external IP addresses. It enables supported resources to initiate outbound connections and receive the corresponding return traffic, but it does not permit unsolicited inbound connections from the internet and is not an inbound firewall enforcement mechanism. Deploying Cloud NAT in every region would not create a centrally inherited rule that explicitly denies TCP port 3389 across all projects. Cloud NAT can reduce the need to assign external IP addresses to workloads, which can indirectly reduce exposure, but it does not satisfy the requirement to enforce an organization-wide RDP prohibition while allowing teams to manage their other firewall rules.

**Reference links**

- [docs.cloud.google.com/firewall/docs/firewall-policies](https://docs.cloud.google.com/firewall/docs/firewall-policies)
- [docs.cloud.google.com/armor/docs/cloud-armor-overview](https://docs.cloud.google.com/armor/docs/cloud-armor-overview)
- [docs.cloud.google.com/nat/docs/overview](https://docs.cloud.google.com/nat/docs/overview)

**Related notes:** [Firewall, Hierarchical Policies, and Secure Tags (Cloud NGFW)](../06-networking/products/firewall-hierarchical-policies-and-secure-tags.md)

</details>

[Back to index](#index)

---

### Q19

> Northwind Analytics has configured an egress firewall rule to deny connections from its Compute Engine workloads to a protected subnet. The network administrator must verify that the deny rule is being triggered and determine which source virtual machine instances are attempting the blocked connections. Which feature should the administrator enable?  

- **A.** Cloud Trace
- **B.** Data Access audit logs
- **C.** Cloud Profiler
- **D.** VPC firewall rules logging

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Cloud Trace is an application-performance diagnostics service that collects and analyzes distributed request latency data. It helps developers understand how requests propagate through services and identify slow application operations. It does not record whether VPC firewall rules allow or deny network connections, and it does not identify the Compute Engine instances whose packets matched a particular firewall rule. Therefore, enabling Cloud Trace would not confirm that the egress deny rule is being triggered.

**B is incorrect** because Data Access audit logs record API operations that read resource configuration, metadata, or user-provided data. For example, they can show that a user or service account called a Google Cloud API to access a resource. They do not capture individual network connections evaluated by VPC firewall rules. Although audit logs might show administrative operations performed on a firewall rule, they do not show whether workload traffic matched that rule or which source instances generated the matching packets.

**C is incorrect** because Cloud Profiler continuously analyzes the resource consumption of application code, such as CPU time, memory allocation, and execution behavior. It is intended to locate performance bottlenecks within supported applications. Cloud Profiler does not monitor VPC packet filtering, record firewall rule matches, or provide source and destination network connection details. It therefore cannot verify whether the outbound deny rule is affecting specific instances.

**D is correct** because VPC firewall rules logging creates a connection record whenever traffic matches a firewall rule for which logging is enabled. For a deny rule, the resulting records confirm that connections were denied by that specific rule. The records can include the source and destination IP addresses, source and destination ports, protocol, timestamp, disposition, firewall rule reference, and relevant instance metadata. The administrator can query these records in Cloud Logging to verify that the rule is matching traffic and identify the source Compute Engine instances attempting to reach the restricted network. Logging should be enabled directly on the applicable firewall rule, and metadata should be included when instance-identification details are required.

**Reference links**

- [docs.cloud.google.com/firewall/docs/vpc-firewall-rules-logging-overview](https://docs.cloud.google.com/firewall/docs/vpc-firewall-rules-logging-overview)
- [docs.cloud.google.com/firewall/docs/vpc-log-format](https://docs.cloud.google.com/firewall/docs/vpc-log-format)
- [docs.cloud.google.com/firewall/docs/manage-vpc-firewall-rules-logging](https://docs.cloud.google.com/firewall/docs/manage-vpc-firewall-rules-logging)

**Related notes:** [Firewall Rules Logging and VPC Flow Logs](../06-networking/products/firewall-rules-logging-and-vpc-flow-logs.md)

</details>

[Back to index](#index)

---

### Q20

> PulseCart operates a retail analytics platform that continuously streams transaction records into BigQuery. The company’s analytics team needs to write and execute its own GoogleSQL queries against the most recently ingested records. What should PulseCart do?  

- **A.** Create a Looker Studio report that connects to the relevant BigQuery tables, and grant the analytics team view access to the report.
- **B.** Create one service account for the analytics team, and distribute a separate copy of its private key to every analyst.
- **C.** Use Cloud Scheduler to periodically start a batch Dataflow job that copies the BigQuery data into the analytics team’s on-premises data warehouse.
- **D.** Grant the BigQuery User IAM role to a Google Group containing all members of the analytics team.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a Looker Studio report provides dashboards, charts, filters, and other predefined visualizations, but view access to the report does not give analysts permission to open the BigQuery query editor and execute arbitrary custom GoogleSQL queries. Looker Studio can connect to BigQuery and display recently available data, subject to connector and caching behavior, but report viewers generally interact with the report configuration created by its author. This option therefore provides data visualization rather than the requested direct, self-service SQL access.

**B is incorrect** because service accounts are intended primarily for applications, virtual machines, automated processes, and other workloads rather than for representing a group of human users. Sharing a service account across the BI team would prevent clear attribution because BigQuery jobs would appear to originate from the same service account instead of the individual analysts. Distributing private service account keys also creates a serious security risk: keys can be copied, leaked, or retained after a user leaves the team, and each key holder receives all permissions granted to the service account. Human users should authenticate with their own identities and receive access through IAM groups.

**C is incorrect** because exporting the data to another warehouse does not give the analytics team direct access to the latest information in BigQuery. A periodically scheduled batch job introduces delay between ingestion into BigQuery and availability in the internal warehouse. It also creates duplicate storage, additional processing costs, another pipeline to operate, and possible synchronization failures. BigQuery already supports interactive SQL queries against streamed data, so copying the data elsewhere is unnecessary for this requirement.

**D is correct** because granting an IAM role to a Google Group is the appropriate scalable method for authorizing a team of human users. Membership can be managed centrally, each analyst continues to use an individual identity, and Cloud Audit Logs can attribute query activity to the user who performed it. The BigQuery User role includes permission to create BigQuery jobs, including query jobs, in the project. Strictly applying current least-privilege guidance, the users must also have permission to read the referenced tables, usually through the BigQuery Data Viewer role on the appropriate dataset or tables. The more narrowly scoped BigQuery Job User role is now commonly used for query-job creation, but among the listed choices, assigning BigQuery User to the team’s Google Group is the correct approach, assuming the required dataset-level read access already exists or is granted separately.

**Reference links**

- [docs.cloud.google.com/bigquery/docs/access-control](https://docs.cloud.google.com/bigquery/docs/access-control)
- [docs.cloud.google.com/bigquery/docs/running-queries](https://docs.cloud.google.com/bigquery/docs/running-queries)
- [docs.cloud.google.com/iam/docs/best-practices-service-accounts](https://docs.cloud.google.com/iam/docs/best-practices-service-accounts)

</details>

[Back to index](#index)

---

### Q21

> Northstar Health is rebuilding its internal appointment-processing platform as containerized microservices. The services must be accessible only from the company’s VPC network, and the engineering team does not want to manage Kubernetes nodes, scaling, or infrastructure maintenance. Which deployment approach should the company use?  

- **A.** Create a Google Kubernetes Engine (GKE) cluster in Autopilot mode.
- **B.** Create multiple Compute Engine virtual machines and install and operate Kubernetes on them.
- **C.** Create a regional Google Kubernetes Engine (GKE) cluster in Standard mode.
- **D.** Create a zonal Google Kubernetes Engine (GKE) cluster in Standard mode.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because GKE Autopilot provides the lowest-management Kubernetes option among the choices. In Autopilot mode, Google Cloud manages the cluster’s underlying infrastructure, including worker nodes, node provisioning, scaling, many security configurations, and infrastructure maintenance. The application team can concentrate on Kubernetes workloads and services instead of sizing, configuring, upgrading, and monitoring node pools. Autopilot clusters are regional, providing a highly available control plane without requiring the company to configure a regional Standard cluster manually. Using Autopilot does not require applications to be publicly accessible. The company can keep the microservices private by using ClusterIP Services for communication inside the cluster, internal LoadBalancer Services for access from the VPC network, or an internal Application Load Balancer through internal Ingress. Public exposure is controlled by the workload’s networking configuration and is not an automatic consequence of using Autopilot.

**B is incorrect** because installing Kubernetes on Compute Engine instances creates a self-managed Kubernetes environment. The company would be responsible for provisioning virtual machines, configuring the Kubernetes control plane and worker nodes, managing availability, installing networking components, applying security patches, performing upgrades, replacing failed nodes, configuring autoscaling, and monitoring the entire platform. Although the applications could be placed on private IP addresses, this option creates the greatest management and operational burden and does not satisfy the requirement to minimize infrastructure administration.

**C is incorrect** because a regional GKE Standard cluster offers strong availability, but it requires more operational management than Autopilot. Google Cloud manages the GKE control plane, but the company remains responsible for configuring and managing node pools, machine types, node scaling settings, upgrade strategies, capacity planning, and several infrastructure-level controls. A regional Standard cluster would be appropriate when the company needs detailed control over nodes or requires workload configurations that are not suitable for Autopilot. However, no such requirement exists in this scenario, so Standard mode introduces unnecessary administrative work.

**D is incorrect** because a zonal GKE Standard cluster combines the additional node-management responsibilities of Standard mode with lower control-plane availability than a regional cluster. A zonal cluster’s control plane operates in a single zone, making it less resilient to a zonal disruption. The company would also need to manage node pools, scaling, upgrades, and capacity. Although private applications can run on a zonal Standard cluster, it does not provide the operational simplicity of Autopilot and is less suitable for a production microservices platform that should remain highly available.

**Reference links**

- [cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview](https://cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview)
- [cloud.google.com/kubernetes-engine/docs/concepts/cluster-architecture](https://cloud.google.com/kubernetes-engine/docs/concepts/cluster-architecture)
- [cloud.google.com/kubernetes-engine/docs/how-to/internal-load-balancing](https://cloud.google.com/kubernetes-engine/docs/how-to/internal-load-balancing)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q22

> PixelForge Labs is developing a web platform that automatically creates animated product previews. Its model uses custom CUDA kernels, and the processing pipeline performs NVIDIA GPU-accelerated 3D rendering. The company wants to move the existing application to Google Cloud without rewriting the CUDA code or changing the rendering engine. Which compute option should it choose?  

- **A.** Run the workload on a Compute Engine instance equipped with a compatible NVIDIA GPU
- **B.** Run the workload on a TPU-only node pool in Google Kubernetes Engine
- **C.** Run the workload on an E2 Compute Engine instance without an accelerator
- **D.** Deploy the workload as a Cloud Run function and configure maximum request concurrency

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a Compute Engine instance with a compatible NVIDIA GPU directly supports workloads that depend on NVIDIA CUDA libraries. CUDA applications are designed to execute on compatible NVIDIA GPUs, so the team can preserve its existing CUDA kernels, machine-learning libraries, and GPU rendering components with minimal modification. Compute Engine provides multiple GPU machine families and NVIDIA GPU models for machine learning, scientific computing, visualization, and graphics-intensive workloads. The team can select a GPU model that supports its required CUDA version, install the appropriate NVIDIA driver and CUDA toolkit, and run the training and rendering software inside a familiar virtual machine environment. Compute Engine also gives the team control over the operating system, drivers, libraries, storage, networking, and long-running processes. This makes it the most direct migration option when both CUDA compatibility and general-purpose GPU rendering are mandatory.

**B is incorrect** because Cloud TPU hardware is not an interchangeable replacement for an NVIDIA GPU. TPUs are Google-designed application-specific accelerators optimized primarily for supported machine-learning operations and frameworks. A TPU does not execute CUDA code because CUDA is an NVIDIA-specific programming platform. Migrating custom CUDA kernels to TPUs would require the team to rewrite or replace those components with TPU-compatible implementations, such as operations supported through TensorFlow, JAX, or PyTorch/XLA. In addition, a TPU-only GKE node pool would not satisfy the GPU-based rendering requirement because TPUs are not general-purpose graphics processors and are not intended to run CUDA rendering engines. GKE can provide NVIDIA GPU node pools, but the option specifically proposes a TPU-only node pool, so it does not meet the workload’s compatibility requirements.

**C is incorrect** because the E2 machine series does not provide the NVIDIA GPU acceleration required by the application. An E2 instance without an accelerator can execute CPU-based application components, but it cannot run CUDA kernels because CUDA requires a supported NVIDIA GPU and driver. The machine-learning workload would either fail to initialize its CUDA-dependent libraries or fall back to CPU execution if the software supports such a fallback. CPU execution would typically be unsuitable for a workload explicitly designed for accelerated model training and GPU rendering. Additionally, E2 machine types do not support attaching GPUs, so the team could not later add an NVIDIA accelerator to the selected E2 instance. Choosing this option would require substantial application changes or a different machine type.

**D is incorrect** because increasing Cloud Run concurrency controls how many requests a single instance can process simultaneously; it does not automatically provide an accelerator or make a CUDA-dependent workload compatible with the environment. Cloud Run functions are designed for event-driven or request-driven serverless execution rather than serving as general-purpose virtual machines for complex model training and GPU rendering pipelines. Although Cloud Run services can support selected NVIDIA GPUs in supported configurations, this option only proposes a Cloud Run function with maximum concurrency and does not specify a compatible GPU configuration. Maximum concurrency could also cause several resource-intensive operations to compete for the same CPU, memory, or GPU resources. It does not solve the requirement for CUDA compatibility, unrestricted driver and library control, or a rendering environment. Compute Engine with an NVIDIA GPU remains the more appropriate choice for minimal code changes and full control over the execution stack.

**Reference links**

- [docs.cloud.google.com/compute/docs/gpus](https://docs.cloud.google.com/compute/docs/gpus)
- [docs.cloud.google.com/compute/docs/gpus/install-drivers-gpu](https://docs.cloud.google.com/compute/docs/gpus/install-drivers-gpu)
- [docs.cloud.google.com/tpu/docs/intro-to-tpu](https://docs.cloud.google.com/tpu/docs/intro-to-tpu)

**Related notes:** [Compute Engine](../03-compute-containers/products/compute-engine.md) · [Cloud TPU and GPU](../03-compute-containers/products/cloud-tpu-and-gpu.md)

</details>

[Back to index](#index)

---

### Q23

> ParcelPilot operates an on-premises shipment-tracking platform composed of several Python microservices. Each microservice is packaged as a Docker container, and runtime settings such as database addresses and service URLs are supplied through environment variables. The company wants to migrate the existing application to a fully managed serverless Google Cloud platform while minimizing code and build-process changes. What should the team do?  

- **A.** Continue using the existing CI/CD pipeline, deploy the generated container images as Cloud Run services, and update the environment variables and service endpoints for Google Cloud.
- **B.** Continue using the existing CI/CD pipeline, deploy the generated container images as Cloud Run functions, and retain all on-premises configuration values.
- **C.** Deploy the source code of every microservice as an independent Cloud Run function, and update the environment variables and service endpoints.
- **D.** Deploy the existing source code of every microservice as an independent Cloud Run service, and retain all on-premises configuration values.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Cloud Run services are designed to execute containerized applications in a fully managed serverless environment. The microservices are already packaged as Docker container images, so the team can preserve the existing application architecture and continue using most of its CI/CD process. The pipeline can build the images, store them in a supported container registry such as Artifact Registry, and deploy each image as a separate Cloud Run service. Cloud Run automatically handles infrastructure provisioning, request-based scaling, load balancing, health management, and, when configured appropriately, scaling to zero. The containers must comply with the Cloud Run container runtime contract, including listening for requests on the port supplied through the PORT environment variable and not depending on persistent local storage. The team must also replace on-premises configuration values with cloud-appropriate values. For example, internal service addresses must be changed to the HTTPS URLs or private endpoints assigned to the Cloud Run services, database connection information may need to reference a Google Cloud database or network path, and authentication between services may need to use service accounts and identity tokens. Cloud Run supports injecting environment variables into containers, so the application’s existing configuration pattern can still be used even though the actual values and endpoints must be updated.

**B is incorrect** because Cloud Run functions are intended for function-oriented, event-driven units of code rather than for directly migrating an existing collection of independently designed application containers. A Cloud Run function deployment normally starts from function source code, identifies a function entry point, uses the Functions Framework, and builds the source into a container as part of the deployment process. An arbitrary prebuilt microservice image produced by the existing CI/CD pipeline is more naturally deployed as a Cloud Run service. This option is also incorrect because retaining all on-premises configuration values would generally prevent the migrated services from reaching their dependencies. On-premises hostnames, private IP addresses, database addresses, and service URLs might not be valid or reachable from Cloud Run. Even when connectivity to on-premises resources is intentionally preserved through hybrid networking, the configuration, networking, security, and endpoint requirements must still be reviewed and adjusted.

**C is incorrect** because converting every existing microservice into a Cloud Run function would usually require application refactoring. Each function must expose an appropriate function entry point and follow the supported HTTP or CloudEvent programming model. A complex Python microservice might contain its own web server, routing, middleware, startup logic, background processing, or multiple API paths, none of which necessarily maps cleanly to a single function. Separating such an application into functions could also require changes to dependencies, request handling, state management, testing, deployment, and service communication. Although updating the configurations and endpoints is necessary, this option does not satisfy the goal of migrating the existing containerized application with minimal changes. Deploying the already-built containers as Cloud Run services is the more direct lift-and-modernize approach.

**D is incorrect** because Cloud Run services are deployed from container images or from source code that Google Cloud builds into container images; the wording does not preserve the existing image-based CI/CD workflow as clearly as option A. More importantly, using the same on-premises configurations without modification is inappropriate. Cloud Run services receive their own endpoints, identities, networking context, and runtime settings. Environment variables containing localhost references, private on-premises addresses, fixed ports, internal DNS names, credentials, or service URLs must be reassessed. Each service must typically reference the new Cloud Run endpoints or properly configured private destinations. Sensitive values should also be stored in Secret Manager rather than embedded as ordinary configuration values. Therefore, deploying to Cloud Run is appropriate, but retaining the on-premises configuration unchanged makes this option unsuitable.

**Reference links**

- [docs.cloud.google.com/run/docs/deploying](https://docs.cloud.google.com/run/docs/deploying)
- [docs.cloud.google.com/run/docs/configuring/services/environment-variables](https://docs.cloud.google.com/run/docs/configuring/services/environment-variables)
- [docs.cloud.google.com/run/docs/container-contract](https://docs.cloud.google.com/run/docs/container-contract)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md)

</details>

[Back to index](#index)

---

### Q24

> BluePeak Analytics runs a reporting service on a Compute Engine virtual machine. The service needs secure read access to the customer_metrics BigQuery dataset and must not access other datasets in the project. BluePeak wants the application to use automatically generated short-lived credentials while avoiding frequent identity changes and unnecessary administration. What should BluePeak Analytics do?  

- **A.** Attach a newly created service account to the virtual machine every 45 minutes, and grant it the BigQuery Data Viewer IAM role on the project.
- **B.** Attach a dedicated custom service account to the virtual machine, and grant it the BigQuery Data Viewer IAM role on the customer_metrics dataset.
- **C.** Attach a newly created service account to the virtual machine every 45 minutes, and grant it the BigQuery Data Viewer IAM role on the customer_metrics dataset.
- **D.** Attach a dedicated custom service account to the virtual machine, and grant it the BigQuery Data Viewer IAM role on the project.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because granting the BigQuery Data Viewer role at the project level gives the service account read access to BigQuery datasets and related resources throughout the project rather than limiting access to the intended customer_metrics dataset. This violates the principle of least privilege. Creating and attaching a new service account every 45 minutes is also unnecessary and operationally expensive. An application running on a Compute Engine instance can use Application Default Credentials to obtain automatically generated, short-lived OAuth access tokens for the service account attached to the instance. Therefore, service account rotation is not required to obtain short-lived credentials.

**B is correct** because attaching a dedicated custom service account to the Compute Engine instance is the Google-recommended method for allowing a workload on the instance to authenticate to Google Cloud APIs. Application Default Credentials can obtain short-lived access tokens for the attached service account from the Compute Engine metadata server, so the company does not need to create, distribute, rotate, or store service account keys. Granting the BigQuery Data Viewer role directly on the customer_metrics dataset limits the service account’s data-reading permissions to that dataset and follows the principle of least privilege. The same custom service account can remain attached to the instance while its access tokens are automatically refreshed. If the application submits query jobs, it might also require a narrowly assigned role containing the bigquery.jobs.create permission, such as BigQuery Job User at the appropriate project level, but the dataset’s data access should remain restricted through the dataset-level BigQuery Data Viewer role.

**C is incorrect** because granting BigQuery Data Viewer at the dataset level correctly restricts data access to the intended dataset, but creating and attaching a new service account every 45 minutes is unnecessary. The lifetime of a service account identity is separate from the lifetime of the credentials issued for that identity. A long-lived custom service account attached to a Compute Engine instance can receive short-lived access tokens from the metadata server. Continuously creating service accounts would increase IAM administration, consume service account quota, complicate auditing, and require repeated updates to the VM and dataset IAM policy without providing a meaningful security benefit.

**D is incorrect** because using a dedicated custom service account attached to the instance is appropriate and allows the application to receive short-lived credentials automatically. However, granting the BigQuery Data Viewer role at the project level is broader than required. Project-level permissions are inherited by eligible BigQuery resources within the project, which could allow the application to read data from datasets other than customer_metrics. Granting the role directly on the intended dataset provides more granular authorization and better satisfies the requirement that the application access only that dataset.

**Reference links**

- [cloud.google.com/compute/docs/access/authenticate-workloads](https://cloud.google.com/compute/docs/access/authenticate-workloads)
- [cloud.google.com/bigquery/docs/control-access-to-resources-iam](https://cloud.google.com/bigquery/docs/control-access-to-resources-iam)
- [cloud.google.com/iam/docs/best-practices-service-accounts](https://cloud.google.com/iam/docs/best-practices-service-accounts)

</details>

[Back to index](#index)

---

### Q25

> PayWave Retail is replacing its VM-based order settlement platform with a serverless architecture. New settlement requests must be accepted quickly and processed asynchronously, and the platform must automatically scale during traffic spikes with minimal infrastructure administration. What should PayWave Retail do?  

- **A.** Run Apache Kafka on Compute Engine instances to receive settlement requests, and use Cloud Run to process them.
- **B.** Use Pub/Sub to receive settlement requests, and use Compute Engine instances to process them.
- **C.** Use Pub/Sub to receive settlement requests, and use Cloud Run to process them.
- **D.** Run Apache Kafka on Compute Engine instances to receive settlement requests, and use Compute Engine instances to process them.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Cloud Run provides a serverless and scalable processing environment, but operating Apache Kafka on Compute Engine instances requires PayWave Retail to provision and maintain virtual machines, configure Kafka brokers, manage storage, perform upgrades, monitor cluster health, handle broker failures, and plan capacity. This means the overall architecture would not be fully serverless and would retain significant operational overhead. A self-managed Kafka deployment might be suitable when an organization requires Kafka-specific functionality, but it does not satisfy the requirement to minimize infrastructure management.

**B is incorrect** because Pub/Sub is an appropriate fully managed service for accepting and buffering transaction messages asynchronously. It decouples transaction producers from transaction processors and can scale as message volume changes. However, processing the transactions on Compute Engine instances would require the company to manage virtual machines, instance templates, operating-system patches, scaling policies, capacity, and availability. Even when a managed instance group is used, the processing tier remains VM-based rather than fully serverless. Therefore, this option satisfies the asynchronous messaging requirement but not the requirement to migrate the application to a serverless architecture with minimal management overhead.

**C is correct** because Pub/Sub and Cloud Run are both fully managed Google Cloud services that support an asynchronous, serverless, and scalable transaction-processing architecture. The application can publish each settlement request as a message to a Pub/Sub topic, allowing the request to be accepted independently of the processing service. A Pub/Sub subscription can then deliver messages to a Cloud Run service, directly through a push subscription or through an event-driven integration such as Eventarc. Cloud Run automatically creates service instances as requests arrive and can scale down when demand decreases, eliminating the need to provision or administer worker virtual machines. The processor should acknowledge a message only after completing the transaction successfully. If processing fails or the acknowledgement is not completed, Pub/Sub can redeliver the message. Because redelivery is possible, the transaction-processing logic should be idempotent so that processing the same message more than once does not create duplicate financial or business outcomes.

**D is incorrect** because both components require the company to manage virtual-machine infrastructure. PayWave Retail would be responsible for deploying and operating Kafka brokers as well as provisioning, patching, scaling, monitoring, and maintaining the Compute Engine instances that process transactions. Although Kafka can support asynchronous messaging, this design is neither serverless nor the lowest-management option. It preserves most of the operational responsibilities associated with the existing VM-based architecture and therefore does not meet the migration objectives.

**Reference links**

- [docs.cloud.google.com/pubsub/docs/overview](https://docs.cloud.google.com/pubsub/docs/overview)
- [docs.cloud.google.com/run/docs/overview/what-is-cloud-run](https://docs.cloud.google.com/run/docs/overview/what-is-cloud-run)
- [docs.cloud.google.com/run/docs/tutorials/pubsub](https://docs.cloud.google.com/run/docs/tutorials/pubsub)

</details>

[Back to index](#index)

---

### Q26

> HarborLink Logistics operates several legacy warehouse applications that exchange documents through a shared NFS file server. The company wants to replace the server with a fully managed Google Cloud service while preserving the applications’ existing file-system access patterns and minimizing code changes. What should HarborLink Logistics do?  

- **A.** Create a Compute Engine instance, configure it as an NFS server, and redirect the applications’ NFS mounts to the instance.
- **B.** Create a Filestore instance and update the applications’ NFS mount configurations to use the Filestore file share.
- **C.** Create a Firestore database and modify the applications to store and retrieve their shared files as Firestore documents.
- **D.** Create a Cloud Storage bucket and modify the applications to access shared files by using Cloud Storage client libraries.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because configuring an NFS server on a Compute Engine instance would preserve the applications’ existing NFS access method, but it would not provide a fully managed file-storage service. HarborLink Logistics would remain responsible for configuring the operating system and NFS software, applying patches, monitoring storage capacity, implementing backups, managing availability, replacing failed instances, and planning disaster recovery. Additional infrastructure would also be necessary to eliminate the single point of failure created by one NFS server. This option modernizes the server location but does not meaningfully reduce management overhead.

**B is correct** because Filestore provides fully managed NFS file servers on Google Cloud. Legacy applications that already use NFS can mount a Filestore file share and continue accessing files through familiar file-system paths and NFS operations. The primary application-side change is updating the NFS mount target to the Filestore instance’s IP address and file-share name. Applications generally do not need to be redesigned to use database APIs or object-storage client libraries. Google Cloud manages the underlying file-server infrastructure, making Filestore the option that provides NFS compatibility while requiring the least application change.

**C is incorrect** because Firestore is a managed NoSQL document database rather than an NFS-compatible shared file system. The legacy applications could not mount Firestore as an NFS file share. Developers would need to redesign the applications’ storage logic, convert files and file metadata into an appropriate document-based data model, integrate Firestore client libraries, and replace normal file operations with database operations. Firestore can be appropriate for structured application data requiring scalable document queries, but it does not provide a low-change migration path for workloads that depend on shared NFS storage.

**D is incorrect** because Cloud Storage is an object-storage service rather than a traditional NFS file system. Applications normally interact with objects in buckets through client libraries, REST APIs, command-line tools, or other supported interfaces. Migrating the applications to Cloud Storage client libraries would require changes to their file-access logic and potentially their handling of directories, file updates, locking, renaming, and concurrent access. Cloud Storage is highly scalable and managed, but replacing NFS operations with object-storage operations would require substantially more application modification than mounting a Filestore file share.

**Reference links**

- [docs.cloud.google.com/filestore/docs/overview](https://docs.cloud.google.com/filestore/docs/overview)
- [docs.cloud.google.com/filestore/docs/about-supported-protocols](https://docs.cloud.google.com/filestore/docs/about-supported-protocols)
- [docs.cloud.google.com/storage/docs/objects](https://docs.cloud.google.com/storage/docs/objects)

**Related notes:** [Filestore](../05-storage-databases-data/products/filestore.md)

</details>

[Back to index](#index)

---

### Q27

> QuickBite Delivery has built an online food-ordering platform composed of separate catalog, payment, ordering, and notification microservices. Each microservice is packaged in its own Docker container image. The company wants to run the platform on Google Kubernetes Engine and independently adjust the number of replicas for each microservice based on its workload. What should the company do?  

- **A.** Create and deploy a Custom Resource Definition for each microservice.
- **B.** Create and deploy one Docker Compose file containing all the microservices.
- **C.** Create and deploy a Kubernetes Job for each microservice.
- **D.** Create and deploy a Kubernetes Deployment for each microservice.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a Custom Resource Definition extends the Kubernetes API by introducing a new resource type with a custom name and schema. CRDs are commonly used when building Kubernetes operators or implementing specialized resources that Kubernetes does not provide natively. They are not required to deploy ordinary containerized microservices. Creating one CRD for each microservice would add unnecessary complexity because Kubernetes already provides standard workload resources, including Deployments, for running and scaling long-lived applications. A CRD would also require additional controller logic if the custom resource were expected to manage Pods automatically.

**B is incorrect** because Docker Compose is primarily designed to define and run multi-container applications in Docker environments, especially for local development and testing. A Docker Compose file is not a native Kubernetes workload resource that can be deployed directly to GKE in the same way as a Deployment manifest. Even if the Compose configuration were converted into Kubernetes manifests, defining the application as one combined Compose project would not be the most appropriate way to provide independent Kubernetes lifecycle management, rolling updates, replica control, and autoscaling for every microservice. Each independently scalable microservice should have its own Kubernetes workload definition.

**C is incorrect** because a Kubernetes Job is designed for finite workloads that perform a task and then terminate successfully. Jobs are suitable for activities such as batch processing, data migrations, report generation, and one-time administrative operations. The application’s microservices are long-running services that must remain available to process customer requests continuously. A Job would attempt to complete the workload rather than continuously maintain the desired number of running application replicas, making it unsuitable for hosting these microservices.

**D is correct** because a Kubernetes Deployment manages a replicated set of Pods for a long-running application and continuously works to maintain the declared number of replicas. The company should create a separate Deployment for each microservice, with each Deployment referencing that microservice’s Docker container image. This separation allows the catalog, payment, ordering, and notification services to be deployed, updated, restarted, and scaled independently. The company can manually change each Deployment’s replica count or associate a separate HorizontalPodAutoscaler with each Deployment so that replicas increase or decrease according to metrics such as CPU utilization, memory utilization, or application-specific metrics. Deployments also support controlled rollouts and rollbacks, making them the standard Kubernetes resource for managing stateless microservices on GKE.

**Reference links**

- [kubernetes.io/docs/concepts/workloads/controllers/deployment/](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)
- [kubernetes.io/docs/concepts/workloads/controllers/job/](https://kubernetes.io/docs/concepts/workloads/controllers/job/)
- [kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/)

</details>

[Back to index](#index)

---

### Q28

> AsterPeak Manufacturing is migrating its global supply-chain planning platform to Google Cloud. The platform uses an in-memory database that loads its entire operational dataset into RAM to provide rapid forecasting and inventory calculations. You need to select the most appropriate Compute Engine resources for this memory-intensive production workload. What should you do?  

- **A.** Provision Compute Engine Spot VMs.
- **B.** Provision Compute Engine instances with GPUs attached.
- **C.** Provision Compute Engine instances with Local SSD disks attached.
- **D.** Provision Compute Engine instances from the M1 memory-optimized machine series.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Spot VMs provide discounted Compute Engine capacity that Google Cloud can stop or preempt at any time. They are suitable for fault-tolerant workloads such as batch processing, rendering, testing, and distributed jobs that can tolerate interruptions or restart automatically. A production supply-chain platform running an in-memory database typically requires stable, continuously available compute resources because an unexpected VM termination can interrupt transactions and remove the database contents held in volatile memory. Spot VMs also do not inherently provide the large memory-to-vCPU ratio required by an in-memory database. Although a properly designed database cluster might use replication and automated recovery, choosing interruptible instances for the primary production database would introduce unnecessary availability risk.

**B is incorrect** because GPUs are specialized accelerators designed primarily for workloads that perform highly parallel computations, such as machine learning training, artificial intelligence inference, scientific simulations, graphics rendering, and video processing. Attaching GPUs does not address the platform’s primary requirement, which is enough system memory to hold the entire database. The database needs a VM with a large amount of RAM and a high memory-to-vCPU ratio rather than additional graphics or accelerator memory. Unless the application documentation explicitly requires GPU acceleration, GPUs would increase cost without providing the most appropriate resource configuration for an in-memory relational database.

**C is incorrect** because Local SSD provides high-performance, low-latency block storage, but it is not a replacement for system memory. An application that keeps its complete database in memory requires sufficient RAM to contain the active dataset. Local SSD could improve temporary disk operations, caching, database logging, or spillover processing, but data read from Local SSD is still accessed more slowly than data held directly in RAM. Local SSD data is also ephemeral and can be lost when the VM is stopped, deleted, or affected by certain host events. Therefore, attaching Local SSD disks does not satisfy the fundamental requirement for a very large memory capacity.

**D is correct** because the M1 machine series belongs to the Compute Engine memory-optimized machine family and provides substantially higher memory capacity and memory-to-vCPU ratios than typical general-purpose machine types. M1 instances can provide up to approximately 4 TB of memory and are designed for workloads such as medium-sized in-memory databases, SAP HANA, in-memory analytics, business warehousing, and other memory-intensive enterprise applications. This allows the platform to keep its operational database in RAM and deliver the required fast data access. Google Cloud now also offers newer memory-optimized series, including M2, M3, M4, M4N, and X4, which might be considered when sizing a real deployment. However, among the listed options, the M1 memory-optimized machine series is the resource specifically designed to meet the application’s large in-memory database requirement.

**Reference links**

- [cloud.google.com/compute/docs/memory-optimized-machines](https://cloud.google.com/compute/docs/memory-optimized-machines)
- [cloud.google.com/compute/docs/instances/spot](https://cloud.google.com/compute/docs/instances/spot)
- [cloud.google.com/compute/docs/disks/local-ssd](https://cloud.google.com/compute/docs/disks/local-ssd)

**Related notes:** [Compute Engine](../03-compute-containers/products/compute-engine.md)

</details>

[Back to index](#index)

---

### Q29

> BrightCart runs its catalog, payment, and reporting applications on separate Compute Engine VM instances within one Google Cloud project. Each application requires a different identity and set of IAM permissions when accessing Google Cloud APIs. How should BrightCart configure the VM instances?  

- **A.** Specify the appropriate user-managed service account when creating each VM instance.
- **B.** Store the email address of the appropriate service account as custom metadata on each VM instance.
- **C.** Start each VM instance, and then run gcloud compute instances update to attach the appropriate service account.
- **D.** Start each VM instance, and then use gcloud compute instances update to store the appropriate service account email address as instance metadata.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Compute Engine supports attaching a user-managed service account directly to a VM when the VM is created. Each VM can have one attached service account, so BrightCart can assign a different identity to the catalog, payment, and reporting instances. Applications running on each VM can obtain short-lived credentials for the attached service account from the Compute Engine metadata server and use those credentials to authenticate to Google Cloud APIs. IAM roles granted to each service account determine what its VM application is authorized to do, allowing BrightCart to apply least privilege separately to every workload. The administrator creating the VMs must also have permission to attach the selected service accounts, typically through the Service Account User role. Appropriate access scopes should be configured as well; Google recommends the cloud-platform scope and controlling actual permissions through IAM roles.

**B is incorrect** because custom instance metadata is only user-defined configuration data. Placing a service account name or email address in metadata does not attach that service account to the VM, grant the VM permission to impersonate it, or make its credentials available to applications. Although an application could read the stored text, the value would merely be a string and would not establish an authenticated workload identity. The service account must be configured through the VM’s service account property.

**C is incorrect** because gcloud compute instances update is not the command used to change a VM’s attached service account. An existing VM can be reconfigured to use a different service account, but the VM must first be stopped, and the appropriate command is gcloud compute instances set-service-account with the service account and access scopes specified. Because the requirement is known before deployment, attaching the correct service account during instance creation is simpler and avoids stopping and reconfiguring the VM afterward.

**D is incorrect** because it combines an unsuitable command with an ineffective metadata-based approach. The gcloud compute instances update command does not attach a workload identity merely by recording a service account name as metadata. Custom metadata does not cause Compute Engine to issue credentials for that service account, and applications would continue using whichever service account is actually attached to the VM. To change an existing VM’s identity, BrightCart would need to stop the VM and use gcloud compute instances set-service-account rather than storing the service account name in metadata.

**Reference links**

- [docs.cloud.google.com/compute/docs/access/create-enable-service-accounts-for-instances](https://docs.cloud.google.com/compute/docs/access/create-enable-service-accounts-for-instances)
- [docs.cloud.google.com/compute/docs/access/service-accounts](https://docs.cloud.google.com/compute/docs/access/service-accounts)
- [docs.cloud.google.com/sdk/gcloud/reference/compute/instances/set-service-account](https://docs.cloud.google.com/sdk/gcloud/reference/compute/instances/set-service-account)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q30

> TrendScope Media runs customer-facing services on several Compute Engine instances and needs a scalable way to retain and investigate application logs. Its operations team must analyze the logs by using SQL and create charts that reveal recurring errors and traffic trends over time. The company wants to use Google-managed services and avoid maintaining custom ingestion pipelines. What should TrendScope Media do?  

- **A.** Develop a custom script that sends application logs from the Compute Engine instances directly to BigQuery for analysis.
- **B.** Install the Ops Agent to send application logs to Cloud Logging, and investigate the logs by using Logs Explorer.
- **C.** Install the Ops Agent to send application logs to Cloud Logging, and analyze the logs by using Observability Analytics.
- **D.** Develop a custom script that sends application logs from the Compute Engine instances to Cloud SQL for analysis.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because BigQuery supports SQL analysis and can process large volumes of log data, but building a custom script to send logs directly from each Compute Engine instance creates unnecessary operational work. The company would need to develop and maintain ingestion code, handle authentication, buffer records during failures, retry unsuccessful writes, manage duplicate records, accommodate schema changes, monitor the pipeline, and control streaming ingestion costs. This solution bypasses the managed log-collection capabilities provided by the Ops Agent and Cloud Logging. Exporting or linking Cloud Logging data to BigQuery can be useful when logs must be joined with other business datasets or analyzed through other BigQuery tools, but it is unnecessary when the main requirements are SQL-based log analysis and visualization within Google Cloud Observability.

**B is incorrect** because using the Ops Agent to collect logs from Compute Engine is the recommended ingestion approach, but Logs Explorer does not best satisfy the SQL analysis requirement. Logs Explorer is primarily designed for troubleshooting, filtering, viewing, and interactively investigating individual log entries by using the Logging query language. It includes a timeline and tools for analyzing log fields, but it is not the SQL-based analytics interface intended for aggregating log data and creating detailed charts of patterns and trends. Therefore, the ingestion component is appropriate, but the selected analysis interface does not meet all the stated requirements.

**C is correct** because the Ops Agent is Google Cloud’s primary agent for collecting logs, metrics, and traces from Compute Engine instances. It can collect application log files and send their entries to Cloud Logging without requiring the company to build and operate a custom ingestion pipeline. Observability Analytics, which is the current name for the capability previously called Log Analytics, provides a SQL-based interface for querying and aggregating logs stored in analytics-enabled log buckets. Query results can be displayed as tables or charts, and the visualizations can be saved to custom dashboards for ongoing analysis of patterns and trends. This architecture uses managed ingestion, storage, querying, and visualization capabilities, thereby reducing development effort and operational overhead. It also avoids creating a second copy of the logs in BigQuery unless integration with separate BigQuery datasets or tools is specifically required.

**D is incorrect** because Cloud SQL is a managed relational database service intended primarily for transactional application workloads, not large-scale log ingestion and analytics. The company would still need to design and operate custom scripts that parse log entries, insert them into database tables, retry failed writes, control connection usage, manage schemas, and prevent the ingestion workload from overwhelming the database. As log volume grows, the company would also need to scale the Cloud SQL instance and manage storage and query performance, which could increase costs. Although SQL queries could be executed against the database, Cloud SQL does not provide the purpose-built log exploration and charting experience available through Cloud Logging and Observability Analytics.

**Reference links**

- [docs.cloud.google.com/logging/docs/agent/ops-agent/installation](https://docs.cloud.google.com/logging/docs/agent/ops-agent/installation)
- [docs.cloud.google.com/logging/docs/analyze/query-and-view](https://docs.cloud.google.com/logging/docs/analyze/query-and-view)
- [docs.cloud.google.com/logging/docs/analyze/charts](https://docs.cloud.google.com/logging/docs/analyze/charts)

**Related notes:** [Observability Analytics](../07-operations-cost/products/observability-analytics.md) · [Ops Agent](../07-operations-cost/products/ops-agent.md)

</details>

[Back to index](#index)

---

### Q31

> Northstar Analytics uses an internal deployment tool to create Linux virtual machines in Compute Engine for engineers who run temporary data-processing jobs. You need a centralized way to create and remove Linux access when engineers join, change roles, or leave the company. You want to minimize custom administration and follow Google-recommended security practices. What should you do?  

- **A.** Enable OS Login on all Compute Engine VMs and grant the engineers the appropriate IAM roles.
- **B.** Ask each engineer to generate an SSH public key, and use custom startup scripts to create Linux accounts and maintain their access permissions.
- **C.** Ask each engineer to generate an SSH public key, and configure every key to authenticate directly as the root user.
- **D.** Enable OS Login on all Compute Engine VMs, and use custom startup scripts to create Linux accounts and maintain their access permissions.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because OS Login provides centralized management of SSH access to Linux Compute Engine VMs by associating Linux login identities with users’ Google identities and IAM permissions. Administrators can grant roles such as roles/compute.osLogin for standard user access or roles/compute.osAdminLogin when sudo access is required. When a user’s IAM permissions are changed or removed, the user’s VM login access is updated automatically, which simplifies onboarding, role changes, and offboarding. OS Login can be enabled at the project level so that it applies to all supported VMs, avoiding per-instance account administration. It also supports fine-grained authorization, audit logging, optional two-step verification, and access management through existing Google Cloud identity controls. This approach requires less custom code and ongoing maintenance than manually managing Linux accounts and SSH keys, thereby reducing operational costs.

**B is incorrect** because manually collecting SSH public keys and maintaining Linux users through custom startup scripts creates an unnecessary account-management system. The organization would need to develop, test, secure, monitor, and update the scripts while ensuring that they correctly add users, remove former users, rotate keys, and maintain consistent permissions across every VM. Startup scripts normally run during instance startup, so access changes might not be applied immediately to running VMs unless additional automation is implemented. This approach increases operational effort and creates a risk that obsolete accounts or SSH keys will remain on some instances. OS Login already provides centralized identity and access lifecycle management through IAM, so custom scripts are neither the simplest nor the Google-recommended solution.

**C is incorrect** because configuring developers’ SSH keys for the root account gives them unrestricted administrative access to the operating system and violates the principle of least privilege. It also makes accountability more difficult because multiple developers would authenticate as the same root Linux user rather than using identities associated with their individual Google accounts. Removing a developer’s access would require administrators to locate and remove that developer’s key from every affected VM or metadata configuration. Direct root access also increases the potential impact of credential theft or accidental commands. With OS Login, each developer receives an individually attributable Linux identity, and IAM roles can distinguish between standard login access and administrative login access.

**D is incorrect** because OS Login already manages the Linux account information and authorization required for users to connect to supported Compute Engine VMs. Adding custom startup scripts to create accounts or update permissions duplicates OS Login functionality and introduces additional code that must be maintained. The scripts could also create conflicts between locally managed accounts and OS Login-managed accounts, especially if usernames or user identifiers overlap. Access changes should instead be performed by adding or removing IAM role bindings, allowing OS Login to enforce the updated permissions during login attempts. Using IAM without custom account-management scripts provides a simpler, more reliable, and less expensive operational model.

**Reference links**

- [docs.cloud.google.com/compute/docs/oslogin](https://docs.cloud.google.com/compute/docs/oslogin)
- [docs.cloud.google.com/compute/docs/oslogin/set-up-oslogin](https://docs.cloud.google.com/compute/docs/oslogin/set-up-oslogin)
- [docs.cloud.google.com/compute/docs/access/iam](https://docs.cloud.google.com/compute/docs/access/iam)

**Related notes:** [OS Login](../02-identity-security/products/os-login.md)

</details>

[Back to index](#index)

---

### Q32

> NovaCart, an online retail company, has created a Google Cloud project named novacart-prod by using the Google Cloud CLI and has attached an active billing account. An administrator now wants to create the project’s first Compute Engine VM instance by running the gcloud compute instances create command. Which prerequisite action should the administrator perform?  

- **A.** Create a Cloud Monitoring Workspace for the project.
- **B.** Manually create a VPC network before enabling Compute Engine.
- **C.** Enable the Compute Engine API by enabling compute.googleapis.com.
- **D.** Grant themselves the Compute Admin IAM role.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a Cloud Monitoring Workspace is not required to create a Compute Engine VM instance. Cloud Monitoring can collect metrics, create dashboards, configure alerts, and monitor resources after they are deployed, but creating a monitoring configuration is independent of enabling and using Compute Engine. The VM creation command communicates with the Compute Engine API, so monitoring setup is not a prerequisite.

**B is incorrect** because manually creating a VPC network is not an absolute prerequisite for enabling Compute Engine or creating a VM. A VM must ultimately connect to a VPC network interface, but a new project can have a default VPC network unless default network creation is disabled by an organization policy. An administrator can also create or select a custom VPC network as part of the deployment process. The universally required prerequisite in this situation is enabling the Compute Engine API.

**C is correct** because Compute Engine operations are exposed through the compute.googleapis.com service. Before the Google Cloud CLI can create a VM by using gcloud compute instances create, the Compute Engine API must be enabled in the target project. The administrator can enable it by running gcloud services enable compute.googleapis.com while the correct project is selected. Linking a billing account makes billable resource usage possible, but it does not automatically guarantee that the required API is enabled.

**D is incorrect** because the Compute Admin role is an IAM authorization role rather than a universal service-enablement prerequisite. A user must have sufficient permissions to create the VM, but the project creator commonly already has broader permissions, such as the Owner role, that include the required Compute Engine permissions. Granting an additional Compute Admin role to the same user is therefore not necessarily required. Furthermore, even a user with Compute Admin permissions cannot create Compute Engine resources until the Compute Engine API is enabled. The valid role name is Compute Admin, not Computer Admin.

**Reference links**

- [cloud.google.com/service-usage/docs/enable-disable](https://cloud.google.com/service-usage/docs/enable-disable)
- [cloud.google.com/sdk/gcloud/reference/services/enable](https://cloud.google.com/sdk/gcloud/reference/services/enable)
- [cloud.google.com/sdk/gcloud/reference/compute/instances/create](https://cloud.google.com/sdk/gcloud/reference/compute/instances/create)

**Related notes:** [Compute Engine](../03-compute-containers/products/compute-engine.md)

</details>

[Back to index](#index)

---

### Q33

> BrightCart operates an online retail platform that uses a Google Kubernetes Engine (GKE) cluster and a Cloud SQL database in the same Google Cloud project. The Site Reliability Engineering team needs a specific set of permissions across both services. Existing predefined IAM roles include some required permissions but also contain permissions that the team does not need. You must grant the necessary access while following the principle of least privilege. What should you do?  

- **A.** Create a custom IAM role containing every permission from the two relevant predefined roles.
- **B.** Assign both relevant predefined IAM roles to the Site Reliability Engineering team.
- **C.** Create a custom IAM role containing only the individual GKE and Cloud SQL permissions that the team requires.
- **D.** Assign the Kubernetes Engine Admin and Cloud SQL Admin roles to the Site Reliability Engineering team.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because combining every permission from both predefined roles would also include permissions that the team does not require. Although a custom IAM role can contain supported permissions associated with multiple Google Cloud services, simply copying all permissions from the two predefined roles does not improve the organization’s least-privilege posture. It effectively reproduces the combined access of those roles in a single custom role and could authorize unrelated operations. The custom role should instead be designed around the team’s actual job responsibilities and contain only the necessary GKE and Cloud SQL permissions.

**B is incorrect** because assigning both predefined roles would grant every permission included in those roles, including permissions outside the team’s operational requirements. Google generally recommends predefined roles when one or more predefined roles closely match the required access because Google maintains and updates them. In this scenario, however, the predefined roles do not precisely match the required permission set and contain unnecessary permissions. Granting both roles would therefore create excessive access. A narrowly scoped custom role is more appropriate when existing predefined roles cannot provide the required permissions without overprovisioning access.

**C is correct** because a custom IAM role allows the company to select only the supported GKE and Cloud SQL permissions that the Site Reliability Engineering team needs. This approach follows the principle of least privilege by excluding unrelated permissions from the existing predefined roles. The custom role can be created at the organization level when it needs to be reused across multiple projects or at the project level when it is required only within one project. The role should be granted to a Google group representing the team rather than separately to individual users, which simplifies membership and access lifecycle management. Administrators must maintain custom roles and review them as service requirements change, but this maintenance is justified when predefined roles would grant materially broader access than necessary.

**D is incorrect** because Kubernetes Engine Admin and Cloud SQL Admin are broad administrative roles. Kubernetes Engine Admin provides extensive control over GKE resources, while Cloud SQL Admin provides broad authority to create, modify, and manage Cloud SQL resources. The team requires only a specific subset of permissions, so assigning both administrator roles would provide unnecessary and potentially high-impact privileges. This would increase the risk of accidental or unauthorized changes and would violate the principle of least privilege. Administrative roles should be granted only when users genuinely need full administrative control over the corresponding services.

**Reference links**

- [docs.cloud.google.com/iam/docs/creating-custom-roles](https://docs.cloud.google.com/iam/docs/creating-custom-roles)
- [docs.cloud.google.com/iam/docs/choose-role-type](https://docs.cloud.google.com/iam/docs/choose-role-type)
- [docs.cloud.google.com/iam/docs/using-iam-securely](https://docs.cloud.google.com/iam/docs/using-iam-securely)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q34

> NovaCart stores private container images in Artifact Registry for its online ordering platform. The cloud team is creating a new Google Kubernetes Engine cluster to run these images. A custom IAM service account already has the Artifact Registry Reader role required to download the images. The team must configure the cluster so that its nodes can pull the images securely. What should the team do?  

- **A.** Specify the IAM service account in the serviceAccountName field of each Pod manifest.
- **B.** Enable Workload Identity Federation for GKE on the cluster.
- **C.** Configure the cluster nodes to use the custom IAM service account.
- **D.** Create a JSON key for the IAM service account and store the key in a Kubernetes Secret after creating the cluster.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the serviceAccountName field in a Pod specification refers to a Kubernetes ServiceAccount in the Pod’s namespace, not directly to an IAM service account attached to the GKE nodes. Kubernetes ServiceAccounts define the identity under which Pods interact with the Kubernetes API and can also be mapped to Google Cloud identities through Workload Identity Federation for GKE. However, pulling a container image occurs at the node level before the application container starts. The kubelet and container runtime on the node retrieve the image by using the node’s IAM service account. Therefore, placing the configured IAM service account name in the Pod manifest does not give the node permission to pull the image and might also reference a nonexistent Kubernetes ServiceAccount.

**B is incorrect** because Workload Identity Federation for GKE provides Google Cloud identities to workloads running inside Pods. It is the recommended method for allowing applications to access services such as Cloud Storage, Secret Manager, or Pub/Sub without service account keys. It does not control the identity that the GKE node uses when its kubelet pulls an image before starting a Pod. Even when Workload Identity Federation for GKE is enabled, private Artifact Registry image pulls normally depend on the IAM permissions and access scopes of the node service account. Enabling Workload Identity Federation for GKE is a security best practice for workload authentication, but it does not by itself satisfy the image-pulling requirement described here.

**C is correct** because GKE nodes use their attached IAM service account when performing node-level operations, including authenticating to Artifact Registry to pull private container images. Because the custom service account already has the required Artifact Registry permissions, the cluster or node pool should be created with that service account configured as its node service account. For example, a Standard cluster can be created with the --service-account flag. The service account should have the Artifact Registry Reader role on the relevant repository or project and the Kubernetes Engine Default Node Service Account role for the system operations that GKE nodes must perform. The nodes must also have an appropriate access scope, such as cloud-platform, because both IAM permissions and access scopes can limit requests made from GKE nodes. Attaching the configured service account directly to the nodes lets the kubelet authenticate and download the images without distributing long-lived credentials.

**D is incorrect** because creating and storing a service account JSON key introduces a long-lived credential that must be protected, rotated, audited, and eventually revoked. Service account keys can be exposed through Kubernetes Secret access, application logs, accidental configuration disclosure, or unauthorized cluster access. Although Kubernetes imagePullSecrets can be used to authenticate to some private registries, manually distributing a Google Cloud service account key is unnecessary for a GKE cluster whose nodes can authenticate by using their attached IAM service account. Attaching the service account to the nodes provides short-lived credentials through the Google Cloud metadata system and avoids the security and administrative risks of managing JSON keys.

**Reference links**

- [docs.cloud.google.com/artifact-registry/docs/integrate-gke](https://docs.cloud.google.com/artifact-registry/docs/integrate-gke)
- [docs.cloud.google.com/kubernetes-engine/security/configure-node-service-accounts](https://docs.cloud.google.com/kubernetes-engine/security/configure-node-service-accounts)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/workload-identity](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/workload-identity)

**Related notes:** [Artifact Registry](../03-compute-containers/products/artifact-registry.md)

</details>

[Back to index](#index)

---

### Q35

> HealthBridge Systems is moving a patient-records application from its private data center to Compute Engine. The application runs in one zone, but its storage must remain current and accessible if that zone becomes unavailable. The recovery design should minimize data loss and avoid restoring data from backups during a zonal failure. What should the company do?  

- **A.** -Store the application data on a zonal Persistent Disk and configure a snapshot schedule.  
  -During an outage, restore the latest snapshot to a new disk and attach it to a VM in another zone.
- **B.** Store the application data on a zonal Persistent Disk. During an outage, create a VM in another zone and attach the existing disk to that VM.
- **C.** -Store the application data on a regional Persistent Disk and configure a snapshot schedule.  
  -During an outage, restore the latest snapshot to a new disk and attach it to a VM in another zone.
- **D.** Store the application data on a regional Persistent Disk. During an outage, create a VM in the disk’s other replica zone and attach the regional disk to that VM.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a zonal Persistent Disk exists in only one zone. If that zone becomes unavailable, the disk cannot be directly accessed from a VM in another zone. A snapshot schedule provides periodic backups, but snapshots are created only at configured intervals. Consequently, the latest snapshot might not include the most recent application writes, resulting in a recovery point objective greater than zero. Creating a new disk from a snapshot also requires additional recovery time, so the data would not be immediately available. Snapshot schedules are valuable for backup, corruption recovery, and longer-term data protection, but they are not a replacement for synchronous cross-zone replication in a high-availability design.

**B is incorrect** because a zonal Persistent Disk can be attached only to VM instances located in the same zone as the disk. A VM created in another zone cannot attach the existing zonal disk. If the original zone fails, both the VM and access to its zonal disk can become unavailable. Recovering the workload in a different zone would require creating a new disk from a snapshot or another replicated copy, neither of which is included in this option.

**C is incorrect** because using a regional Persistent Disk is appropriate for protecting application data against a single zonal failure. A regional Persistent Disk synchronously maintains replicas in two zones within the same region. However, restoring the latest snapshot during the outage is unnecessary and would not provide immediate access to the most current data. A snapshot contains the disk state only as of the time the snapshot was created, so the restored disk might omit writes made after that point. Restoring and attaching a new disk would also increase recovery time. Snapshots should still be used as part of a backup strategy, but failover should use the synchronously replicated regional disk itself.

**D is correct** because a regional Persistent Disk synchronously replicates its data between two zones in the same Google Cloud region. An application write is acknowledged only after the required replication has occurred, allowing the surviving replica to contain current data when one zone fails. If the VM in the primary zone becomes unavailable, the company can create or start a replacement VM in the disk’s other replica zone and attach the same regional disk. When the failed VM cannot release the disk normally, the recovery process can use a force-attach operation to attach the disk to the replacement VM and prevent simultaneous access from the failed primary VM. This approach provides a zero recovery point objective for a single zonal failure, although the application still requires a failover process to start the replacement compute instance, attach and mount the disk, and restart the application.

**Reference links**

- [docs.cloud.google.com/compute/docs/disks/high-availability-regional-persistent-disk](https://docs.cloud.google.com/compute/docs/disks/high-availability-regional-persistent-disk)
- [docs.cloud.google.com/compute/docs/disks/repd-failover](https://docs.cloud.google.com/compute/docs/disks/repd-failover)
- [docs.cloud.google.com/compute/docs/regions-zones/global-regional-zonal-resources](https://docs.cloud.google.com/compute/docs/regions-zones/global-regional-zonal-resources)

**Related notes:** [Persistent Disk and snapshots](../03-compute-containers/products/persistent-disk-and-snapshots.md)

</details>

[Back to index](#index)

---

### Q36

> Northwind Media operates Bigtable, Cloud SQL, Memorystore, and Spanner resources for several customer-facing applications. The operations team needs one dashboard that displays the health of the entire database fleet and highlights configurations that could cause availability problems or downtime. What should the team do?  

- **A.** Use Dataplex Universal Catalog to search the metadata of the database resources and review their operational health.
- **B.** Run the terraform state list command from the Terraform working directory that contains the database deployments.
- **C.** Open Cloud Asset Inventory in the Google Cloud console to review the database fleet and identify availability risks.
- **D.** Open Database Center in the Google Cloud console to review the database fleet and its health issues.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Dataplex Universal Catalog is primarily a data discovery, metadata management, governance, and cataloging service. It helps organizations search for data assets, understand metadata, document data, apply governance controls, and discover relationships among data resources. Although it can provide metadata about certain storage and analytics assets, it is not the unified operational health dashboard designed to monitor the availability posture of Bigtable, Cloud SQL, Memorystore, and Spanner resources. Searching metadata would not automatically identify database configuration problems related to durability, fault tolerance, data protection, security, performance, or downtime risk across the database fleet.

**B is incorrect** because the terraform state list command only lists resources recorded in the current Terraform state. It can help an administrator determine which resources are managed by a particular Terraform configuration, but it does not retrieve live database health information, performance signals, availability recommendations, or downtime risks. It might also omit resources that were created manually, deployed by another Terraform state, or managed through another provisioning tool. Therefore, Terraform state cannot provide a complete and continuously evaluated health view of the company’s database fleet.

**C is incorrect** because Cloud Asset Inventory provides an inventory of Google Cloud resources and their metadata, configurations, policies, and change history. It is useful for locating resources, analyzing IAM policies, exporting asset metadata, and tracking configuration changes across projects, folders, or an organization. However, it is not specifically designed to evaluate database fleet health or categorize database issues that could affect availability and cause downtime. An administrator might find the individual database resources in Cloud Asset Inventory, but the service does not provide the specialized database health dashboard and actionable health findings required by the scenario.

**D is correct** because Database Center provides a centralized view of a Google Cloud database fleet, including supported Bigtable, Cloud SQL, Memorystore, and Spanner resources. Its dashboard consolidates database inventory and health information so administrators can identify resources affected by availability, data protection, security, performance, compliance, and cost issues. Availability health issues specifically evaluate resource configurations that can affect durability, fault tolerance, and the likelihood of downtime. Therefore, opening Database Center in the Google Cloud console provides the unified, database-focused health overview required to identify resources at risk.

**Reference links**

- [docs.cloud.google.com/database-center/docs/overview](https://docs.cloud.google.com/database-center/docs/overview)
- [docs.cloud.google.com/database-center/docs/database-health-issues](https://docs.cloud.google.com/database-center/docs/database-health-issues)
- [docs.cloud.google.com/asset-inventory/docs/asset-inventory-overview](https://docs.cloud.google.com/asset-inventory/docs/asset-inventory-overview)

**Related notes:** [Database Center](../05-storage-databases-data/products/database-center.md)

</details>

[Back to index](#index)

---

### Q37

> PixelNest runs a Cloud Run service that displays product media stored in an existing shared Cloud Storage bucket. The service must read only the objects whose names begin with catalog-east/. The permission must also apply automatically to future objects uploaded with this prefix, and the solution should require minimal implementation and ongoing administration. What should you do?  

- **A.** Use fine-grained access control, and modify the uploader so that it adds an object ACL granting the Cloud Run service identity the READER role whenever an object with the catalog-east/ prefix is uploaded.
- **B.** Create a separate bucket for objects with the catalog-east/ prefix, and grant the Cloud Run service identity the roles/storage.objectViewer IAM role at the project level.
- **C.** Create a separate bucket for objects with the catalog-east/ prefix, and grant the Cloud Run service identity the roles/storage.objectViewer IAM role directly on that bucket.
- **D.** Enable uniform bucket-level access on the existing bucket, and add a conditional IAM binding that grants the Cloud Run service identity the roles/storage.objectViewer IAM role only for objects with the catalog-east/ prefix.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because fine-grained access control and object ACLs could technically grant the Cloud Run service identity permission to read individual objects, but this approach creates unnecessary operational work. The uploader must be modified to apply the correct ACL every time it creates a matching object, and all existing matching objects would also need their ACLs updated separately. An upload that fails to apply the ACL could leave an object inaccessible to the service. Fine-grained access also requires administrators to manage both IAM policies and legacy ACLs, making access auditing and maintenance more complicated. The requirement is better satisfied by one centralized policy that automatically applies according to the object name.

**B is incorrect** because granting roles/storage.objectViewer at the project level would generally give the Cloud Run service identity read access to objects across the project’s Cloud Storage buckets, not just the objects intended for PixelNest. This violates the principle of least privilege. Creating a new bucket would also require copying or moving existing objects, changing the upload destination, updating the application configuration, and potentially maintaining lifecycle, encryption, logging, and networking settings for another bucket. This creates substantially more implementation work than applying a conditional policy to the existing bucket.

**C is incorrect** because a bucket-level roles/storage.objectViewer grant on a dedicated bucket would appropriately limit access to objects in that bucket and would be safer than the project-level grant in option B. However, it still requires creating and administering another bucket, migrating the existing catalog-east/ objects, changing the uploader, and updating the Cloud Run service configuration. Although this design could work, it does not meet the requirement for minimal implementation and maintenance when the objects can remain in the existing shared bucket and be protected by a prefix-based IAM Condition.

**D is correct** because uniform bucket-level access centralizes authorization in IAM and disables the use of individual object ACLs. Uniform bucket-level access is required before IAM Conditions can be added directly to a Cloud Storage bucket policy. A conditional roles/storage.objectViewer binding can evaluate the object’s resource name and grant the Cloud Run service identity read access only when that name begins with the resource path corresponding to catalog-east/. Objects outside that prefix do not satisfy the condition. Because the condition is evaluated whenever access is requested, existing matching objects and all future objects uploaded with the same prefix are covered automatically. No uploader changes, per-object ACL updates, object migration, or additional bucket administration are required, making this the least-privilege solution with the lowest ongoing maintenance.

**Reference links**

- [docs.cloud.google.com/storage/docs/access-control](https://docs.cloud.google.com/storage/docs/access-control)
- [docs.cloud.google.com/storage/docs/access-control/using-iam-permissions](https://docs.cloud.google.com/storage/docs/access-control/using-iam-permissions)
- [docs.cloud.google.com/storage/docs/access-control/iam-roles](https://docs.cloud.google.com/storage/docs/access-control/iam-roles)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q38

> StreamLoom is developing an AI application on Gemini Enterprise Agent Platform that consumes delivery events from a Pub/Sub subscription. During local testing, a developer authenticated with personal Application Default Credentials. The team has now created a user-managed service account and configured it as the application’s agent identity for deployment. You need to ensure that the deployed application can continue consuming Pub/Sub messages securely. What should you do?  

- **A.** Grant the required Pub/Sub IAM roles to the service account configured as the application’s agent identity.
- **B.** Create a JSON private key for the service account, and add the key to the Gemini Enterprise Agent Platform deployment metadata.
- **C.** Run the gcloud auth print-access-token command with the developer’s account, and package the resulting token with the application.
- **D.** Store the developer’s personal credentials in Secret Manager, and modify the application to retrieve and use those credentials.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the deployed application authenticates as the service account configured as its agent identity, not as the developer who tested the application locally. Therefore, the service account must be authorized to access the required Pub/Sub resources. For an application that consumes messages from an existing subscription, the service account typically needs the roles/pubsub.subscriber role on that subscription or at another appropriate resource level. Granting the role directly to the workload identity follows the principle of least privilege and allows Google Cloud client libraries to use Application Default Credentials automatically. Gemini Enterprise Agent Platform can obtain short-lived credentials for the attached service account without storing credentials in the application. The application code can therefore use the same standard authentication mechanism in local and deployed environments while the underlying identity changes appropriately.

**B is incorrect** because generating and uploading a JSON private key is unnecessary when the application already has an attached service account identity. Google Cloud workloads can obtain short-lived service account credentials automatically through Application Default Credentials. A downloaded service account key is a long-lived credential that must be securely stored, protected, audited, and rotated. Anyone who obtains the key can authenticate as the service account until the key is disabled or deleted. Deployment metadata is also not an appropriate location for storing private authentication keys. Using the attached service account is simpler, safer, and requires less credential management.

**C is incorrect** because an access token generated by gcloud auth print-access-token is temporary and expires after a limited period. Packaging that token with the application would cause Pub/Sub access to fail after the token expires. The token would also represent the developer’s personal identity rather than the application’s production identity. Regularly generating and redeploying personal access tokens would be insecure, operationally impractical, and incompatible with reliable production authentication. The deployed workload should obtain renewable, short-lived credentials automatically through its configured service account.

**D is incorrect** because production applications should not depend on a developer’s personal credentials. Personal credentials can be revoked, expire, be affected by account security policies, or become unavailable when the employee changes roles or leaves the organization. Storing them in Secret Manager does not correct the underlying identity design and creates an unnecessary dependency on a human account. Additionally, the application would already need a Google Cloud identity with permission to access the secret, so that identity can instead be granted the required Pub/Sub permissions directly. A dedicated service account provides clearer ownership, better auditing, more precise permissions, and a safer workload identity lifecycle.

**Reference links**

- [docs.cloud.google.com/gemini-enterprise-agent-platform/machine-learning/general/custom-service-account](https://docs.cloud.google.com/gemini-enterprise-agent-platform/machine-learning/general/custom-service-account)
- [docs.cloud.google.com/pubsub/docs/access-control](https://docs.cloud.google.com/pubsub/docs/access-control)
- [docs.cloud.google.com/docs/authentication/set-up-adc-attached-service-account](https://docs.cloud.google.com/docs/authentication/set-up-adc-attached-service-account)

**Related notes:** [Gemini Enterprise Agent Platform: Agent Runtime](../08-iac-platform-ai/products/agent-runtime.md)

</details>

[Back to index](#index)

---

### Q39

> QuantaFleet is developing a data-processing tool that will run in Google Cloud and access BigQuery and Cloud Storage by using an existing service account named fleet-data-runner. A developer is signed in to the Google Cloud CLI on a company laptop with a personal Google Account. Before deployment, the developer must run the tool locally as fleet-data-runner to verify that the service account’s existing permissions are sufficient. Company policy prohibits downloading or managing service account keys. Which IAM role should be granted to the developer on fleet-data-runner?  

- **A.** Grant the developer roles/iam.workloadIdentityUser on fleet-data-runner.
- **B.** Grant the developer roles/iam.serviceAccountKeyAdmin on fleet-data-runner.
- **C.** Grant the developer roles/iam.serviceAccountTokenCreator on fleet-data-runner.
- **D.** Grant the developer roles/iam.serviceAccountUser on fleet-data-runner.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the Workload Identity User role is intended primarily for principals that impersonate IAM service accounts from GKE workloads through Workload Identity Federation for GKE. Although this role contains limited permissions for generating access tokens and OpenID Connect ID tokens, it is not the standard predefined role for a developer authenticated with a Google Account who needs to impersonate a service account from a local workstation. For user-based local testing, Google Cloud specifies the Service Account Token Creator role.

**B is incorrect** because the Service Account Key Admin role permits the developer to create and manage user-managed service account keys. The developer could create a JSON key and authenticate as the service account, but that would introduce persistent private key material, directly violating the requirement not to handle sensitive secrets. Service account keys must be securely stored, rotated, monitored, and eventually deleted, and anyone who obtains the key can act as the service account. Service account impersonation is safer because it produces temporary credentials without exposing the service account’s private key.

**C is correct** because the Service Account Token Creator role grants the permissions required for a Google Account to impersonate the existing service account and obtain short-lived credentials. After receiving this role on fleet-data-runner, the developer can test individual Google Cloud CLI commands by using the --impersonate-service-account flag or configure local Application Default Credentials by running gcloud auth application-default login --impersonate-service-account=SERVICE_ACCOUNT_EMAIL. The application then makes requests using fleet-data-runner’s identity and existing resource permissions, allowing the developer to accurately determine whether those permissions are sufficient. The generated credentials are temporary, the service account’s private key is never downloaded, and granting the role directly on the specific service account limits the developer’s impersonation capability to that account.

**D is incorrect** because the Service Account User role grants the iam.serviceAccounts.actAs permission, which allows a principal to attach a service account to a supported Google Cloud resource such as a Compute Engine instance, Cloud Run service, or other managed workload. It does not permit the developer to create short-lived credentials for the service account or use the Google Cloud CLI’s --impersonate-service-account option from a local workstation. Therefore, it would be appropriate when deploying a resource that runs as fleet-data-runner, but it does not satisfy the local impersonation and permission-testing requirement.

**Reference links**

- [docs.cloud.google.com/docs/authentication/use-service-account-impersonation](https://docs.cloud.google.com/docs/authentication/use-service-account-impersonation)
- [docs.cloud.google.com/iam/docs/service-account-permissions](https://docs.cloud.google.com/iam/docs/service-account-permissions)
- [docs.cloud.google.com/iam/docs/service-account-impersonation](https://docs.cloud.google.com/iam/docs/service-account-impersonation)

**Related notes:** [Service account impersonation](../02-identity-security/products/service-account-impersonation.md)

</details>

[Back to index](#index)

---

### Q40

> SilverOak Analytics is deploying a licensed reporting application on a new Compute Engine VM. Several existing VMs use the project’s default Compute Engine service account. The application’s installation packages are stored in a private Cloud Storage bucket, and only the new VM must be able to read them. What should the cloud administrator do?  

- **A.** Attach the default Compute Engine service account to the new VM and grant that service account access to the Cloud Storage bucket.
- **B.** Attach the default Compute Engine service account to the new VM and add matching metadata to the VM and the Cloud Storage objects.
- **C.** Create a user-managed service account, attach it to the new VM, and grant it the required permissions on the Cloud Storage bucket.
- **D.** Create a user-managed service account, attach it to the new VM, and add matching metadata to the VM and the Cloud Storage objects.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the existing Compute Engine instances already use the default Compute Engine service account. Granting that shared service account permission to read the installation files would potentially authorize every VM that uses the same service account to access those files. IAM permissions are associated with the service account identity, not with one particular VM using that identity. This approach therefore fails the requirement that only the new VM should have access. A separate service account should be used to isolate the application’s permissions from those of the existing instances.

**B is incorrect** because custom VM metadata and Cloud Storage object metadata do not create an authorization relationship. VM metadata is commonly used to provide configuration values, startup scripts, or other information to a VM, while object metadata describes or categorizes Cloud Storage objects. Cloud Storage does not compare these metadata values to decide whether a VM can download an object. Access must be granted through an authorization mechanism such as IAM. This option also uses the shared default Compute Engine service account and therefore does not isolate the new VM from the existing VMs.

**C is correct** because a dedicated user-managed service account gives the new VM a distinct Google Cloud identity. The administrator can attach this service account only to the new VM and grant it the minimum Cloud Storage permissions required to download the installation packages. For example, the service account can receive the Storage Object Viewer role on the specific bucket containing the files. Applications running on the VM can then use the attached service account’s credentials through Application Default Credentials without storing long-lived service account keys on the instance. Because the existing VMs use a different service account, they do not inherit the new service account’s Cloud Storage access. This follows the principles of least privilege and workload identity isolation.

**D is incorrect** because creating and attaching a dedicated user-managed service account is appropriate, but matching metadata does not grant that service account permission to access Cloud Storage. The service account must be assigned an IAM role containing the required permissions, such as storage.objects.get and, when object listing is required, storage.objects.list. Without an appropriate IAM role on the bucket, project, or another supported resource level, the application receives an authorization error even when the VM and Cloud Storage objects contain identical metadata.

**Reference links**

- [cloud.google.com/compute/docs/access/service-accounts](https://cloud.google.com/compute/docs/access/service-accounts)
- [cloud.google.com/compute/docs/access/create-enable-service-accounts-for-instances](https://cloud.google.com/compute/docs/access/create-enable-service-accounts-for-instances)
- [cloud.google.com/storage/docs/access-control/iam-roles](https://cloud.google.com/storage/docs/access-control/iam-roles)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q41

> Northstar Games maintains 4.8 petabytes of historical player-event data in Apache Avro files in an on-premises data center. The company is moving the data to Google Cloud so data scientists can perform large-scale analysis and train models by using BigQuery. You need to avoid copying the files into BigQuery-managed storage and keep long-term storage costs as low as possible. What should you do?  

- **A.** Configure BigQuery Data Transfer Service to import the Avro files into a native BigQuery table.
- **B.** Import the Avro data into Cloud SQL for PostgreSQL, and query it from BigQuery by using federated queries.
- **C.** Store the Avro files in Cloud Storage using a Hive-compatible partition layout, and create a partitioned BigQuery external table over the files.
- **D.** Store the Avro files in Cloud Storage, define the destination table schema, and run a separate bq load job for each file.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because BigQuery Data Transfer Service is designed to automate data movement from supported sources into BigQuery, but importing the Avro files into a native table would place the data in BigQuery-managed storage. This contradicts the requirement to avoid the loading process and prevent an additional managed copy of several petabytes of data. The organization would first need to move or stage the on-premises files in a supported source, configure the transfer, monitor the ingestion jobs, and maintain the resulting native tables. Although native BigQuery tables generally provide stronger query performance than external tables, this option does not satisfy the stated storage and ingestion constraints.

**B is incorrect** because Cloud SQL for PostgreSQL is an operational relational database service rather than a petabyte-scale analytical data lake. Moving 4.8 petabytes of historical Avro data into PostgreSQL would require converting the files into relational tables and operating a database architecture that is inappropriate for this volume of analytical data. BigQuery federated queries against Cloud SQL are useful when analysts need to access relatively small operational datasets without first copying them into BigQuery, but they remain constrained by the source database’s processing capacity and are not an efficient solution for large-scale scans or machine learning workloads. This option would also add database administration, capacity planning, indexing, backup, and scaling overhead.

**C is correct** because BigQuery external tables allow BigQuery to store the table definition and schema while leaving the actual Avro data in Cloud Storage. BigQuery supports Avro as an external-table format, so analysts can query the files without loading them into native BigQuery-managed storage. Organizing the files in a Hive-compatible directory structure, such as event_date=2026-06-15, allows BigQuery to expose the directory values as partition columns. Queries that filter on those columns can prune unrelated partitions, reducing the amount of data read and improving query efficiency. This design avoids maintaining a second petabyte-scale copy in BigQuery, removes the operational overhead of running thousands of load jobs, and allows Cloud Storage lifecycle policies and suitable storage classes to be used according to the data’s access frequency. The Cloud Storage bucket and BigQuery dataset must also use compatible locations.

**D is incorrect** because the bq load command imports data from Cloud Storage into native BigQuery tables. Defining the schema does not make the table external when the files are processed with bq load. Running a separate load operation for every file would create considerable orchestration and monitoring overhead for a multi-petabyte archive, and the loaded data would consume BigQuery-managed storage, which directly conflicts with the requirements. Loading Avro files can be appropriate when native-table performance and BigQuery-managed storage features are more important than avoiding ingestion, but an external table is the more suitable design in this scenario.

**Reference links**

- [docs.cloud.google.com/bigquery/docs/external-data-cloud-storage](https://docs.cloud.google.com/bigquery/docs/external-data-cloud-storage)
- [docs.cloud.google.com/bigquery/docs/hive-partitioned-queries](https://docs.cloud.google.com/bigquery/docs/hive-partitioned-queries)
- [docs.cloud.google.com/bigquery/docs/loading-data-cloud-storage-avro](https://docs.cloud.google.com/bigquery/docs/loading-data-cloud-storage-avro)

**Related notes:** [BigQuery](../05-storage-databases-data/products/bigquery.md)

</details>

[Back to index](#index)

---

### Q42

> BrightCart operates an online grocery platform on Google Cloud. A new application engineer joins the app-release group and must deploy containerized services to an existing Google Kubernetes Engine (GKE) cluster. The engineer does not need permission to create, modify, or delete clusters or manage unrelated Google Cloud resources. You must provide access according to the principle of least privilege. What should you do?  

- **A.** Add the engineer to the app-release group, which already has the Kubernetes Engine Developer role (roles/container.developer).
- **B.** Grant the engineer the Kubernetes Engine Admin role (roles/container.admin) on the project.
- **C.** Grant the engineer the Kubernetes Engine Service Agent role (roles/container.serviceAgent) on the project.
- **D.** Grant the engineer the Editor basic role (roles/editor) on the project.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the Kubernetes Engine Developer role is designed for users who need to work with containerized workloads in GKE without receiving full administrative control over the cluster. It includes permissions for accessing clusters and working with Kubernetes API objects, which supports common application deployment activities such as creating and updating Deployments, Pods, Services, and related workload resources. Adding the engineer to the existing app-release group is also preferable to assigning the role directly to the individual because group-based access simplifies onboarding, offboarding, auditing, and consistent permission management. Since the group already has the appropriate role, group membership gives the engineer the required permissions without granting unnecessary access to other Google Cloud resources or cluster administration capabilities. Depending on the cluster’s authorization configuration, Kubernetes role-based access control may also be used to restrict the engineer to particular namespaces or Kubernetes resources.

**B is incorrect** because the Kubernetes Engine Admin role provides broad administrative permissions for GKE resources. It can allow a principal to create, update, and delete clusters and manage other GKE configuration, rather than limiting the principal to deploying applications to an existing cluster. The engineer does not need control over cluster infrastructure, node pools, or cluster-level settings. Granting roles/container.admin would therefore provide significantly more authority than the stated task requires and would violate the principle of least privilege.

**C is incorrect** because the Kubernetes Engine Service Agent role is intended for the Google-managed GKE service agent, not for human developers or administrators. Service agent roles contain permissions that Google Cloud services require to operate resources on behalf of a project. Assigning this role to a developer could expose sensitive service-level capabilities and does not represent the supported method for granting workload deployment access. Service agent roles should generally remain assigned only to their corresponding Google-managed service accounts unless Google Cloud documentation explicitly instructs otherwise.

**D is incorrect** because the Editor basic role grants broad write access across many supported Google Cloud services in the project. It is not limited to GKE workloads and could allow the engineer to modify unrelated resources such as Compute Engine instances, storage resources, networking configurations, and other project services. Basic roles are too broad for most production access-control requirements. A predefined role targeted to the required GKE task, combined with group-based assignment and optional Kubernetes namespace-level authorization, provides a more secure least-privilege solution.

**Reference links**

- [cloud.google.com/iam/docs/roles-permissions/container](https://cloud.google.com/iam/docs/roles-permissions/container)
- [cloud.google.com/kubernetes-engine/docs/how-to/iam](https://cloud.google.com/kubernetes-engine/docs/how-to/iam)
- [cloud.google.com/iam/docs/understanding-roles](https://cloud.google.com/iam/docs/understanding-roles)

</details>

[Back to index](#index)

---

### Q43

> OrbitPay runs payment-processing workloads across many Google Cloud projects. The company manages employees through Cloud Identity and wants each engineering team’s permissions to change automatically when people join, transfer, or leave. You need a scalable access-management model that uses groups created specifically for resource authorization and follows Google-recommended security practices. What should you do?  

- **A.** Create one Google Group per engineering team with only the cloudidentity.googleapis.com/groups.discussion_forum label, manage its membership, and add the group to IAM allow policies.
- **B.** Create one service account per engineering team and grant every team member permission to impersonate the team’s service account.
- **C.** Create one service account per engineering team and allow every team member to create and download keys for the team’s service account.
- **D.** Create one Google Group per engineering team with the cloudidentity.googleapis.com/groups.discussion_forum and cloudidentity.googleapis.com/groups.security labels, manage its membership, and add the group to IAM allow policies.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because an ordinary Google Group with only the cloudidentity.googleapis.com/groups.discussion_forum label can technically be used as a principal in IAM policies, and its members can inherit the roles granted to the group. However, this label creates a standard collaboration-capable Google Group rather than a Cloud Identity security group intended specifically for controlling access to organizational resources. Collaboration-oriented groups can have looser membership and lifecycle controls, making them less appropriate for managing sensitive access across hundreds of resources. Because the requirement explicitly calls for Google-recommended security practices, the group should also have the cloudidentity.googleapis.com/groups.security label.

**B is incorrect** because service accounts represent non-human identities intended primarily for applications, workloads, virtual machines, and automated processes. They should not normally be used as shared identities for teams of human users. Granting every team member permission to impersonate a service account adds unnecessary identity indirection and requires administrators to manage service account impersonation permissions in addition to team membership. A compromised or excessively privileged service account could also provide access to every resource available to that service account. Directly granting IAM roles to a properly controlled security group is simpler, more transparent, and better aligned with the team-based access requirement.

**C is incorrect** because service account keys are long-lived credentials that can be copied, shared, leaked, or used outside the organization’s managed environment. Allowing multiple employees to generate and download keys creates substantial security and administrative overhead, including key inventory, secure distribution, rotation, monitoring, and revocation. Removing a person from a team would not automatically invalidate copies of keys that the person previously downloaded. Google recommends avoiding service account keys whenever possible, and service accounts are not the appropriate replacement for Cloud Identity groups that represent human teams.

**D is correct** because a Cloud Identity security group is designed specifically for controlling access to organizational resources. A security group created through the Cloud Identity Groups API includes both cloudidentity.googleapis.com/groups.discussion_forum and cloudidentity.googleapis.com/groups.security labels. The group can be added as a principal to IAM allow policies, and every group member inherits the roles granted to that group. Administrators can then grant or revoke access by changing only the group’s membership rather than editing IAM policies across hundreds of individual resources. When a person joins a team, adding the person to the corresponding security group provides the team’s permissions; when the person transfers or leaves, removing the membership revokes those inherited permissions. This approach reduces administrative effort, supports centralized lifecycle management, avoids shared credentials, and follows Google’s recommendation to use access groups and Cloud Identity security groups for resource authorization.

**Reference links**

- [docs.cloud.google.com/identity/docs/how-to/update-group-to-security-group](https://docs.cloud.google.com/identity/docs/how-to/update-group-to-security-group)
- [docs.cloud.google.com/identity/docs/groups](https://docs.cloud.google.com/identity/docs/groups)
- [docs.cloud.google.com/iam/docs/groups-best-practices](https://docs.cloud.google.com/iam/docs/groups-best-practices)

</details>

[Back to index](#index)

---

### Q44

> LumaDesk Technologies has built an AI support agent that must remain available to handle customer requests and automatically scale during changes in traffic. The development team wants a fully managed execution environment designed for production AI agents and does not want to administer Kubernetes clusters, virtual machines, or custom autoscaling infrastructure. What should LumaDesk Technologies use?  

- **A.** Cloud Workstations
- **B.** Application Design Center
- **C.** Gemini CLI
- **D.** Agent Runtime on Gemini Enterprise Agent Platform

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Cloud Workstations provides managed, secure development environments for software developers. It allows an organization to create standardized browser-based or locally connected workstations with centrally controlled configurations, development tools, networking, and security policies. Developers could use Cloud Workstations to write, test, and debug the agent’s source code, but Cloud Workstations is not a production runtime for continuously serving agent requests. It does not provide the specialized agent deployment, execution, session management, and production scaling capabilities required by the scenario.

**B is incorrect** because Application Design Center helps teams design, standardize, and deploy approved cloud application architectures using reusable infrastructure components and templates. A platform team can use it to create governed deployment patterns based on Terraform modules, making those patterns available for developer self-service. However, Application Design Center does not execute an AI agent or provide an agent-specific managed runtime. It could help model the surrounding cloud architecture, but another service would still be required to run and scale the agent.

**C is incorrect** because Gemini CLI is an open-source AI agent that developers use from a command-line environment. It can assist with tasks such as understanding code, implementing features, fixing bugs, running tools, and interacting with local or remote Model Context Protocol servers. It is primarily a development and productivity tool, not a managed production hosting environment. Running Gemini CLI would not provide a continuously available endpoint, agent-specific runtime management, or automatic production scaling without the team building and operating additional infrastructure.

**D is correct** because Agent Runtime on Gemini Enterprise Agent Platform is specifically designed to deploy, manage, and scale AI agents in production. It handles the underlying execution and scaling infrastructure, allowing the development team to focus on the agent rather than operating Kubernetes clusters, managing virtual machines, or implementing custom autoscaling. After deployment, the agent can be made remotely available to process requests, and the runtime can adjust capacity as demand changes. Agent Runtime also fits the broader Gemini Enterprise Agent Platform lifecycle for building, deploying, governing, and optimizing enterprise-grade agents, making it the most appropriate managed service for a continuously running production agent.

**Reference links**

- [docs.cloud.google.com/gemini-enterprise-agent-platform/build/runtime](https://docs.cloud.google.com/gemini-enterprise-agent-platform/build/runtime)
- [docs.cloud.google.com/gemini-enterprise-agent-platform/scale/runtime/deploy-an-agent](https://docs.cloud.google.com/gemini-enterprise-agent-platform/scale/runtime/deploy-an-agent)
- [docs.cloud.google.com/gemini-enterprise-agent-platform/overview](https://docs.cloud.google.com/gemini-enterprise-agent-platform/overview)

**Related notes:** [Gemini Enterprise Agent Platform: Agent Runtime](../08-iac-platform-ai/products/agent-runtime.md)

</details>

[Back to index](#index)

---

### Q45

Choose 2.

> NovaForge Solutions needs to provide browser-based development environments for 55 external software contractors. Each environment must contain the same security-approved IDE, libraries, command-line tools, and language runtimes. Contractors must retain source code and configuration files after their sessions end, and unused environments must stop automatically after 35 minutes without user activity. Which two configurations should the administrator use? (Choose two.)  

- **A.** Provision a dedicated permanent Compute Engine VM for each contractor.
- **B.** Create a Cloud Workstations configuration that specifies an approved container image.
- **C.** Configure persistent home directories and set an idle timeout.
- **D.** Save all contractor files only on each workstation VM’s boot disk.
- **E.** Configure all contractors to use the same operating-system account.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B, C

**Explanation**

**A is incorrect** because assigning a permanent Compute Engine VM to each contractor would require the company to manage VM provisioning, operating-system updates, development tools, security configurations, and shutdown automation. It also would not inherently ensure that every contractor receives an identical, centrally controlled browser-based development environment. Cloud Workstations provides managed development environments that administrators can standardize through shared workstation configurations, making individually maintained permanent VMs unnecessary.

**B is correct** because a Cloud Workstations configuration defines the common settings used by workstations created from it. The administrator can specify an approved custom container image containing the required IDE, libraries, command-line utilities, language runtimes, security tools, and organizational configurations. Every contractor’s workstation created from that configuration therefore starts with the same reviewed toolchain. When the administrator updates the workstation configuration or its container image, the standardized environment can be maintained centrally rather than configured independently by each contractor.

**C is correct** because persistent home directories preserve contractor files across workstation sessions, while an idle timeout automatically stops workstations that are no longer receiving user activity. Cloud Workstations normally runs each development session on an ephemeral VM. A persistent disk can be mounted as the workstation’s home directory and retained when the workstation stops, allowing source code, settings, and other files stored there to remain available when the contractor starts the workstation again. Configuring an idle timeout also reduces unnecessary resource consumption by stopping inactive workstations after the defined period.

**D is incorrect** because the workstation VM is ephemeral and is deleted when the workstation stops. Data stored only on its boot disk is runtime data and does not provide reliable persistence between sessions. Contractor files that must survive workstation shutdowns should be stored in the configured persistent home directory, which is backed by a persistent disk that is detached when the session ends and reattached when the workstation starts again.

**E is incorrect** because sharing one operating-system account among all contractors weakens security, accountability, and access control. Actions performed through the shared account would be difficult to attribute to a specific contractor, and permissions or personalized settings could not be managed independently. Each contractor should authenticate with an individual identity and receive access to an individually assigned workstation created from the centrally approved Cloud Workstations configuration.

**Reference links**

- [docs.cloud.google.com/workstations/docs/overview](https://docs.cloud.google.com/workstations/docs/overview)
- [docs.cloud.google.com/workstations/docs/create-configuration](https://docs.cloud.google.com/workstations/docs/create-configuration)
- [docs.cloud.google.com/workstations/docs/customize-container-images](https://docs.cloud.google.com/workstations/docs/customize-container-images)

**Related notes:** [Cloud Workstations](../08-iac-platform-ai/products/cloud-workstations.md)

</details>

[Back to index](#index)

---

### Q46

> MetricHaven operates a monitoring agent in a Google Kubernetes Engine cluster. The agent must use an existing IAM service account to collect performance metrics from several Google Cloud services. An organization policy prevents the creation of service account keys. You need to authenticate the monitoring agent securely without storing long-lived credentials in the cluster. What should you do?  

- **A.** Configure the monitoring agent to authenticate by using the personal Google Account credentials of a developer who has the required permissions.
- **B.** Create a separate Google Cloud project, generate a key for a service account in that project, and grant the service account access to resources in the monitoring project.
- **C.** Add a project-level exception to the organization policy, create a long-lived service account key, and mount the key in the monitoring agent’s Pod.
- **D.** Configure Workload Identity Federation for GKE so that the monitoring agent’s Kubernetes ServiceAccount can impersonate the IAM service account.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because personal user credentials should not be used as the identity of a production workload. The application would become dependent on the developer’s account, permissions, employment status, credential lifecycle, and multifactor authentication requirements. The credentials might expire or be revoked, and actions performed by the application would be attributed to a human identity instead of a dedicated workload identity. Supplying personal credentials to a Pod would also create sensitive credential-management risks. Production GKE applications should use dedicated workload identities with only the permissions required by the application.

**B is incorrect** because creating the service account in another project does not eliminate the security risks associated with a downloaded service account key. The JSON key would still be a long-lived private credential that must be distributed, stored, protected, rotated, audited, and eventually deleted. If the new project belongs to the same organization, the organization policy might also prevent service account key creation there. Even when cross-project service accounts are appropriate, the workload should use short-lived credentials through identity federation or service account impersonation rather than a downloaded key. Creating another project also introduces unnecessary administrative overhead.

**C is incorrect** because overriding a security-focused organization policy and creating a long-lived service account key directly contradicts both the stated requirement and Google-recommended security practices. Mounting the key in the Pod exposes persistent credentials to the container environment and potentially to users, processes, logging systems, backups, or compromised workloads that can access the mounted secret. A stolen key can be used outside the GKE cluster until it is disabled or deleted. This approach also creates ongoing key rotation, distribution, inventory, and incident-response responsibilities that are unnecessary when GKE supports keyless workload authentication.

**D is correct** because Workload Identity Federation for GKE is the recommended mechanism for allowing GKE workloads to authenticate to Google Cloud APIs without using service account key files. The monitoring Pod runs as a Kubernetes ServiceAccount, and that Kubernetes identity is authorized to impersonate the required IAM service account. The IAM service account retains the permissions needed to collect performance data, while the Kubernetes ServiceAccount receives permission to act through that identity. GKE provides the workload with automatically generated, short-lived credentials, and supported Google Cloud client libraries can obtain these credentials through Application Default Credentials. No private key is downloaded, embedded in the container image, or mounted into the Pod. This design follows the principle of least privilege, preserves clear workload-level auditing, complies with the organization policy, and removes the operational burden and security risk of managing long-lived service account keys.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/workload-identity](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/workload-identity)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/workload-identity](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/workload-identity)
- [docs.cloud.google.com/iam/docs/best-practices-for-managing-service-account-keys](https://docs.cloud.google.com/iam/docs/best-practices-for-managing-service-account-keys)

**Related notes:** [Workload Identity Federation for GKE](../02-identity-security/products/workload-identity-federation-for-gke.md)

</details>

[Back to index](#index)

---

### Q47

> BrightCart Media stores product images in a Cloud Storage bucket that uses a customer-managed encryption key located in a separate security project. Cloud Storage must encrypt newly uploaded objects and decrypt them when authorized users access the data. Which IAM role should be granted on the key to the bucket project’s Cloud Storage service agent?  

- **A.** Cloud KMS Admin
- **B.** Cloud KMS CryptoKey Encrypter/Decrypter
- **C.** Storage Object Admin
- **D.** Service Account Token Creator

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because the Cloud KMS Admin role is intended to manage Cloud KMS resources such as key rings, keys, and IAM policies. Administrative control over a key does not provide the cryptographic permissions required to use the key for encryption and decryption. Granting this role to the Cloud Storage service agent would also provide unnecessarily broad key-management permissions and would violate the principle of least privilege. The service agent only needs permission to perform cryptographic operations with the selected key, not permission to modify or administer the key.

**B is correct** because the Cloud KMS CryptoKey Encrypter/Decrypter role provides the permissions required to encrypt and decrypt data with a Cloud KMS key. Cloud Storage uses its project-specific service agent to perform these operations when writing and reading objects protected by a customer-managed encryption key. Because the key is stored in a separate security project, the role must be granted on that key to the Cloud Storage service agent belonging to the project that contains the bucket. The service agent normally follows the format service-PROJECT_NUMBER@gs-project-accounts.iam.gserviceaccount.com. Granting roles/cloudkms.cryptoKeyEncrypterDecrypter at the individual CryptoKey level provides the necessary access while limiting the service agent’s permissions to the relevant key.

**C is incorrect** because the Storage Object Admin role grants permissions to create, read, update, and delete objects in Cloud Storage. It controls access to storage objects, but it does not grant any permissions to use a Cloud KMS key. Even when a user has permission to upload an object, the upload can fail if the Cloud Storage service agent cannot use the configured customer-managed encryption key. The required role must therefore be granted on the Cloud KMS key rather than granting a Cloud Storage data-management role.

**D is incorrect** because the Service Account Token Creator role allows a principal to create short-lived credentials, sign blobs, sign JSON Web Tokens, or impersonate a service account. It does not grant permission to encrypt or decrypt data with Cloud KMS. Cloud Storage does not need to impersonate the service agent to use the key; the Cloud Storage service agent itself must receive the appropriate cryptographic permissions on the customer-managed encryption key.

**Reference links**

- [docs.cloud.google.com/storage/docs/encryption/customer-managed-keys](https://docs.cloud.google.com/storage/docs/encryption/customer-managed-keys)
- [docs.cloud.google.com/kms/docs/reference/permissions-and-roles](https://docs.cloud.google.com/kms/docs/reference/permissions-and-roles)
- [docs.cloud.google.com/kms/docs/iam](https://docs.cloud.google.com/kms/docs/iam)

**Related notes:** [Cloud KMS](../02-identity-security/products/cloud-kms.md)

</details>

[Back to index](#index)

---

### Q48

Choose 2.

> AsterPeak Commerce runs a customer-ordering platform in a production Google Cloud project. Its operations team needs to detect Google Cloud service outages that could affect the project, receive notifications when new incidents are reported, and use one place to review open Cloud Monitoring incidents alongside resource and service-health information. Which two actions should the team take? (Choose two.)  

- **A.** Use Cloud Hub to review application, resource, and operational health information.
- **B.** Enable VPC Flow Logs as the project’s only monitoring mechanism.
- **C.** Configure Personalized Service Health alerts for the production project.
- **D.** Export Cloud Billing data to BigQuery for incident detection.
- **E.** Configure a lifecycle rule on the application’s Cloud Storage bucket.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A, C

**Explanation**

**A is correct** because Cloud Hub provides a centralized view of operational information for Google Cloud applications and resources. Its health view can display open Cloud Monitoring alerts, which Cloud Monitoring also refers to as incidents, together with Google Cloud service-health events and relevant health metrics. The operations team can use this consolidated context to determine whether an issue is caused by its own application or infrastructure, an active Monitoring incident, or a disruption affecting a Google Cloud product. Cloud Hub therefore satisfies the requirement for a centralized view of open incidents and resource-health signals.

**B is incorrect** because VPC Flow Logs record sampled network-flow information for supported VPC network interfaces and resources. They are useful for network monitoring, traffic analysis, security investigation, and connectivity troubleshooting, but they do not notify the team about Google Cloud service disruptions. They also do not provide a centralized view of Cloud Monitoring incidents and broader resource-health signals. Enabling VPC Flow Logs might complement an observability strategy, but using them as the only monitoring mechanism would not meet either of the primary requirements.

**C is correct** because Personalized Service Health identifies Google Cloud service-health events that are relevant to a specific project or organization. It filters service disruptions according to their potential effect on the team’s resources instead of showing only broad public incidents. The team can create alerting policies for new incidents, updates to existing incidents, and events involving selected products or locations. Notifications can be delivered through configured Cloud Monitoring notification channels, allowing operators to respond promptly when a new Google Cloud disruption might affect the production project.

**D is incorrect** because exporting Cloud Billing data to BigQuery supports cost analysis, spending reports, forecasting, chargeback, and financial governance. Billing records might reveal changes in resource consumption or charges, but they are not a dependable or timely source for detecting Google Cloud service incidents. A billing export does not generate Personalized Service Health notifications and does not consolidate open Cloud Monitoring incidents with resource-health information.

**E is incorrect** because a Cloud Storage lifecycle rule automatically performs actions on stored objects when specified conditions are met. For example, it can delete older objects or change their storage class. Lifecycle management is related to data retention and storage-cost optimization, not operational incident management. It cannot detect Google Cloud service disruptions, send incident alerts, or display Cloud Monitoring incidents and resource-health signals.

**Reference links**

- [docs.cloud.google.com/hub/docs/health](https://docs.cloud.google.com/hub/docs/health)
- [docs.cloud.google.com/service-health/docs/overview](https://docs.cloud.google.com/service-health/docs/overview)
- [docs.cloud.google.com/service-health/docs/configure-alerts-dashboard](https://docs.cloud.google.com/service-health/docs/configure-alerts-dashboard)

**Related notes:** [Cloud Hub](../07-operations-cost/products/cloud-hub.md) · [Personalized Service Health](../07-operations-cost/products/personalized-service-health.md)

</details>

[Back to index](#index)

---

### Q49

> NovaRender Studios runs a large-scale visual-effects pipeline across several hundred Compute Engine instances. All rendering workers must concurrently access the same multi-terabyte collection of scene files through a POSIX-compliant file system. The storage platform must provide extremely high aggregate throughput, and the company does not want to deploy or maintain its own distributed file-system cluster. Which Google Cloud service should NovaRender Studios use?  

- **A.** Cloud SQL
- **B.** Regional Persistent Disk
- **C.** Filestore Basic
- **D.** Google Cloud Managed Lustre

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Cloud SQL is a managed relational database service for MySQL, PostgreSQL, and SQL Server workloads. It provides structured database storage accessed through SQL queries and database connections. It does not expose a POSIX-compliant shared file system that hundreds of Compute Engine instances can mount, and it is not designed to deliver parallel file access for high-performance computing workloads.

**B is incorrect** because Regional Persistent Disk provides durable block storage that is synchronously replicated across two zones in a region for high availability. A block device is not automatically a shared POSIX file system, and Regional Persistent Disk does not operate as a managed parallel file system for hundreds of concurrent workers. Building this capability with block storage would require the organization to deploy and manage an additional clustered or distributed file-system layer, which conflicts with the requirement for a fully managed solution.

**C is incorrect** because Filestore Basic provides managed NFS file shares and supports standard file-system access from Compute Engine instances. It can work well for general shared-file workloads, but the Basic tier is not a parallel file system designed for extremely high aggregate throughput across hundreds of high-performance computing workers. Its performance and scalability are more limited than the storage architecture required for a large, highly parallel rendering workload. Higher Filestore tiers can provide greater performance, but they still do not match the specific parallel file-system requirement addressed by Managed Lustre.

**D is correct** because Google Cloud Managed Lustre is a fully managed, high-performance parallel file system designed for demanding AI, machine learning, high-performance computing, rendering, and scientific workloads. It provides POSIX-compatible file access and can be mounted concurrently by many Compute Engine instances. Lustre distributes data and I/O operations across multiple storage resources, enabling very high aggregate throughput when hundreds of workers read or write the same shared dataset simultaneously. Google Cloud manages the underlying Lustre infrastructure, so NovaRender Studios does not need to install, configure, scale, patch, or operate its own distributed storage cluster.

**Reference links**

- [docs.cloud.google.com/managed-lustre/docs/overview](https://docs.cloud.google.com/managed-lustre/docs/overview)
- [docs.cloud.google.com/managed-lustre/docs/create-instance](https://docs.cloud.google.com/managed-lustre/docs/create-instance)
- [docs.cloud.google.com/filestore/docs/performance](https://docs.cloud.google.com/filestore/docs/performance)

**Related notes:** [Google Cloud Managed Lustre](../05-storage-databases-data/products/google-cloud-managed-lustre.md)

</details>

[Back to index](#index)

---

### Q50

> BrightCart operates an online retail platform on Google Cloud. During a least-privilege review, its administrators remove several IAM policy bindings from the production project. Shortly afterward, a managed Google Cloud service stops accessing a resource required for normal operation. The administrators discover that the removed binding granted a service-specific role to a Google-managed service agent. What should BrightCart do?  

- **A.** Assign the Owner role to the project’s default service account.
- **B.** Restore the documented service-specific role to the Google-managed service agent.
- **C.** Generate a service account key and configure the managed service to use it.
- **D.** Grant the removed role to allAuthenticatedUsers.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because the project’s default service account and the Google-managed service agent are separate IAM principals with different purposes. A default service account is typically used by customer workloads, such as Compute Engine virtual machines or application instances, whereas a service agent is created and managed by Google Cloud so that a particular managed service can perform operations on the customer’s behalf. Granting Owner to the default service account would not restore the missing permissions to the affected service agent. It would also violate the principle of least privilege because the Owner role provides broad control over nearly all project resources, including the ability to manage many resources and IAM policies.

**B is correct** because Google-managed service agents require specific documented service agent roles to perform actions for their associated Google Cloud services. These roles are normally granted automatically when a service is enabled or its service agent is created. If an administrator removes one of these required bindings, the service might lose access to dependent resources and stop functioning correctly. The appropriate remediation is to identify the affected service agent and restore the service-specific role documented for that agent at the required project, folder, organization, or resource level. This restores the service’s intended permissions without granting unnecessary access to unrelated principals. Service agent roles should be granted only to their corresponding service agents because these roles can contain powerful permissions specifically designed for managed service operations.

**C is incorrect** because creating a service account key does not restore an IAM role that was removed from a Google-managed service agent. IAM roles determine what actions a principal is authorized to perform, while a service account key is only a credential that can be used to authenticate as a user-managed service account. Google-managed services normally authenticate through Google-controlled service identities and do not require customers to create or distribute private keys for service agents. Introducing a key would not fix the missing authorization and would add unnecessary credential-management and security risks, including possible key exposure, rotation requirements, and unauthorized use.

**D is incorrect** because allAuthenticatedUsers is a broad special principal representing users and service accounts authenticated with a Google account or service account. Granting the missing role to this principal would expose the associated permissions to an extremely large population rather than limiting them to the affected service agent. Even if such a broad binding allowed the service agent to perform the operation, it would create a serious security vulnerability and directly contradict least-privilege access control. The role must be granted specifically to the documented Google-managed service agent rather than to a public or broadly accessible principal.

**Reference links**

- [docs.cloud.google.com/iam/docs/service-agents](https://docs.cloud.google.com/iam/docs/service-agents)
- [docs.cloud.google.com/iam/docs/create-service-agents](https://docs.cloud.google.com/iam/docs/create-service-agents)
- [docs.cloud.google.com/iam/docs/grant-role-console](https://docs.cloud.google.com/iam/docs/grant-role-console)

</details>

[Back to index](#index)

---
