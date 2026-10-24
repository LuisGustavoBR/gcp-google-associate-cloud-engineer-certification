# Practice Exam 2

[Previous](exam-1.md) · [All exams](README.md) · [Next](exam-3.md)

50 questions in the original English. Open "Show answer" under each question to see the correct answer and the explanation.

## Index

| Q | Question |
|---|---|
| [Q1](#q1) | MediCore Analytics is preparing a Google Kubernetes Engine cluster for a healthcare proces... |
| [Q2](#q2) | StreamForge runs a video-processing service on a Google Kubernetes Engine cluster. The tea... |
| [Q3](#q3) | StreamNest operates a serverless video-processing application on Google Cloud. The develop... |
| [Q4](#q4) | BrightRoute Logistics must move its dispatch and warehouse applications to Google Cloud be... |
| [Q5](#q5) | PulseWave Gaming operates a fast-growing multiplayer platform whose customers are currentl... |
| [Q6](#q6) | BlueHarbor Analytics operates an on-premises retail insights platform that includes below ... |
| [Q7](#q7) | PulseCart, an online retail company, has packaged its inventory API into a Docker image. T... |
| [Q8](#q8) | HarborDesk Logistics uses an internal order-processing portal that is accessed only by emp... |
| [Q9](#q9) | BrightCart operates several PostgreSQL databases in its private data center and plans to m... |
| [Q10](#q10) | BrightPath Analytics is onboarding employees to its new Cloud Identity domain. Several emp... |
| [Q11](#q11) | Northwind Commerce is moving its Terraform-based CI/CD automation to dedicated Compute Eng... |
| [Q12](#q12) | ShopSphere is deploying an order-processing service on Cloud Run that connects to a Cloud ... |
| [Q13](#q13) | Crestline Foods has a Google Cloud project named Inventory Pulse with the project ID crest... |
| [Q14](#q14) | Northstar Media processes analytics data for its streaming platform every evening. Each pr... |
| [Q15](#q15) | SouthernCross Health Analytics processes regulated healthcare data in Google Cloud. The co... |
| [Q16](#q16) | AuroraMart publishes a BigQuery dataset containing anonymized inventory and customer-order... |
| [Q17](#q17) | TrailCart runs a customer marketplace, a delivery portal, and an analytics application on ... |
| [Q18](#q18) | BluePeak Media operates a Google Kubernetes Engine cluster named qa-hub in Google Cloud. A... |
| [Q19](#q19) | Northwind Metrics uses Looker Studio to display sales dashboards based on a BigQuery summa... |
| [Q20](#q20) | NimbusCart uses the Google Cloud CLI from an administrator’s laptop through an authenticat... |
| [Q21](#q21) | Northstar Finance uses an Application Design Center template to deploy a standardized empl... |
| [Q22](#q22) | PulseCart is launching an updated checkout experience on Google Cloud. The operations team... |
| [Q23](#q23) | LedgerPeak Insurance is migrating claim documents from its data center to Cloud Storage. T... |
| [Q24](#q24) | LedgerHaven operates a digital records portal that stores signed audit documents in a Clou... |
| [Q25](#q25) | ParcelPilot, a delivery-tracking application, has completed testing of an AI agent that he... |
| [Q26](#q26) | HarborPulse, a maritime logistics company, stores vessel telemetry files in Cloud Storage.... |
| [Q27](#q27) | PixelNest Media stores completed image-processing files in a Cloud Storage bucket by using... |
| [Q28](#q28) | Northstar Retail deployed a new version of its inventory API to Google Kubernetes Engine (... |
| [Q29](#q29) | StreamNest has completed a new release of its video-transcoding API and stored the product... |
| [Q30](#q30) | TrailPulse operates a fitness-tracking application on a Compute Engine VM instance. The ap... |
| [Q31](#q31) | OrbitFleet is migrating its containerized logistics applications to Kubernetes clusters ru... |
| [Q32](#q32) | NimbusCart is moving its retail applications from an on-premises environment to Google Clo... |
| [Q33](#q33) | BrightCart is launching an online storefront on a Compute Engine VM. The company has creat... |
| [Q34](#q34) | BrightCart runs an order-processing API on a regional Compute Engine managed instance grou... |
| [Q35](#q35) | Northstar Retail operates a production order-processing database on Spanner in a regional ... |
| [Q36](#q36) | ParcelPulse operates a package-tracking platform on Google Kubernetes Engine. Its real-tim... |
| [Q37](#q37) | Northstar Media deploys its streaming services to Google Kubernetes Engine (GKE) by applyi... |
| [Q38](#q38) | LedgerSpring Insurance generates daily financial reconciliation reports after business hou... |
| [Q39](#q39) | PulseTrack is developing a public web application that responds asynchronously to events g... |
| [Q40](#q40) | AuroraFleet, a logistics analytics company, runs 11 Linux virtual machines on Compute Engi... |
| [Q41](#q41) | Lexora Health wants to fine-tune open large language models by using several terabytes of ... |
| [Q42](#q42) | LedgerLoop operates many independent Google Cloud projects for its financial analytics tea... |
| [Q43](#q43) | BrightPath Media manages several production projects inside a folder named Digital Operati... |
| [Q44](#q44) | AsterPeak Manufacturing is migrating its SAP HANA database to Compute Engine. The database... |
| [Q45](#q45) | HarborCart operates an online marketplace supported by 32 development squads. Each squad r... |
| [Q46](#q46) | MetroPulse operates a city transit application that occasionally fails to process ticket p... |
| [Q47](#q47) | HealthAxis operates a patient analytics platform backed by a Bigtable instance with five n... |
| [Q48](#q48) | Northstar Labs maintains a local repository containing a Python API, automated tests, and ... |
| [Q49](#q49) | BrightTrail Media has validated Terraform modules for VPC networking, Cloud Run services, ... |
| [Q50](#q50) | ClearRoute Insurance has finished testing an AI agent that helps employees summarize claim... |

---

### Q1

> MediCore Analytics is preparing a Google Kubernetes Engine cluster for a healthcare processing service. The cluster must cryptographically verify the identity and boot integrity of every worker node. Worker nodes must use only internal IP addresses and must not be directly reachable from the public internet. The platform team also wants Google Cloud to manage node provisioning, scaling, security configuration, and maintenance wherever possible. What should the team do?  

- **A.** Deploy a private Autopilot cluster.
- **B.** Deploy a public Autopilot cluster.
- **C.** Deploy a Standard public cluster and enable Shielded GKE Nodes.
- **D.** Deploy a Standard private cluster and enable Shielded GKE Nodes.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a private Autopilot cluster satisfies all the requirements with the lowest operational burden. Private nodes use internal IP addresses and do not have external IP addresses, preventing direct access to the nodes from the public internet. Autopilot mode also enables Shielded GKE Nodes by default, and this setting cannot be disabled. Shielded GKE Nodes use capabilities such as virtual Trusted Platform Module, secure boot measurements, and integrity monitoring to provide verifiable node identity and boot integrity. In addition, Google manages the nodes, scaling, security settings, and much of the cluster infrastructure in Autopilot mode. This reduces the administrative effort associated with configuring node pools, selecting machine types, scaling nodes, and maintaining node infrastructure. Private nodes can still reach required external services through a controlled mechanism such as Cloud NAT when outbound internet access is necessary.

**B is incorrect** because Autopilot provides the required managed operations and automatically enforces Shielded GKE Nodes, but a public Autopilot cluster does not meet the requirement that nodes must not be accessible from the internet. Public nodes can receive external IP addresses, which creates a potential path for internet connectivity to the node infrastructure. Firewall rules can restrict inbound access, but using private nodes is the Google-recommended design when nodes must not have direct public internet exposure. Therefore, Autopilot addresses the operational and node-integrity requirements, but the public networking configuration fails the network-isolation requirement.

**C is incorrect** because enabling Shielded GKE Nodes provides verifiable node identity and integrity, but a public Standard cluster does not satisfy the requirement to prevent internet access to the nodes. Public nodes can have external IP addresses, even when firewall rules limit the traffic that is allowed to reach them. Standard mode also requires the platform team to manage more of the cluster configuration, including node pools, machine types, scaling settings, upgrades, and other infrastructure decisions. Consequently, this option fails the private-node requirement and creates more operational work than an Autopilot cluster.

**D is incorrect** because a Standard private cluster with Shielded GKE Nodes can technically satisfy the security and networking requirements. Private nodes use internal IP addresses, and Shielded GKE Nodes provide cryptographically verifiable node identity and integrity. However, Standard mode gives the customer significantly more responsibility for configuring and managing node pools, capacity, scaling, upgrades, and security settings. Because the company specifically wants to reduce cluster-management overhead and follow Google-recommended practices, a private Autopilot cluster is the better solution. Shielded GKE Nodes are already mandatory in Autopilot, so the team receives the required protection without managing the feature separately.

**Reference links**

- [cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview](https://cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview)
- [cloud.google.com/kubernetes-engine/docs/how-to/shielded-gke-nodes](https://cloud.google.com/kubernetes-engine/docs/how-to/shielded-gke-nodes)
- [cloud.google.com/kubernetes-engine/docs/concepts/network-isolation](https://cloud.google.com/kubernetes-engine/docs/concepts/network-isolation)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q2

> StreamForge runs a video-processing service on a Google Kubernetes Engine cluster. The team does not yet know how much CPU and memory each Pod requires because demand changes with customer traffic, media file sizes, and third-party service response times. StreamForge wants the workload to remain responsive while receiving cost-effective CPU and memory recommendations based on actual usage. What should the team do?  

- **A.** Configure the Horizontal Pod Autoscaler to maintain workload availability, and use the cluster autoscaler to generate CPU and memory recommendations.
- **B.** Configure the Horizontal Pod Autoscaler to maintain workload availability, and enable Vertical Pod Autoscaler recommendations to obtain CPU and memory suggestions.
- **C.** Enable Vertical Pod Autoscaler recommendations to maintain workload availability, and use the cluster autoscaler to generate CPU and memory suggestions.
- **D.** Enable Vertical Pod Autoscaler recommendations to maintain workload availability, and use the Horizontal Pod Autoscaler to generate CPU and memory suggestions.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because the Horizontal Pod Autoscaler is appropriate for maintaining workload responsiveness and availability by increasing or decreasing the number of Pod replicas according to metrics such as CPU utilization, memory utilization, custom metrics, or external metrics. However, the cluster autoscaler does not analyze individual containers and recommend suitable CPU and memory requests. Its purpose is to adjust the number of nodes in a GKE Standard cluster when Pods cannot be scheduled because the cluster lacks capacity or when nodes are underutilized and can be removed. It operates at the cluster infrastructure level rather than providing resource-sizing recommendations for individual workloads.

**B is correct** because the Horizontal Pod Autoscaler can automatically adjust the number of Pod replicas as demand changes, helping the application continue serving traffic during varying usage patterns. Vertical Pod Autoscaler recommendations analyze historical and current workload resource usage and provide suggested CPU and memory requests for the workload’s containers. Using Vertical Pod Autoscaler in recommendation-only mode allows the team to review and apply cost-effective resource values without automatically restarting or modifying running Pods. This combination addresses both requirements: the Horizontal Pod Autoscaler supports consistent workload performance by scaling replicas, while Vertical Pod Autoscaler recommendations help prevent overprovisioning and underprovisioning by suggesting appropriate CPU and memory settings. Because the Vertical Pod Autoscaler is used only for recommendations, it does not automatically change resource requests in a way that could interfere with Horizontal Pod Autoscaler behavior.

**C is incorrect** because Vertical Pod Autoscaler recommendations do not directly maintain workload availability. Recommendation-only mode analyzes resource consumption and publishes suggested CPU and memory requests, but it does not automatically modify the workload, add Pod replicas, or respond to traffic increases. The cluster autoscaler also does not generate CPU and memory recommendations for containers. It scales the number of cluster nodes according to the scheduling requirements of Pods. Therefore, this combination neither provides automatic Pod-level scaling for availability nor uses the correct service for workload resource recommendations.

**D is incorrect** because the roles of the two autoscalers are reversed. Vertical Pod Autoscaler recommendation mode provides CPU and memory sizing suggestions but does not automatically scale the number of Pods to maintain responsiveness during traffic changes. The Horizontal Pod Autoscaler changes the number of Pod replicas based on observed metrics, but it does not recommend appropriate CPU and memory requests for each container. Consequently, Vertical Pod Autoscaler recommendations should be used for resource-sizing suggestions, while the Horizontal Pod Autoscaler should be used to scale replicas and support workload availability.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/horizontalpodautoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/horizontalpodautoscaler)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/verticalpodautoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/verticalpodautoscaler)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler)

**Related notes:** [HPA, VPA, and cluster autoscaler](../03-compute-containers/products/hpa-vpa-and-cluster-autoscaler.md)

</details>

[Back to index](#index)

---

### Q3

> StreamNest operates a serverless video-processing application on Google Cloud. The development team wants to release an updated application version to 8% of users, monitor its behavior, and then gradually increase its share of production traffic. Which deployment approach should the team use?  

- **A.** Deploy the application to Cloud Run and use revision-based traffic splitting for a gradual rollout.
- **B.** Deploy the application to Google Kubernetes Engine and use Cloud Service Mesh for traffic splitting.
- **C.** Deploy the application as a Cloud Run function and include the release number in each function’s name.
- **D.** Deploy the application to App Engine and create a separate service for every application release.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Cloud Run is a fully managed serverless application platform that automatically creates an immutable revision whenever a new application version is deployed. Cloud Run can divide incoming traffic between multiple revisions by percentage, allowing the team to send a small amount of production traffic, such as 8%, to the new revision while the existing stable revision continues receiving the remaining traffic. The team can monitor errors, latency, logs, and application behavior before gradually increasing the new revision’s traffic allocation. If the new revision has problems, traffic can be moved back to the stable revision without redeploying the application. This directly supports canary releases, gradual rollouts, traffic migration, and rollbacks while preserving the serverless requirement.

**B is incorrect** because Google Kubernetes Engine is a managed Kubernetes platform rather than the most direct serverless application platform requested in the question. Cloud Service Mesh, formerly called Anthos Service Mesh, can perform weighted traffic splitting and support canary deployments between Kubernetes workloads. However, this solution requires a GKE cluster, Kubernetes resources, workload configuration, and service-mesh administration. It introduces substantially more operational complexity than Cloud Run. Although the traffic-splitting capability is technically possible, the architecture does not best satisfy the requirement to deploy the application by using serverless technology.

**C is incorrect** because adding a release number to the name of a Cloud Run function creates separately named functions rather than configuring controlled percentage-based traffic distribution. A function name identifies a deployed function; it does not tell Google Cloud to route a specified percentage of production requests to that function. The team would need an additional routing component to distribute traffic between the separately named functions. Cloud Run functions are appropriate for event-driven and HTTP function workloads, but merely changing function names does not implement a gradual rollout.

**D is incorrect** because App Engine services are intended to represent separate logical components of an application, while releases of the same component should normally be deployed as different versions within one service. App Engine can split traffic between versions of the same service, so creating an entirely new service for every release is unnecessary and does not directly configure the required percentage-based rollout. The proposed design confuses services with versions and would require additional routing configuration. Although App Engine supports serverless application hosting and version traffic splitting, the specific procedure described in this option is incorrect.

**Reference links**

- [docs.cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration](https://docs.cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration)
- [docs.cloud.google.com/service-mesh/docs/service-routing/advanced-traffic-management](https://docs.cloud.google.com/service-mesh/docs/service-routing/advanced-traffic-management)
- [docs.cloud.google.com/appengine/docs/standard/splitting-traffic](https://docs.cloud.google.com/appengine/docs/standard/splitting-traffic)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md)

</details>

[Back to index](#index)

---

### Q4

> BrightRoute Logistics must move its dispatch and warehouse applications to Google Cloud before its colocation agreement expires. Its current network has no connection to Google Cloud. The company will rehost the applications without redesigning them and modernize them later. Several legacy services communicate by using hard-coded private IP addresses rather than DNS names. BrightRoute wants the fastest migration possible without changing application code or disrupting application communication. What should the company do?  

- **A.** Move the internal DNS server first, create a Cloud DNS forwarding zone that sends queries to the migrated DNS server, and migrate the remaining workloads with ephemeral internal IP addresses.
- **B.** Create a VPC network whose subnet CIDR ranges do not overlap with the existing environment, and assign a new static internal IP address to each migrated workload.
- **C.** Create a VPC network whose subnet CIDR ranges match the existing environment, and assign each migrated workload its original static internal IP address.
- **D.** Place every migrated workload in one VPC subnet, configure Cloud NAT for that subnet, and manually assign a static IP address to the Cloud NAT gateway.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the applications communicate through hard-coded IP addresses, so migrating the DNS server does not solve the underlying dependency. DNS forwarding is useful when applications resolve hostnames and need DNS queries forwarded between environments. In this case, the applications do not perform name resolution for these connections; they directly send traffic to specific internal IP addresses. Assigning ephemeral internal IP addresses would allow Google Cloud to select addresses automatically, and those addresses could differ from the addresses expected by the applications. Ephemeral addresses can also be released when resources are deleted or re-created. Consequently, the existing application configuration would point to incorrect destinations and communication would fail.

**B is incorrect** because non-overlapping CIDR ranges are normally desirable when an on-premises network and a VPC network must communicate through Cloud VPN, Cloud Interconnect, VPC Network Peering, or another routed connection. However, the two environments in this scenario are not connected, and the immediate requirement is to preserve hard-coded IP-based communication without modifying the applications. Assigning new static internal IP addresses would make the addresses persistent, but persistence alone is insufficient. The addresses would still differ from those embedded in the application code or configuration. Each affected application would therefore require configuration or code changes, which conflicts with the lift-and-shift requirement.

**C is correct** because recreating the existing CIDR ranges in the VPC network makes it possible to assign the migrated workloads the same internal IP addresses they used in the original environment. Static internal IP addresses preserve those assignments instead of allowing Google Cloud to allocate arbitrary ephemeral addresses. As a result, applications that send traffic to hard-coded private IP addresses can continue reaching the expected services without application changes. Using overlapping address space would normally create routing problems if the VPC and the original network were connected, because routers could not reliably distinguish between identical destination ranges. In this scenario, however, there is no network connection between the environments, so the duplicate CIDR ranges do not create a routing conflict. Workloads with interdependencies should be migrated in a coordinated migration wave so that services that need to communicate are available together in the new VPC.

**D is incorrect** because Cloud NAT does not preserve the internal destination addresses used for communication between workloads in a VPC. Public NAT primarily enables resources without external IP addresses to initiate outbound connections while translating their source addresses to external NAT IP addresses. It is not a mechanism for assigning legacy internal IP addresses to individual virtual machines or for redirecting hard-coded east-west application traffic. Cloud NAT is also a distributed, software-defined service rather than a traditional gateway appliance through which all VPC traffic passes. Assigning a NAT address would therefore not make each workload reachable through its former private IP address, and placing all workloads in one subnet would not solve the hard-coded address mismatch.

**Reference links**

- [docs.cloud.google.com/vpc/docs/subnets](https://docs.cloud.google.com/vpc/docs/subnets)
- [docs.cloud.google.com/vpc/docs/reserve-static-internal-ip-address](https://docs.cloud.google.com/vpc/docs/reserve-static-internal-ip-address)
- [docs.cloud.google.com/nat/docs/overview](https://docs.cloud.google.com/nat/docs/overview)

**Related notes:** [VPC, Subnets, and IPs](../06-networking/products/vpc-subnets-and-ips.md)

</details>

[Back to index](#index)

---

### Q5

> PulseWave Gaming operates a fast-growing multiplayer platform whose customers are currently concentrated in Canada. Its transactional PostgreSQL database runs in a Toronto data center and cannot handle the platform’s increasing traffic. PulseWave needs a managed Google Cloud database that can scale automatically, support deployment across multiple regions as the business expands globally, and provide low-latency access to application data. What should the company do?  

- **A.** Migrate the transactional data to BigQuery.
- **B.** Migrate the transactional database to Spanner.
- **C.** Migrate the database to Cloud SQL for PostgreSQL.
- **D.** Migrate the transactional data to Bigtable.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because BigQuery is a serverless analytical data warehouse designed for large-scale analytics, reporting, and processing complex queries over very large datasets. It is not intended to serve as the primary operational database for a social or gaming platform that requires frequent low-latency transactional reads and writes. BigQuery can scale automatically and process data across Google Cloud infrastructure, but its architecture and query execution model are optimized for analytical workloads rather than online transaction processing. It would be appropriate for analyzing user activity, engagement metrics, or historical events, but not for replacing the platform’s main PostgreSQL transactional database.

**B is correct** because Spanner is a fully managed, horizontally scalable relational database designed for transactional applications that need strong consistency, high availability, and global distribution. It supports regional, dual-region, and multi-region instance configurations, allowing PulseWave to initially place resources near its Canadian users and later distribute database replicas across multiple geographic regions. Spanner can increase or decrease compute capacity through managed autoscaling as application demand changes. It also provides SQL support, relational schemas, ACID transactions, and strong consistency, making it suitable for a rapidly growing transactional application. By choosing an appropriate instance configuration and placing application services close to the database’s read-write or read-only replicas, the company can maintain low latency while gaining the scalability and multi-region capabilities required for future expansion. Migrating from PostgreSQL might require schema and application adjustments because Spanner is not a managed PostgreSQL server, although Spanner supports a PostgreSQL interface that improves compatibility with PostgreSQL tools and syntax.

**C is incorrect** because Cloud SQL for PostgreSQL is a managed relational database service that provides strong PostgreSQL compatibility and would usually require fewer application changes during migration. It supports vertical scaling, read replicas, regional high availability, and cross-region replicas. However, its primary instance remains associated with one region, and cross-region replicas are primarily used for read scaling and disaster recovery. It does not provide the same native horizontal write scaling and globally distributed, synchronously replicated transactional architecture as Spanner. Cloud SQL could be appropriate when PostgreSQL compatibility and migration simplicity are the main requirements, but it is not the best option when automatic scaling, large-scale growth, and native multi-region transactional operation are the dominant requirements.

**D is incorrect** because Bigtable is a highly scalable, low-latency NoSQL wide-column database designed for large volumes of single-keyed data, such as time-series information, telemetry, personalization data, financial data, and high-throughput operational records. Bigtable supports replication across regions and can scale to very large workloads, but it does not provide a traditional relational data model, PostgreSQL compatibility, joins, or general-purpose relational transactions. Migrating an existing PostgreSQL application to Bigtable would typically require substantial data-model and application redesign. Because the platform currently relies on a relational PostgreSQL database and requires a scalable multi-region transactional database, Spanner is the more suitable choice.

**Reference links**

- [docs.cloud.google.com/spanner/docs/instance-configurations](https://docs.cloud.google.com/spanner/docs/instance-configurations)
- [docs.cloud.google.com/spanner/docs/autoscaling-overview](https://docs.cloud.google.com/spanner/docs/autoscaling-overview)
- [docs.cloud.google.com/bigtable/docs/overview](https://docs.cloud.google.com/bigtable/docs/overview)

**Related notes:** [Spanner](../05-storage-databases-data/products/spanner.md)

</details>

[Back to index](#index)

---

### Q6

> BlueHarbor Analytics operates an on-premises retail insights platform that includes below mentioned tech-stack. BlueHarbor Analytics wants to migrate these workloads to Google Cloud while minimizing infrastructure management and operational costs. The company prefers serverless services that can automatically scale based on demand. What should the company do?  
> -A Python Flask customer portal  
> -A REST API used by mobile applications  
> -A scheduled background process that performs data transformation and generates nightly reports  

- **A.** -Deploy the Flask portal to App Engine and the REST API to Cloud Run.  
  -Use Cloud Tasks to execute the background process on Compute Engine.
- **B.** -Deploy the Flask portal to App Engine and the REST API to Cloud Run.  
  -Use Cloud Tasks to execute the background process on Cloud Run.
- **C.** -Host the Flask portal in a Cloud Storage bucket and deploy the REST API to Cloud Run.  
  -Use Cloud Tasks to execute the background process on Cloud Run.
- **D.** -Host the Flask portal in a Cloud Storage bucket and deploy the REST API to Cloud Run.  
  -Use Cloud Tasks to execute the background process on Compute Engine.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because App Engine is a managed platform that can run the Python Flask portal, and Cloud Run is a suitable serverless platform for the containerized REST API. However, running the background process on Compute Engine introduces virtual machine administration. The company would need to manage VM configuration, operating system updates, security patches, capacity, availability, and idle resources. Although Cloud Tasks can send requests to an HTTP worker running on Compute Engine, this design does not provide a completely serverless architecture and can create higher operational costs than using Cloud Run.

**B is correct** because all three workloads are migrated to managed, serverless Google Cloud services. App Engine can run the Flask portal without requiring the company to manage servers and can automatically scale application instances according to incoming traffic. Cloud Run is appropriate for the REST API because it runs containerized applications, automatically scales based on requests, and can scale to zero when no requests are being processed. Cloud Tasks can place background work in a managed queue and securely send each task to a Cloud Run service for asynchronous processing. Cloud Tasks also provides configurable retries, rate controls, scheduling parameters, and delivery management. This architecture minimizes infrastructure administration and avoids maintaining continuously running virtual machines. Each background task must remain within the applicable Cloud Tasks dispatch deadline and Cloud Run request-timeout limits.

**C is incorrect** because a Cloud Storage bucket can host only static website content, such as HTML, CSS, JavaScript, images, and downloadable files. It does not provide a Python runtime and cannot execute server-side Flask application code. The REST API and background processing components are appropriately placed on Cloud Run, but the Flask portal cannot be migrated directly to Cloud Storage without redesigning it as a completely static frontend.

**D is incorrect** because it contains two unsuitable design decisions. First, Cloud Storage cannot execute the server-side Python code required by a Flask application. Second, using Compute Engine for the background process requires VM provisioning, maintenance, patching, monitoring, and capacity management. This approach therefore fails to provide the requested serverless architecture and does not minimize operational overhead as effectively as using App Engine, Cloud Run, and Cloud Tasks.

**Reference links**

- [docs.cloud.google.com/appengine/docs/standard/python3/building-app](https://docs.cloud.google.com/appengine/docs/standard/python3/building-app)
- [docs.cloud.google.com/run/docs/triggering/using-tasks](https://docs.cloud.google.com/run/docs/triggering/using-tasks)
- [docs.cloud.google.com/storage/docs/hosting-static-website](https://docs.cloud.google.com/storage/docs/hosting-static-website)

**Related notes:** [Cloud Tasks](../04-events-integration/products/cloud-tasks.md)

</details>

[Back to index](#index)

---

### Q7

> PulseCart, an online retail company, has packaged its inventory API into a Docker image. The development team wants to run the application as a managed workload on Google Kubernetes Engine and allow Kubernetes to maintain the required Pods. What should the team do?  

- **A.** Store the Docker image in Cloud Storage and create a Kubernetes Service that references the image.
- **B.** Store the Docker image in Cloud Storage and create a Kubernetes Deployment that references the image.
- **C.** Push the Docker image to Artifact Registry and create a Kubernetes Service that references the image.
- **D.** Push the Docker image to Artifact Registry and create a Kubernetes Deployment that references the image.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Cloud Storage is a general-purpose object storage service and is not a container image registry from which GKE normally pulls Docker or OCI container images. In addition, a Kubernetes Service does not define or deploy a container image. A Service provides a stable network endpoint for an existing group of Pods, usually by selecting them through labels. Because this option provides neither a supported container registry reference nor a workload controller that creates Pods, it cannot deploy the application as a GKE workload.

**B is incorrect** because a Kubernetes Deployment is the appropriate type of resource for running and managing a typical stateless containerized workload, but storing the Docker image in Cloud Storage is not the correct image-distribution method. A Deployment’s Pod template must reference a container image in a registry that the GKE nodes can access and authenticate to. Cloud Storage can hold an exported image archive as a file, but a Kubernetes Deployment cannot use a Cloud Storage object URL as its standard container image reference. The image should first be pushed to Artifact Registry.

**C is incorrect** because Artifact Registry is the correct Google Cloud service for storing and distributing Docker container images, but a Kubernetes Service is not responsible for creating or managing the application’s Pods. A Service routes network traffic to Pods that already exist and match its label selector. It does not contain a Pod template, container image specification, replica count, or rollout strategy. Therefore, the image would be stored correctly, but the application workload would not be deployed. A Service could be created afterward when the running Pods need a stable internal or external network endpoint.

**D is correct** because Artifact Registry is the current Google Cloud service for securely storing and managing Docker and OCI container images, and a Kubernetes Deployment is designed to create and manage application Pods. The team pushes the image to an Artifact Registry Docker repository and places its fully qualified Artifact Registry image URI in the Deployment’s Pod template. GKE then pulls the image and runs it in the Pods created by the Deployment. The Deployment also manages the requested number of replicas, replaces failed Pods, and supports controlled application updates and rollbacks through ReplicaSets. Container Registry, which appeared in the original service terminology, has been deprecated and shut down for image writes, so Artifact Registry is the appropriate current service. A Kubernetes Service is necessary only when the workload must be reachable through a stable network endpoint; it is not required merely to deploy the container workload.

**Reference links**

- [docs.cloud.google.com/artifact-registry/docs/integrate-gke](https://docs.cloud.google.com/artifact-registry/docs/integrate-gke)
- [docs.cloud.google.com/kubernetes-engine/docs/deploy-app-cluster](https://docs.cloud.google.com/kubernetes-engine/docs/deploy-app-cluster)
- [kubernetes.io/docs/concepts/workloads/controllers/deployment/](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)

**Related notes:** [Artifact Registry](../03-compute-containers/products/artifact-registry.md)

</details>

[Back to index](#index)

---

### Q8

> HarborDesk Logistics uses an internal order-processing portal that is accessed only by employees at its Bengaluru office. The portal performs frequent relational queries and updates several related tables within a single transaction. Its existing database and application code use PostgreSQL, and the company wants to migrate to Google Cloud without redesigning the application. Which database service should the company select?  

- **A.** BigQuery
- **B.** Cloud SQL for PostgreSQL
- **C.** Spanner
- **D.** Firestore in Datastore mode

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because BigQuery is a serverless enterprise data warehouse designed primarily for analytics, reporting, large-scale data processing, and queries that scan substantial datasets. Although BigQuery supports SQL and can process transactional data for analytical purposes, it is not intended to serve as the primary operational database for a latency-sensitive order-processing application that continuously performs individual inserts, updates, and multi-table transactions. Moving an existing PostgreSQL transactional application to BigQuery would also require significant changes to the application’s schema, query patterns, transaction logic, and database connectivity. BigQuery is more appropriate for analyzing historical order data than for managing live transactional orders.

**B is correct** because Cloud SQL for PostgreSQL is a fully managed relational database service that runs PostgreSQL on Google Cloud. It supports relational schemas, indexes, joins, constraints, fast operational queries, and ACID transactions involving multiple tables. Because the existing application already uses PostgreSQL, Cloud SQL for PostgreSQL allows the company to retain most of its existing SQL statements, database drivers, schemas, transaction logic, and PostgreSQL-compatible tools. This results in substantially fewer application changes than moving to a different database model. The application is used from one physical location and does not indicate a requirement for global horizontal scalability or globally distributed transactions, so the additional scale and architectural complexity of Spanner are unnecessary. Cloud SQL therefore provides the required transactional capabilities while best satisfying the minimal-code-change requirement.

**C is incorrect** because Spanner is a distributed relational database designed for applications that require horizontal scalability, high availability, strong consistency, and transactions across large regional or global deployments. Spanner supports ACID transactions and provides a PostgreSQL interface, but that interface is not identical to running a standard PostgreSQL database. Differences can exist in supported PostgreSQL features, data types, SQL syntax, extensions, transaction behavior, client libraries, schema design, sequences, and database administration functionality. Migrating an existing PostgreSQL application to Spanner can therefore require assessment, schema conversion, query modifications, application refactoring, and testing. Spanner would be appropriate if HarborDesk required massive scale or geographically distributed transactional processing, but those requirements are absent. Cloud SQL for PostgreSQL provides a simpler migration with fewer code changes.

**D is incorrect** because Firestore in Datastore mode is a NoSQL document database rather than a PostgreSQL-compatible relational database. It stores data as entities or documents instead of conventional relational tables and does not support PostgreSQL SQL, relational joins, foreign-key relationships, or the same multi-table transaction model used by the existing application. Although Firestore in Datastore mode provides strong consistency and transactional capabilities, migrating the order-processing application would require redesigning the relational data model, replacing SQL queries, modifying transaction logic, and changing the application’s database access layer. This conflicts with the requirement to deploy the PostgreSQL application with minimal code changes.

**Reference links**

- [docs.cloud.google.com/sql/docs/postgres](https://docs.cloud.google.com/sql/docs/postgres)
- [docs.cloud.google.com/spanner/docs/postgresql-interface](https://docs.cloud.google.com/spanner/docs/postgresql-interface)
- [docs.cloud.google.com/datastore/docs/concepts/overview](https://docs.cloud.google.com/datastore/docs/concepts/overview)

**Related notes:** [Cloud SQL](../05-storage-databases-data/products/cloud-sql.md)

</details>

[Back to index](#index)

---

### Q9

> BrightCart operates several PostgreSQL databases in its private data center and plans to migrate them to Google Cloud. The company wants substantially faster transactional and analytical query performance without redesigning its relational schemas or extensively modifying its applications. Its combined database footprint in each region is expected to grow beyond 180 TB. BrightCart also wants a fully managed solution that follows Google-recommended practices and reduces ongoing administrative effort. What should BrightCart do?  

- **A.** Migrate the databases to AlloyDB.
- **B.** Migrate the databases to Spanner.
- **C.** Migrate the databases to Firebase.
- **D.** Migrate the databases to Bigtable.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because AlloyDB for PostgreSQL is a fully managed, PostgreSQL-compatible relational database designed for demanding enterprise workloads. Its PostgreSQL compatibility allows BrightCart to retain most existing schemas, SQL queries, drivers, tools, and application logic, which minimizes migration-related code changes. AlloyDB uses a Google-built database engine and a disaggregated compute-and-storage architecture to provide significantly better transactional and analytical performance than standard PostgreSQL. Features such as automatic storage management, high availability, automated backups, point-in-time recovery, read pools, query insights, and managed maintenance reduce operational effort and cost. Because BrightCart has multiple databases, its aggregate regional footprint can be distributed across multiple appropriately sized AlloyDB clusters rather than requiring all regional data to reside in one cluster. This makes AlloyDB the best match for PostgreSQL compatibility, higher performance, large aggregate capacity, and reduced database administration.

**B is incorrect** because Spanner is an excellent choice for applications requiring virtually unlimited horizontal scalability, strong consistency, and regional or global distribution, but it is not fully compatible with standard PostgreSQL. Spanner offers a PostgreSQL interface, but that interface exposes Spanner capabilities through PostgreSQL-like syntax and does not support every PostgreSQL feature, data type, extension, client, transaction behavior, or query pattern. Migrating existing PostgreSQL workloads to Spanner can require schema redesign, careful primary-key selection, SQL modification, application refactoring, and changes to database connectivity. Spanner could handle the required data volume, but it conflicts with BrightCart’s primary requirement to minimize schema and application changes. The additional migration and engineering work can also increase operational and implementation costs.

**C is incorrect** because Firebase is an application-development platform whose database offerings, such as Cloud Firestore and Firebase Realtime Database, are document-oriented or JSON-based NoSQL services. They are commonly used for mobile and web applications that need real-time synchronization, offline support, and direct client integration. Firebase does not provide a PostgreSQL-compatible relational engine and cannot directly preserve PostgreSQL schemas, joins, constraints, stored procedures, extensions, or existing SQL-based application behavior. Migrating these databases to Firebase would require a substantial data-model redesign and extensive application-code changes, making it unsuitable for this relational enterprise migration.

**D is incorrect** because Bigtable is a distributed wide-column NoSQL database optimized for extremely large, low-latency workloads such as time-series data, telemetry, financial market data, personalization, and high-throughput key-based access. Although Bigtable can scale to very large data volumes, it does not provide PostgreSQL compatibility or the same relational database capabilities. A migration from PostgreSQL to Bigtable would require redesigning tables around row keys and access patterns, denormalizing relational data, replacing joins and relational constraints, and rewriting the application’s data-access layer. Therefore, Bigtable satisfies the scale requirement but does not satisfy the requirement to minimize schema and application changes.

**Reference links**

- [docs.cloud.google.com/alloydb/docs/overview](https://docs.cloud.google.com/alloydb/docs/overview)
- [docs.cloud.google.com/alloydb/quotas](https://docs.cloud.google.com/alloydb/quotas)
- [docs.cloud.google.com/spanner/docs/postgresql-interface](https://docs.cloud.google.com/spanner/docs/postgresql-interface)

**Related notes:** [AlloyDB](../05-storage-databases-data/products/alloydb.md)

</details>

[Back to index](#index)

---

### Q10

> BrightPath Analytics is onboarding employees to its new Cloud Identity domain. Several employees previously created unmanaged Google Accounts using their corporate email addresses. The administrator wants to bring these accounts under organizational management while preserving the users’ existing Google data and preventing conflicting accounts. What should the administrator do?  

- **A.** Send account transfer invitations to the users who have unmanaged Google Accounts.
- **B.** Ask the users to add alternate email aliases to their unmanaged Google Accounts.
- **C.** Require the users to delete their unmanaged Google Accounts before managed accounts are created.
- **D.** Ask the users to remove personal messages and files from their unmanaged Google Accounts.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Cloud Identity provides a process for transferring unmanaged Google Accounts into an organization’s managed account environment. An unmanaged account can exist when an employee independently creates a Google Account using an email address belonging to the organization’s verified domain. The administrator can identify the unmanaged account and send the user an invitation to transfer it. After the user accepts the invitation, the account becomes managed by the organization while retaining its identity and supported data. Completing this transfer before provisioning a separate managed account with the same username helps prevent a conflicting account, in which an unmanaged account and a managed account are associated with the same corporate email address. The transfer process is therefore the recommended approach when the organization wants to preserve the existing account and bring it under Cloud Identity administration.

**B is incorrect** because adding an email alias does not transfer ownership or administrative control of the unmanaged Google Account to the Cloud Identity organization. An alias is simply an additional email address associated with an account and does not resolve the underlying identity-management problem. The original unmanaged account would remain controlled by the individual rather than by the organization. In addition, Cloud Identity’s process for finding unmanaged accounts primarily evaluates the account’s primary email address against the organization’s verified domains; changing or adding aliases is not the recommended method for consolidating accounts. The administrator should instead invite the account owner to transfer the existing account.

**C is incorrect** because deleting the existing account is unnecessarily destructive and can result in the loss of data, access permissions, service configurations, and resources associated with that identity. Google provides an account transfer process specifically so that eligible unmanaged accounts can be converted into managed accounts without requiring account deletion. Although an organization might eventually create a new managed account when a user refuses to transfer the unmanaged account, forcing deletion is not the recommended initial practice. The administrator should first send a transfer invitation so that the existing identity and supported data can be preserved.

**D is incorrect** because removing personal email or other personal content does not change whether the Google Account is managed or unmanaged. A conflict is caused by the identity and username relationship, not by the type of content stored in the account. Even after personal content is removed, the user would still control an unmanaged Google Account using the organization’s domain. Creating a separate Cloud Identity account with the same username could therefore still produce a conflicting account. The account must be transferred into the organization or otherwise renamed outside the verified domain; merely deleting personal content does not resolve the account-management conflict.

**Reference links**

- [docs.cloud.google.com/architecture/identity/migrating-consumer-accounts](https://docs.cloud.google.com/architecture/identity/migrating-consumer-accounts)
- [docs.cloud.google.com/identity/docs/how-to/create-cloud-identity-user-accounts](https://docs.cloud.google.com/identity/docs/how-to/create-cloud-identity-user-accounts)
- [docs.cloud.google.com/identity/docs/concepts/overview-user-invitations](https://docs.cloud.google.com/identity/docs/concepts/overview-user-invitations)

**Related notes:** [Cloud Identity and Google Cloud Directory Sync](../02-identity-security/products/cloud-identity-and-google-cloud-directory-sync.md)

</details>

[Back to index](#index)

---

### Q11

> Northwind Commerce is moving its Terraform-based CI/CD automation to dedicated Compute Engine instances. The automation will create, modify, and remove Google Cloud resources as part of application deployments. Northwind Commerce wants the pipeline to have the necessary access while avoiding unnecessary credential exposure and following the principle of least privilege. What should the company do?  

- **A.** Attach a service account with basic permissions to the Compute Engine instances, and allow that service account to impersonate a Cloud Identity user that has elevated infrastructure administration permissions.
- **B.** Add a manual approval stage before Terraform runs, and use the approving employee’s Cloud Identity account to provision the infrastructure.
- **C.** Attach a dedicated service account to the Compute Engine instances, and grant that service account only the IAM permissions required to create, modify, and remove the resources managed by the pipeline.
- **D.** Create a separate service account for each deployment workflow, grant each account minimal IAM permissions, store their service account key files in Secret Manager, and retrieve the required key during pipeline execution.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a CI/CD workload should use a service account as its own machine identity and should receive the permissions required to perform its tasks directly. Allowing the service account to impersonate a more privileged Cloud Identity user introduces an unnecessary privilege-escalation path and makes authorization more difficult to understand and audit. Cloud Identity user accounts represent people and should not normally serve as runtime identities for automated infrastructure provisioning. The safer design is to grant the pipeline’s service account the exact resource-level permissions it needs rather than giving it indirect access to a broadly privileged human identity.

**B is incorrect** because human approval can be a useful governance control, particularly for sensitive production changes, but it does not provide an appropriate authentication design for an automated pipeline. Running infrastructure provisioning under the approving employee’s Cloud Identity account couples automation to a human identity, complicates auditing, and can cause failures when the employee changes roles, leaves the organization, loses access, or is unavailable. The approval decision and the execution identity should be separate: a human can approve a deployment, but a dedicated service account should perform the automated provisioning.

**C is correct** because a service account attached to a Compute Engine instance provides the pipeline with a managed workload identity. Applications on the instance can obtain short-lived credentials through the metadata server and Application Default Credentials, so the company does not need to create, distribute, store, or rotate service account key files. The company should grant this dedicated service account only the IAM roles and permissions that the pipeline genuinely requires to manage its defined infrastructure. This applies the principle of least privilege, keeps the automation independent of individual employees, produces audit logs under a consistent machine identity, and reduces the risk associated with long-lived credentials. Because this scenario describes a dedicated pipeline running on Compute Engine, attaching its purpose-specific service account is the most secure choice among the available options. Access to the Compute Engine instances and to the pipeline’s source configuration must also be tightly controlled because code running on an instance can use the permissions of its attached service account.

**D is incorrect** because creating purpose-specific service accounts with minimal permissions is a sound isolation practice, especially when different pipelines manage different resources. However, creating user-managed service account key files is not recommended when the workload runs on Google Cloud and can use managed, short-lived credentials instead. A service account key is a long-lived credential that can be used by anyone who obtains it. Storing the key in Secret Manager protects its storage and controls retrieval, but the key must still be downloaded or exposed to the pipeline during execution and must be monitored, rotated, and revoked. Attaching a dedicated service account to the Compute Engine instance avoids these key-management risks entirely. In a more complex environment that runs multiple pipelines on shared workers, separate pipeline service accounts and short-lived impersonation would be preferable to stored key files.

**Reference links**

- [docs.cloud.google.com/iam/docs/service-account-creds](https://docs.cloud.google.com/iam/docs/service-account-creds)
- [docs.cloud.google.com/iam/docs/best-practices-for-using-service-accounts-in-deployment-pipelines](https://docs.cloud.google.com/iam/docs/best-practices-for-using-service-accounts-in-deployment-pipelines)
- [docs.cloud.google.com/iam/docs/best-practices-for-managing-service-account-keys](https://docs.cloud.google.com/iam/docs/best-practices-for-managing-service-account-keys)

</details>

[Back to index](#index)

---

### Q12

> ShopSphere is deploying an order-processing service on Cloud Run that connects to a Cloud SQL database. The development team has implemented connection pooling and wants to measure how often the application opens a new database connection. They need to display this information on a Cloud Monitoring dashboard to confirm that existing connections are being reused. What should they do?  

- **A.** Create a custom metric in Cloud Monitoring that counts newly created Cloud Run instances, and add the metric to a dashboard.
- **B.** -Configure the application to write a log entry whenever it opens a new database connection.  
  -Create a counter-type log-based metric from those entries, and add the metric to a Cloud Monitoring dashboard.
- **C.** Open the Cloud SQL instance in the Google Cloud console and manually inspect its database logs.
- **D.** Enable Cloud Trace for the project and filter stored traces for newly opened database connections.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because the number of Cloud Run instances created does not equal the number of database connections opened by the application. A single Cloud Run instance might create one connection pool containing several database connections, recreate connections after failures, or open additional connections as traffic increases. Conversely, an instance could reuse existing pooled connections for many requests. An instance-count metric can help monitor application scaling, but it cannot directly measure the connection-creation events needed to verify that database connections are being reused.

**B is correct** because the application is the component that knows exactly when its database client or connection pool creates a new physical database connection. The application should emit a structured log entry for every new connection event. Cloud Logging can then use a filter that matches those entries to create a counter-type log-based metric. Each matching log entry increments the metric, allowing the team to chart the rate or total number of newly created connections in a Cloud Monitoring dashboard. Comparing this metric with request volume, Cloud Run instance count, or traffic patterns helps determine whether connection pooling is working effectively. When connections are reused correctly, the number of new connection events should generally remain much lower than the number of application requests.

**C is incorrect** because reviewing Cloud SQL logs manually does not provide a purpose-built, continuously charted count of connections created by this specific application. Depending on the database engine and its logging configuration, connection events might not be recorded with enough detail to identify the originating Cloud Run application, and manually inspecting logs is inefficient for ongoing monitoring. Cloud SQL metrics can show information such as active database connections, but the number of currently open connections is different from the number of new connections created by the application over time. Instrumenting the application and creating a log-based metric directly measures the required event.

**D is incorrect** because Cloud Trace is designed primarily to collect and analyze distributed request-latency data. It can show spans for application operations when the application is properly instrumented, but enabling trace storage does not automatically record every database connection creation event. Database connection establishment might occur outside an individual request trace, such as during application startup or connection-pool maintenance. Using traces to count these events would also require custom instrumentation and would be less direct than logging each event and creating a counter-type log-based metric.

**Reference links**

- [docs.cloud.google.com/logging/docs/logs-based-metrics](https://docs.cloud.google.com/logging/docs/logs-based-metrics)
- [docs.cloud.google.com/logging/docs/logs-based-metrics/counter-metrics](https://docs.cloud.google.com/logging/docs/logs-based-metrics/counter-metrics)
- [docs.cloud.google.com/sql/docs/mysql/connect-run](https://docs.cloud.google.com/sql/docs/mysql/connect-run)

**Related notes:** [Cloud Logging](../07-operations-cost/products/cloud-logging.md)

</details>

[Back to index](#index)

---

### Q13

> Crestline Foods has a Google Cloud project named Inventory Pulse with the project ID crestline-inventory-pulse. The customer-support department needs similar resources, but its access controls, quotas, billing attribution, and resource lifecycle must remain separate from the inventory department. What should the cloud administrator do?  

- **A.** Grant the customer-support team the Project Editor role on crestline-inventory-pulse.
- **B.** Add a project lien to crestline-inventory-pulse, and then grant the customer-support team the Project Editor role on that project.
- **C.** Create a separate project with the ID crestline-support-pulse, and deploy the customer-support resources in that project.
- **D.** Create another project named Support Pulse with the project ID crestline-inventory-pulse, and grant the customer-support team the Project Editor role.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because granting the customer-support team the Project Editor role on crestline-inventory-pulse would place both departments’ resources in the same Google Cloud project. A project is an important resource-management and isolation boundary for IAM policies, enabled APIs, quotas, billing attribution, monitoring, and resource lifecycle. Although IAM permissions could control some access within a shared project, this option does not organize the customer-support resources independently from the inventory resources. The Project Editor role is also a highly permissive legacy basic role that allows modification of most resources in the project, so granting it to another department could expose or allow changes to the inventory team’s resources. A separate project is the more appropriate organizational boundary.

**B is incorrect** because a project lien is intended to prevent a project from being deleted until the lien is removed. It does not divide a project into independent administrative environments, isolate departmental resources, create separate quotas, or separate billing and resource management. After the customer-support team receives the Project Editor role, both departments would still operate within crestline-inventory-pulse and could potentially affect resources belonging to each other. The lien would protect the shared project from deletion, but it would not satisfy the requirement for independent resource organization.

**C is correct** because a separate Google Cloud project provides the customer-support department with its own resource container and administrative boundary. The organization can deploy equivalent resources in crestline-support-pulse while applying separate IAM policies, service accounts, quotas, API configurations, budgets, labels, monitoring settings, and lifecycle controls. Costs can also be attributed to the new project even when both projects use the same Cloud Billing account. The project ID is different from the existing inventory project ID and can uniquely identify the customer-support project across Google Cloud. This structure keeps the departments’ resources independent while still allowing centralized governance through the same organization resource and, when appropriate, separate folders.

**D is incorrect** because a Google Cloud project ID must be globally unique. The project ID crestline-inventory-pulse is already assigned to the existing Inventory Pulse project and cannot be assigned to another project. Project names are human-readable, can be changed, and do not have to be unique, but project IDs uniquely identify projects in APIs and resource names. A project ID becomes permanent after the project is created. Therefore, the administrator can create a project named Support Pulse, but the project must use a new globally unique ID, such as crestline-support-pulse.

**Reference links**

- [docs.cloud.google.com/resource-manager/docs/creating-managing-projects](https://docs.cloud.google.com/resource-manager/docs/creating-managing-projects)
- [docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy](https://docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)
- [docs.cloud.google.com/resource-manager/docs/project-liens](https://docs.cloud.google.com/resource-manager/docs/project-liens)

</details>

[Back to index](#index)

---

### Q14

> Northstar Media processes analytics data for its streaming platform every evening. Each processing run needs many vCPUs and a large amount of memory for several hours. The workload can save checkpoints and restart if a virtual machine is interrupted. Northstar Media wants to minimize the compute cost of running these jobs. What should the company do?  

- **A.** Run the jobs on M1 machine series instances in Compute Engine.
- **B.** Package the jobs as containers and run the containers on standard Compute Engine instances.
- **C.** Run the jobs on Spot VMs in Compute Engine.
- **D.** Run the jobs on custom machine types in Compute Engine.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the M1 machine series is designed for memory-optimized workloads that require very high memory-to-vCPU ratios, such as large in-memory databases, SAP HANA, real-time analytics, and other memory-intensive applications. Although M1 instances could provide substantial CPU and memory resources, selecting this machine series does not take advantage of the workload’s ability to tolerate interruptions. The company would pay the standard price for specialized memory-optimized capacity, which would generally be less cost-effective than using discounted interruptible capacity. M1 instances can also provide more memory than the batch jobs actually require, potentially resulting in unnecessary resource costs.

**B is incorrect** because containerizing the applications can improve portability, dependency management, and deployment consistency, but it does not inherently reduce the price of the underlying Compute Engine resources. Containers running on standard Compute Engine instances are still billed according to the selected VM machine type and runtime. The company would need to select Spot VMs or another discounted consumption model separately to obtain the cost benefit associated with interruptible capacity. Containerization might be useful as part of the migration, but it does not directly address the primary requirement to minimize compute costs.

**C is correct** because Spot VMs use excess Compute Engine capacity and are available at substantial discounts compared with standard on-demand VMs. Compute Engine can preempt a Spot VM whenever it needs to reclaim the capacity, so Spot VMs are most appropriate for fault-tolerant, stateless, checkpoint-enabled, or restartable workloads. The nightly batch jobs can tolerate interruptions and run for only several hours, making them strong candidates for Spot VMs. The jobs should save intermediate results or checkpoints to durable storage, detect incomplete processing, and automatically resume or restart after an interruption. This approach allows the company to obtain the required CPU and memory while minimizing the compute expense.

**D is incorrect** because custom machine types allow the company to select a specific number of vCPUs and amount of memory instead of using a predefined machine type. This can reduce waste when predefined machine types provide an unsuitable CPU-to-memory ratio. However, a custom machine type running as a standard VM is still charged at regular Compute Engine rates and does not automatically provide the substantial discounts offered by Spot VMs. Custom machine types optimize resource sizing, whereas Spot VMs optimize cost by using interruptible excess capacity. Because the workload explicitly tolerates interruptions, Spot VMs provide the more appropriate and cost-effective solution.

**Reference links**

- [docs.cloud.google.com/compute/docs/instances/spot](https://docs.cloud.google.com/compute/docs/instances/spot)
- [docs.cloud.google.com/compute/docs/memory-optimized-machines](https://docs.cloud.google.com/compute/docs/memory-optimized-machines)
- [docs.cloud.google.com/compute/docs/instances/creating-instance-with-custom-machine-type](https://docs.cloud.google.com/compute/docs/instances/creating-instance-with-custom-machine-type)

**Related notes:** [Spot VMs](../03-compute-containers/products/spot-vms.md)

</details>

[Back to index](#index)

---

### Q15

> SouthernCross Health Analytics processes regulated healthcare data in Google Cloud. The compliance team requires all newly created location-based resources to remain within the Sydney and Melbourne Google Cloud regions. You must enforce this restriction across the organization with the least configuration and ongoing maintenance. What should you do?  

- **A.** Create a custom organization policy with the CEL condition resource.location == 'australia-southeast1' || resource.location == 'australia-southeast2'.
- **B.** Configure the gcp.resourceLocations list constraint by adding in:australia-locations to the allowed_values list.
- **C.** Configure the gcp.resourceLocations list constraint by adding in:australia-locations to the denied_values list.
- **D.** Create a custom organization policy with the CEL condition resource.location.startsWith('australia').

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because creating a custom organization policy requires defining and managing a custom constraint, identifying the applicable resource types and methods, writing and validating the CEL condition, and then attaching a policy that enforces the constraint. Custom constraints are also resource-type-specific and do not automatically provide consistent coverage for every Google Cloud service that supports location restrictions. Although explicitly comparing the two region names appears to express the intended restriction, it requires more configuration and maintenance than using the existing Google-managed gcp.resourceLocations constraint. The predefined constraint already provides standardized enforcement for supported location-based resources.

**B is correct** because gcp.resourceLocations is the Google-managed list constraint designed to control where supported Google Cloud resources can be created. Adding in:australia-locations to allowed_values establishes an allowlist for locations within Australia. The Google-managed value group includes australia-southeast1, australia-southeast2, their associated zones, and the applicable Australian location value used by services that represent locations differently. Resources in other selectable locations are prevented from being created when the policy is enforced. Using the value group requires only one policy value, avoids separate entries for each region and zone, and is maintained by Google as supported locations evolve. The restriction applies to newly created supported resources and does not relocate or remove resources that existed before the policy was applied.

**C is incorrect** because adding in:australia-locations to denied_values produces the opposite result. It prevents supported resources from being created in Australian locations while potentially permitting creation in locations outside Australia. A denied-values policy is appropriate when an organization wants to prohibit selected locations, but the requirement is to allow Australian locations and exclude all others. Therefore, in:australia-locations must be placed in allowed_values rather than denied_values.

**D is incorrect** because a custom CEL condition based on resource.location.startsWith('australia') is less reliable and requires more configuration than the predefined resource location constraint. Not every relevant Australian location value necessarily begins with the literal string australia. For example, some services can use country or multi-region identifiers such as au. The expression could therefore reject valid Australian resources or behave inconsistently across different resource types. A custom constraint must also define supported resource types and method types and may require multiple constraints to cover different services. The Google-managed in:australia-locations value group provides broader, standardized, and lower-maintenance geographic coverage.

**Reference links**

- [docs.cloud.google.com/organization-policy/restrict-locations](https://docs.cloud.google.com/organization-policy/restrict-locations)
- [docs.cloud.google.com/organization-policy/reference/restrict-locations-supported-services](https://docs.cloud.google.com/organization-policy/reference/restrict-locations-supported-services)
- [docs.cloud.google.com/organization-policy/docs/creating-managing-custom-constraints](https://docs.cloud.google.com/organization-policy/docs/creating-managing-custom-constraints)

**Related notes:** [Organization Policy Service](../02-identity-security/products/organization-policy-service.md)

</details>

[Back to index](#index)

---

### Q16

> AuroraMart publishes a BigQuery dataset containing anonymized inventory and customer-order trends. Every employee is managed through the auroramart.com Cloud Identity domain and must be able to read the dataset. You need to grant company-wide read-only access without allowing users outside the organization to view the data. What should you do?  

- **A.** Grant the roles/bigquery.dataViewer role to the domain:auroramart.com principal on the dataset’s IAM policy.
- **B.** Grant the roles/bigquery.dataViewer role to the allUsers principal on the dataset’s IAM policy.
- **C.** Grant the roles/bigquery.dataViewer role to a newly created service account on the dataset’s IAM policy.
- **D.** Grant the roles/bigquery.dataViewer role to the allAuthenticatedUsers principal on the dataset’s IAM policy.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the domain:auroramart.com principal represents users belonging to the company’s Cloud Identity domain. Granting roles/bigquery.dataViewer to this domain at the dataset level gives employees read-only access to the dataset’s tables and views without granting them permission to modify the data or administer the dataset. It also avoids maintaining individual IAM bindings: employees receive access when their organizational accounts are created and lose access when those accounts are removed or suspended. The dataset-level scope follows the principle of least privilege because the role applies only to the required dataset rather than every BigQuery dataset in the project. Users who need to run queries might separately require a role containing bigquery.jobs.create, such as roles/bigquery.jobUser, on the project where query jobs are executed, but that does not change the correct dataset access configuration.

**B is incorrect** because allUsers represents everyone on the internet, including anonymous and unauthenticated users. Granting the BigQuery Data Viewer role to allUsers would make the dataset publicly accessible wherever the resource and organization policies permit public access. This would not restrict access to employees in the Cloud Identity domain and could expose company information to external users. Even though the data is anonymized, the stated requirement is authenticated access for company employees, not public access.

**C is incorrect** because granting the role to a service account gives access only to workloads operating as or impersonating that service account. It does not automatically grant access to employees in the Cloud Identity domain. Providing all employees with access through one shared service account would also introduce unnecessary impersonation configuration, reduce user-level accountability, and complicate auditing. Human users should access the dataset through their own identities, while service accounts should generally represent applications and automated workloads.

**D is incorrect** because allAuthenticatedUsers includes any user on the internet authenticated with a Google Account, as well as service accounts and certain other authenticated identities. It is not limited to accounts managed by auroramart.com and can include personal Gmail accounts and users from unrelated organizations. Consequently, this option would grant access far beyond the company’s workforce. A domain principal precisely limits the IAM binding to users associated with the specified Cloud Identity domain.

**Reference links**

- [docs.cloud.google.com/bigquery/docs/access-control](https://docs.cloud.google.com/bigquery/docs/access-control)
- [docs.cloud.google.com/bigquery/docs/control-access-to-resources-iam](https://docs.cloud.google.com/bigquery/docs/control-access-to-resources-iam)
- [docs.cloud.google.com/iam/docs/principal-identifiers](https://docs.cloud.google.com/iam/docs/principal-identifiers)

**Related notes:** [BigQuery](../05-storage-databases-data/products/bigquery.md)

</details>

[Back to index](#index)

---

### Q17

> TrailCart runs a customer marketplace, a delivery portal, and an analytics application on Google Cloud. Each application has its own deployment schedule, and the platform team must be able to run Terraform operations for one application without affecting the others. How should TrailCart organize its Terraform repository?  

- **A.** Create one module for every resource type and store all module files in a shared directory.
- **B.** Store the Terraform configuration for each application in a separate root directory.
- **C.** Create one module for every application and store all application modules in a shared directory.
- **D.** Create separate root directories for networking, compute, storage, and other resource types.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because organizing modules only by resource type does not provide application-level isolation. Resources such as networks, service accounts, Cloud Storage buckets, and Compute Engine instances could belong to several applications but would be managed together according to their resource category. This structure couples unrelated applications and makes independent planning, deployment, state management, access control, and failure recovery more difficult. In addition, Terraform treats all .tf files in the same directory as one module, so simply placing module files together does not create independent modules or independent Terraform states.

**B is correct** because each separate root directory becomes an independent Terraform root module. TrailCart can initialize, validate, plan, and apply the configuration for each application separately. Each root directory can also use its own backend configuration, Terraform state, provider settings, variables, permissions, and deployment pipeline. A change to the delivery portal therefore does not require Terraform to refresh or evaluate every resource belonging to the marketplace or analytics application. This directory structure follows Google Cloud guidance to place the resources for independently managed applications or services in separate Terraform directories. Each application directory can still call reusable child modules for common infrastructure components.

**C is incorrect** because creating one child module per application does not automatically make the applications independently manageable. When all application modules are called by one shared root module, Terraform includes their resources in the same configuration and normally records them in the same state. Running terraform plan or terraform apply from that root directory can therefore evaluate and potentially modify resources across all applications. Application modules can be useful for reuse and abstraction, but independent lifecycle and state management require separate root configurations, typically stored in separate root directories.

**D is incorrect** because dividing root configurations by resource type separates infrastructure according to implementation details rather than application ownership and lifecycle. For example, the networking root directory could contain networks for every application, while the compute root directory could contain instances for every application. Deploying or removing one application would then require coordinated changes across several root modules and states. It would also make it harder to understand which resources collectively provide a particular application. Resources that are deployed, changed, and retired together should generally be grouped within the application or service root configuration that owns them.

**Reference links**

- [docs.cloud.google.com/docs/terraform/best-practices/root-modules](https://docs.cloud.google.com/docs/terraform/best-practices/root-modules)
- [developer.hashicorp.com/terraform/language/files](https://developer.hashicorp.com/terraform/language/files)
- [developer.hashicorp.com/terraform/language/modules](https://developer.hashicorp.com/terraform/language/modules)

**Related notes:** [Terraform](../08-iac-platform-ai/products/terraform.md)

</details>

[Back to index](#index)

---

### Q18

> BluePeak Media operates a Google Kubernetes Engine cluster named qa-hub in Google Cloud. A platform administrator has installed the Google Cloud CLI and wants future gcloud commands that require a GKE cluster name to use qa-hub by default. What should the administrator do?  

- **A.** Run gcloud config set container/cluster qa-hub.
- **B.** Run gcloud container clusters update qa-hub.
- **C.** Create a file named cluster.default in the ~/.gcloud directory and add qa-hub as its content.
- **D.** Create a file named settings.json in the ~/.gcloud directory and define qa-hub as the default cluster.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the container/cluster property in a Google Cloud CLI configuration specifies the GKE cluster name to use by default when working with Kubernetes Engine. Running gcloud config set container/cluster qa-hub writes this property to the currently active gcloud configuration. Future supported gcloud container commands can then use qa-hub when a cluster name is not supplied explicitly. Google Cloud CLI configurations are the supported mechanism for storing default properties such as the project, account, region, zone, and GKE cluster. The administrator might also need to configure the cluster’s region or zone when commands require its location. In addition, using kubectl directly requires cluster credentials and a Kubernetes context, which are normally configured by running gcloud container clusters get-credentials qa-hub with the appropriate location. However, for setting the default GKE cluster property used by gcloud commands, the command in this option is correct.

**B is incorrect** because gcloud container clusters update modifies the configuration of an existing GKE cluster. It is used for changes such as enabling or disabling supported cluster features, modifying maintenance settings, changing autoscaling-related settings, or updating other cluster attributes. Running gcloud container clusters update qa-hub does not set qa-hub as the default cluster in the active Google Cloud CLI configuration. It also normally requires the administrator to specify an actual cluster setting to update. The requirement concerns local CLI defaults rather than changing the GKE cluster itself, so gcloud config set must be used instead.

**C is incorrect** because Google Cloud CLI does not use a manually created cluster.default file in the ~/.gcloud directory to determine the default GKE cluster. Google Cloud CLI settings are managed through named configurations and properties, typically stored under the Cloud SDK configuration directory, whose standard location is $HOME/.config/gcloud on Linux and macOS unless CLOUDSDK_CONFIG overrides it. Administrators should use gcloud config commands rather than inventing configuration filenames or manually editing unsupported files. Creating this file would therefore have no supported effect on future GKE commands.

**D is incorrect** because defaults.json in the ~/.gcloud directory is not a supported Google Cloud CLI mechanism for selecting a default GKE cluster. Google Cloud CLI configurations are not established by creating an arbitrary JSON file containing resource names. The active configuration and its properties should be managed with commands such as gcloud config set, gcloud config get, and gcloud config configurations activate. Consequently, this file would not cause future gcloud commands to address qa-hub automatically.

**Reference links**

- [docs.cloud.google.com/sdk/gcloud/reference/config/set](https://docs.cloud.google.com/sdk/gcloud/reference/config/set)
- [docs.cloud.google.com/sdk/gcloud/reference/topic/configurations](https://docs.cloud.google.com/sdk/gcloud/reference/topic/configurations)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl)

</details>

[Back to index](#index)

---

### Q19

> Northwind Metrics uses Looker Studio to display sales dashboards based on a BigQuery summary table. New transaction records are appended throughout the day, and a scheduled process replaces the summary table every night with recalculated results. One morning, several Looker Studio charts stop displaying data. The analytics team wants to determine whether the nightly refresh failed. What should the team do?  

- **A.** Review Error Reporting in the Google Cloud console for processing errors.
- **B.** Use BigQuery Studio to inspect the nightly job history and review any errors.
- **C.** Use the discontinued Cloud Debugger service to investigate why the table was not refreshed.
- **D.** Create a Cloud Logging filter for the Looker Studio report.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Error Reporting is designed to aggregate and display application errors collected from supported runtime environments and logged error events. It is not the primary interface for examining the execution status, SQL details, destination table changes, and error messages of a BigQuery query or load job. Because the problem began after the nightly process overwrote the summary table, the most direct troubleshooting step is to inspect that specific BigQuery job rather than search for application exceptions in Error Reporting.

**B is correct** because the nightly table-replacement operation is performed as a BigQuery job, and BigQuery Studio provides access to job history and job details. The team can locate the job that ran during the affected period and check whether it completed successfully, failed, or produced warnings. The job details can reveal SQL errors, permission failures, invalid destination settings, schema mismatches, resource limitations, and other conditions that could prevent the summary table from being rebuilt correctly. The team can also inspect the executed query, timestamps, destination table, processing statistics, and error result. Since Looker Studio depends on the BigQuery table, validating the upstream BigQuery refresh is the most direct way to identify the cause of the broken charts.

**C is incorrect** because Cloud Debugger was intended to inspect the runtime state of application code without stopping the application. It was not a tool for reviewing BigQuery job execution or troubleshooting the results of a scheduled SQL operation. Furthermore, Cloud Debugger was deprecated on May 16, 2022, and shut down on May 31, 2023. Even when it was available, it would not have been the appropriate tool for determining whether a BigQuery job failed to overwrite a reporting table.

**D is incorrect** because Cloud Logging can contain audit and operational logs for supported Google Cloud services, but filtering for a Looker Studio report does not directly diagnose whether the nightly BigQuery table-replacement job succeeded. Looker Studio is the visualization layer, while the suspected failure is in the upstream BigQuery processing operation. A report-related log filter might help investigate access or administrative activity in some environments, but it is less direct than opening BigQuery job history and examining the exact nightly job, its status, and its error details.

**Reference links**

- [docs.cloud.google.com/bigquery/docs/managing-jobs](https://docs.cloud.google.com/bigquery/docs/managing-jobs)
- [docs.cloud.google.com/bigquery/docs/admin-jobs-explorer](https://docs.cloud.google.com/bigquery/docs/admin-jobs-explorer)
- [docs.cloud.google.com/bigquery/docs/error-messages](https://docs.cloud.google.com/bigquery/docs/error-messages)

**Related notes:** [BigQuery](../05-storage-databases-data/products/bigquery.md)

</details>

[Back to index](#index)

---

### Q20

> NimbusCart uses the Google Cloud CLI from an administrator’s laptop through an authenticated corporate proxy. The security team requires that the proxy username and password must not be stored in the gcloud CLI configuration file or written to gcloud CLI logs. How should the administrator provide the proxy credentials?  

- **A.** Run gcloud config set proxy/username and gcloud config set proxy/password to save the credentials as gcloud CLI properties.
- **B.** Generate SHA-256 hashes of the proxy username and password, store them in a certificate file, and configure the file by using the core/custom_ca_certs_file property.
- **C.** Add CLOUDSDK_PROXY_USERNAME and CLOUDSDK_PROXY_PASSWORD entries directly to the active gcloud CLI configuration file.
- **D.** Set CLOUDSDK_PROXY_USERNAME and CLOUDSDK_PROXY_PASSWORD as environment variables in the command-line environment.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because the proxy/username and proxy/password properties are valid gcloud CLI properties, but setting them with gcloud config set saves their values in the active gcloud CLI configuration. This does not satisfy the requirement to prevent the credentials from being stored in that configuration. Commands containing credentials could also be exposed through shell history or other command-recording mechanisms. This approach can configure an authenticated proxy, but it is not the recommended method when credential persistence and logging must be avoided.

**B is incorrect** because SHA-256 is a one-way cryptographic hashing algorithm, not a reversible encoding mechanism that the proxy can use to recover the original username and password. An authenticated proxy generally requires the original credential values during connection establishment. In addition, the core/custom_ca_certs_file property expects the path to a trusted certificate authority file. It is used when a proxy performs TLS inspection with a custom CA certificate; it is unrelated to storing or supplying proxy authentication credentials.

**C is incorrect** because CLOUDSDK_PROXY_USERNAME and CLOUDSDK_PROXY_PASSWORD are environment-variable names rather than properties that should be manually inserted into a gcloud CLI configuration file. Values placed in the configuration file would be stored on disk and could be exposed to users or processes that can read that file. Manually adding environment-variable names to the file also does not make them operating-system environment variables. Persistent gcloud CLI proxy credentials are instead represented by the proxy/username and proxy/password properties.

**D is correct** because every gcloud CLI property has a corresponding CLOUDSDK_SECTION_PROPERTY environment variable. The proxy/username and proxy/password properties therefore correspond to CLOUDSDK_PROXY_USERNAME and CLOUDSDK_PROXY_PASSWORD. When these variables are supplied through the process environment, the gcloud CLI can use the proxy credentials without saving them in its configuration file, and their values take precedence over configured property values. For stronger protection, the values should be obtained through a secure prompt, encrypted local file, or secure credential system rather than typed directly into a command that could be retained in shell history. The variables can also be removed from the environment after the required gcloud CLI operation finishes.

**Reference links**

- [docs.cloud.google.com/sdk/docs/proxy-settings](https://docs.cloud.google.com/sdk/docs/proxy-settings)
- [docs.cloud.google.com/sdk/docs/properties](https://docs.cloud.google.com/sdk/docs/properties)
- [docs.cloud.google.com/sdk/gcloud/reference/config/set](https://docs.cloud.google.com/sdk/gcloud/reference/config/set)

</details>

[Back to index](#index)

---

### Q21

> Northstar Finance uses an Application Design Center template to deploy a standardized employee reporting service. Eight application teams have already deployed applications from this template. The platform team has approved a new Compute Engine machine configuration and wants all new deployments to use it. Owners of existing applications must be able to adopt the approved change through the managed application lifecycle without manually modifying individual resources. What should the platform team do?  

- **A.** Delete the deployed applications and manually rebuild their resources with the new machine configuration.
- **B.** Change the configuration of every underlying Compute Engine instance directly.
- **C.** Publish a separate template with no relationship to the original template and grant application teams the Editor role.
- **D.** Revise the shared template and use the Application Design Center update and redeploy workflow.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because deleting the existing applications and rebuilding their resources manually would bypass the application lifecycle capabilities provided by Application Design Center. This approach could cause service interruption, accidental data loss, configuration inconsistencies, and substantial operational effort. It would also separate the rebuilt resources from the approved template lineage, making future governance and updates more difficult. Existing applications do not need to be destroyed merely because the source template has a new revision. Application Design Center supports applying template revisions to applications and previewing the resulting infrastructure changes before deployment.

**B is incorrect** because directly changing each Compute Engine instance modifies the deployed infrastructure without updating the shared template that defines the organization’s approved architecture. This creates configuration drift between the application’s generated Terraform configuration, the template revision, and the actual resources. Direct changes might later be overwritten or produce conflicts when the application is redeployed. This method is also difficult to apply consistently across multiple applications and does not ensure that future deployments receive the revised configuration. Platform standards should be incorporated into the reusable template rather than implemented through one-time resource modifications.

**C is incorrect** because an unrelated second template would not preserve the revision relationship between the original template and the applications created from it. Existing application owners would not receive the new configuration as an applicable revision through their current application lifecycle. They might instead need to create new applications or manually migrate to the unrelated template. Granting the broad Editor role is also unnecessary and violates the principle of least privilege because Application Design Center provides specific roles for managing application configurations and deployment lifecycles. A new unrelated template is appropriate for a genuinely different architecture, not for an approved revision to an existing standard.

**D is correct** because the platform team should modify the existing shared template, commit or publish a new template revision, and allow application owners to apply that revision through the Application Design Center update and redeploy workflow. Future applications created from the template will use the revised machine configuration. Existing application owners can identify the available template revision, review the generated Terraform changes, preview the deployment plan, and redeploy their applications using the approved update. This preserves template lineage, reduces configuration drift, maintains centralized governance, and avoids manually editing each underlying Google Cloud resource.

**Reference links**

- [docs.cloud.google.com/application-design-center/docs/quickstart-update-template](https://docs.cloud.google.com/application-design-center/docs/quickstart-update-template)
- [docs.cloud.google.com/application-design-center/docs/deploy-applications](https://docs.cloud.google.com/application-design-center/docs/deploy-applications)
- [docs.cloud.google.com/application-design-center/docs/design-application-templates](https://docs.cloud.google.com/application-design-center/docs/design-application-templates)

**Related notes:** [Application Design Center](../08-iac-platform-ai/products/application-design-center.md)

</details>

[Back to index](#index)

---

### Q22

> PulseCart is launching an updated checkout experience on Google Cloud. The operations team wants 8% of customer requests to reach the updated release while the remaining 92% continue using the proven release. The traffic percentages must remain configurable so that the team can gradually increase adoption or quickly roll back. What should the team do?  

- **A.** -Deploy PulseCart on App Engine.  
  -Deploy the updated checkout code as a new version of the existing checkout service, and configure traffic splitting between the stable and updated versions.
- **B.** -Deploy PulseCart on App Engine.  
  -Deploy the updated checkout code as a separate service, and configure traffic splitting between the original and new services.
- **C.** -Deploy PulseCart on Google Kubernetes Engine.  
  -Change the container image in the existing Deployment so that a rolling update replaces the stable application Pods.
- **D.** -Deploy PulseCart on Google Kubernetes Engine.  
  -Create a separate Deployment for the updated release, and change the Kubernetes Service selector so that it targets the new Deployment.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because App Engine supports multiple versions within the same service and provides native percentage-based traffic splitting among those versions. PulseCart can retain the stable version, deploy the checkout update as another version of the same checkout service, and assign 8% of incoming traffic to the new version while keeping 92% on the stable version. App Engine can split traffic by cookie, IP address, or random assignment, depending on the selected configuration. This approach is designed for canary releases, gradual rollouts, and A/B testing. The team can increase the new version’s allocation after validating its behavior, or immediately return all traffic to the stable version if errors occur. Because both deployments are versions of the same logical service, the application continues to use the same service endpoint while App Engine manages request distribution.

**B is incorrect** because an App Engine service represents a distinct application component or microservice, whereas a version represents a particular release of that component. App Engine’s native percentage-based traffic splitting operates between versions belonging to the same service, not between separate services. Creating another service would give the updated checkout component a separate service identity and address. Directing controlled percentages between two separate services would require additional routing or load-balancing logic and would not use App Engine version traffic splitting as described. Since the stable and updated deployments implement different releases of the same checkout component, they should be versions of one service rather than separate services.

**C is incorrect** because changing the container image in an existing Google Kubernetes Engine Deployment initiates a Kubernetes rolling update. During that process, Kubernetes gradually creates Pods containing the new image and removes Pods containing the old image according to the Deployment strategy. This overlap is temporary and is intended to move the Deployment toward a final state in which all managed Pods run the new release. It does not maintain a specified percentage, such as 8%, of real user traffic on the new version while preserving the stable version indefinitely. Rolling-update settings such as maxSurge and maxUnavailable control Pod availability and replacement speed, not weighted user-traffic distribution. A canary rollout on Google Kubernetes Engine would require additional Deployment, routing, load-balancing, Gateway, or service-mesh configuration that is not included in this option.

**D is incorrect** because changing a Kubernetes Service selector so that it targets the new Deployment generally switches the Service’s eligible backend Pods to the new release. A standard Kubernetes Service distributes requests among Pods matching its selector, but it does not provide a native configuration for assigning an exact percentage of traffic to one Deployment and the remaining percentage to another. After the selector is changed to labels belonging only to the new Deployment, the stable Deployment no longer receives normal Service traffic. A Google Kubernetes Engine canary design could use separate Services with weighted routing through an appropriate Gateway, load balancer, or service mesh, or could use carefully managed labels and replica counts for approximate distribution. The option only changes the Service to use the new Deployment, so it does not meet the controlled small-percentage rollout requirement.

**Reference links**

- [cloud.google.com/appengine/docs/standard/splitting-traffic](https://cloud.google.com/appengine/docs/standard/splitting-traffic)
- [cloud.google.com/appengine/docs/an-overview-of-app-engine](https://cloud.google.com/appengine/docs/an-overview-of-app-engine)
- [cloud.google.com/kubernetes-engine/docs/how-to/stateless-apps](https://cloud.google.com/kubernetes-engine/docs/how-to/stateless-apps)

**Related notes:** [App Engine](../03-compute-containers/products/app-engine.md)

</details>

[Back to index](#index)

---

### Q23

> LedgerPeak Insurance is migrating claim documents from its data center to Cloud Storage. The documents have the following requirements. LedgerPeak Insurance wants to use managed Google Cloud features and minimize development and operational overhead. What should the company do?  
> -Each document must be retained for six years.  
> -Up to four versions of the same claim document must be available to support corrections.  
> -Documents older than 400 days should be transitioned to a lower-cost storage class.  

- **A.** Configure a retention policy on the bucket, and use Cloud Scheduler to invoke a Cloud Run function that transitions or deletes documents according to their metadata.
- **B.** Configure a retention policy on the bucket, use lifecycle rules to transition objects to lower-cost storage classes, limit the number of versions, and delete objects after six years.
- **C.** Enable Object Versioning on the bucket, and use Cloud Scheduler to invoke a Cloud Run function that transitions or deletes documents according to their metadata.
- **D.** Enable Object Versioning on the bucket, and use Object Lifecycle Management conditions to transition objects to lower-cost storage classes, retain the required number of versions, and delete objects after six years.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a bucket retention policy can prevent objects from being deleted or replaced before a specified retention period expires, but it does not automatically preserve multiple versions of an object. Without Object Versioning, the company cannot maintain up to four generations of the same claim document for corrections. In addition, implementing Cloud Scheduler and a Cloud Run function would introduce custom code, IAM configuration, scheduling, monitoring, retry handling, and maintenance. Cloud Storage already provides Object Lifecycle Management as a fully managed mechanism for transitioning or deleting objects based on conditions such as object age, storage class, live state, and number of newer versions.

**B is incorrect** because a retention policy does not enable or manage object versions. Object Versioning must be enabled for Cloud Storage to preserve a previous object generation when a document with the same name is replaced or deleted. A six-year bucket retention policy could also prevent the replacement of a live object during its retention period, which would interfere with the requirement to upload corrected versions under the same object name. Although lifecycle rules can transition objects to a lower-cost storage class and delete objects that satisfy specified conditions, they cannot maintain revisions unless Object Versioning is enabled. Therefore, this option cannot satisfy the revision requirement as described.

**C is incorrect** because enabling Object Versioning allows Cloud Storage to retain noncurrent generations when claim documents are replaced or deleted, satisfying the requirement to preserve revisions. However, using Cloud Scheduler and a Cloud Run function to inspect metadata, transition storage classes, limit versions, and delete expired documents creates unnecessary development and operational overhead. The company would need to develop and maintain document-processing logic, handle pagination and retries, secure the function, monitor failures, and ensure that every object is processed correctly. Object Lifecycle Management provides these capabilities natively and is the Google-recommended approach when object actions can be determined through supported lifecycle conditions.

**D is correct** because Object Versioning preserves earlier generations of a claim document whenever the live generation is replaced or deleted. Object Lifecycle Management can then manage these generations automatically without custom code. An age-based lifecycle rule can use the SetStorageClass action to transition documents older than 400 days to an appropriate lower-cost storage class, such as Archive storage, based on the expected access pattern and minimum storage duration. A rule using the numNewerVersions condition can delete older noncurrent generations when the required number of newer generations exists, thereby limiting the number of retained versions. Another age-based delete rule can remove objects after the required six-year period. This combination meets the versioning, storage-tiering, and expiration requirements while minimizing operational and development costs. The lifecycle rules should be designed carefully so that no generation is deleted before it has satisfied the required retention period.

**Reference links**

- [docs.cloud.google.com/storage/docs/object-versioning](https://docs.cloud.google.com/storage/docs/object-versioning)
- [docs.cloud.google.com/storage/docs/lifecycle](https://docs.cloud.google.com/storage/docs/lifecycle)
- [docs.cloud.google.com/storage/docs/lifecycle-configurations](https://docs.cloud.google.com/storage/docs/lifecycle-configurations)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q24

> LedgerHaven operates a digital records portal that stores signed audit documents in a Cloud Storage bucket configured with Standard storage in a multi-region. The documents are rarely retrieved after 120 days but must remain stored indefinitely for compliance. You need a low-maintenance and cost-effective solution that automatically moves each document to the lowest-cost storage class appropriate for long-term archival after it reaches 120 days of age. What should you do?  

- **A.** Enable Object Versioning and create an Object Lifecycle Management rule with a daysSinceNoncurrentTime condition of 120 days that changes noncurrent versions to Archive storage.
- **B.** Create an Object Lifecycle Management rule with an age condition of 120 days and a SetStorageClass action that changes matching objects to Archive storage.
- **C.** Create a scheduled Cloud Run function that runs every night and uses the Cloud Storage API to change objects older than 120 days to Archive storage.
- **D.** Create an Object Lifecycle Management rule with a createdBefore condition set to a date 120 days in the past and a Delete action.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because daysSinceNoncurrentTime measures the amount of time that has passed since a versioned object became noncurrent, not the total time since the live object was created. This condition is intended for buckets that use Object Versioning and applies only after an object is replaced or deleted and an older generation becomes noncurrent. Documents that remain live and are never overwritten would not satisfy this condition, even after they had existed for 120 days. Enabling Object Versioning would also create and retain additional object generations, potentially increasing storage consumption and costs without helping meet the requirement to transition every live document according to its age.

**B is correct** because the age condition evaluates how many days have passed since an object was created, making it a rolling condition that applies independently to every object in the bucket. When an object reaches 120 days of age, it becomes eligible for the SetStorageClass action, which changes its storage class to Archive storage without deleting the object or requiring it to be copied to another bucket. Archive storage has the lowest at-rest storage cost among the standard Cloud Storage classes and is intended for long-term data that is accessed less than once per year. It also has a 365-day minimum storage duration and higher retrieval and operation charges, which are appropriate when documents must be retained indefinitely and are rarely accessed. Object Lifecycle Management is a managed Cloud Storage capability, so it avoids custom code, scheduled compute, API orchestration, and operational maintenance. Lifecycle actions are performed asynchronously, so objects become eligible at the configured age threshold, although the actual transition might not occur at the exact moment the threshold is reached.

**C is incorrect** because a scheduled Cloud Run function could inspect object metadata and rewrite qualifying objects into Archive storage, but it introduces unnecessary custom infrastructure. The company would need to configure scheduling, authentication, IAM permissions, pagination, retries, error handling, logging, monitoring, concurrency controls, and protection against repeatedly processing the same objects. The function and its Cloud Storage API operations could also create additional costs. Object Lifecycle Management already provides the required age-based storage-class transition as a native, scalable, and automatically managed Cloud Storage feature, making the custom function less cost-effective and less reliable.

**D is incorrect** because the Delete action permanently removes qualifying objects rather than moving them to a lower-cost storage class, directly conflicting with the requirement to retain the records indefinitely. In addition, createdBefore uses a fixed calendar date rather than a continuously evaluated object age. Setting it to a date that was 120 days ago when the rule was created would not automatically move forward each day, so newer objects would not become eligible after reaching the intended age unless the rule were repeatedly updated. An age condition provides the necessary rolling evaluation, while SetStorageClass preserves the objects and moves them to Archive storage.

**Reference links**

- [docs.cloud.google.com/storage/docs/lifecycle](https://docs.cloud.google.com/storage/docs/lifecycle)
- [docs.cloud.google.com/storage/docs/storage-classes](https://docs.cloud.google.com/storage/docs/storage-classes)
- [docs.cloud.google.com/storage/docs/object-versioning](https://docs.cloud.google.com/storage/docs/object-versioning)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q25

> ParcelPilot, a delivery-tracking application, has completed testing of an AI agent that helps customers locate delayed shipments and update delivery preferences. The platform team must deploy the agent to a managed production environment that automatically handles infrastructure provisioning and scaling. The company also wants the agent to remain within Gemini Enterprise Agent Platform. Which deployment target should the team use?  

- **A.** Cloud DNS
- **B.** Cloud Scheduler
- **C.** Cloud Asset Inventory
- **D.** Agent Runtime

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Cloud DNS is a managed Domain Name System service used to publish and manage DNS zones and records. It translates domain names into IP addresses and supports functions such as public DNS hosting, private DNS zones, forwarding, and traffic routing. It does not provide an execution environment for AI agents, accept agent packages for deployment, manage agent processes, or automatically scale agent workloads. Cloud DNS might help route users to an application endpoint, but it cannot host the application or agent behind that endpoint.

**B is incorrect** because Cloud Scheduler is a managed cron service designed to invoke supported targets according to a schedule. It can trigger HTTP endpoints, publish messages to Pub/Sub, or initiate scheduled operational tasks. Although it could periodically call an already deployed agent, it does not host the agent itself. It provides scheduling rather than a persistent production runtime, and it does not manage the agent’s serving infrastructure, deployment lifecycle, request processing, or automatic scaling.

**C is incorrect** because Cloud Asset Inventory is a governance and visibility service that records metadata about Google Cloud resources. It can search resources, maintain asset history, export asset information, and help organizations analyze configuration and policy changes. It cannot execute an agent package or expose the agent as a production service. Its purpose is inventory, auditing, analysis, and resource discovery rather than application hosting or agent deployment.

**D is correct** because Agent Runtime is the managed environment within Gemini Enterprise Agent Platform that is specifically designed to deploy, operate, manage, and scale AI agents in production. It handles the underlying serving infrastructure so the operations team does not need to build and maintain custom compute, container orchestration, request handling, or scaling mechanisms. Deploying the tested package to Agent Runtime makes the agent remotely available for requests while keeping its deployment and lifecycle management within Gemini Enterprise Agent Platform. It is therefore the most appropriate target when the organization wants a production-ready agent runtime with minimal infrastructure administration.

**Reference links**

- [docs.cloud.google.com/gemini-enterprise-agent-platform/build/runtime](https://docs.cloud.google.com/gemini-enterprise-agent-platform/build/runtime)
- [docs.cloud.google.com/gemini-enterprise-agent-platform/scale/runtime/deploy-an-agent](https://docs.cloud.google.com/gemini-enterprise-agent-platform/scale/runtime/deploy-an-agent)
- [docs.cloud.google.com/gemini-enterprise-agent-platform/scale/runtime/manage-deployed-agents](https://docs.cloud.google.com/gemini-enterprise-agent-platform/scale/runtime/manage-deployed-agents)

**Related notes:** [Gemini Enterprise Agent Platform: Agent Runtime](../08-iac-platform-ai/products/agent-runtime.md)

</details>

[Back to index](#index)

---

### Q26

> HarborPulse, a maritime logistics company, stores vessel telemetry files in Cloud Storage. A business-critical analytics pipeline reads these files continuously, and the primary users are located in Philadelphia, Pennsylvania. The company wants to minimize storage costs while maintaining appropriate availability and performance. How should the Cloud Storage bucket be configured?  

- **A.** Select the region closest to the users and use the Nearline storage class.
- **B.** Select the region closest to the users and use the Standard storage class.
- **C.** Select the dual-region closest to the users and use the Nearline storage class.
- **D.** Select the dual-region closest to the users and use the Standard storage class.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Nearline storage is intended for infrequently accessed data, generally data that is read no more than approximately once per month. Nearline has lower storage charges than Standard storage, but it includes data retrieval charges and a 30-day minimum storage duration. Because the analytics pipeline continually reads the files, retrieval charges could make Nearline more expensive overall. In addition, a regional bucket stores data within one geographic region and does not provide the cross-region redundancy most appropriate for a mission-critical workload.

**B is incorrect** because Standard storage is the appropriate class for files that are accessed continuously, and selecting a region close to the users can reduce latency and network costs. However, a regional bucket stores the data within a single geographic region. Cloud Storage provides redundancy across availability zones within that region, but a severe regional disruption could affect access to the data. Because the analytics pipeline is mission-critical, a dual-region location provides more suitable geographic redundancy and availability.

**C is incorrect** because a dual-region bucket provides geographic redundancy by storing data across two regions, making the location choice appropriate for a mission-critical analytics pipeline. However, Nearline storage is unsuitable for data that is continually accessed. Nearline retrieval charges apply whenever the files are read, and the class has a 30-day minimum storage duration. Its lower at-rest storage price is designed for infrequently accessed data, such as backups, rather than actively used analytics data.

**D is correct** because Standard storage is designed for frequently accessed or “hot” data and does not impose minimum storage-duration or data-retrieval charges. This makes it the most appropriate storage class for files that a continuous analytics pipeline reads regularly. A dual-region bucket stores the data redundantly in two selected geographic regions, providing stronger availability and disaster resilience than a single-region bucket. Selecting the dual-region closest to the users also helps limit latency and network costs. Although dual-region Standard storage can have a higher at-rest price than regional or Nearline storage, it minimizes the overall cost while satisfying both the continuous-access and mission-critical availability requirements.

**Reference links**

- [cloud.google.com/storage/docs/storage-classes](https://cloud.google.com/storage/docs/storage-classes)
- [cloud.google.com/storage/docs/locations](https://cloud.google.com/storage/docs/locations)
- [cloud.google.com/storage/docs/availability-durability](https://cloud.google.com/storage/docs/availability-durability)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q27

> PixelNest Media stores completed image-processing files in a Cloud Storage bucket by using Standard storage. Its production application reads only files uploaded during the most recent 45 days. Older files must be retained for possible audits, but they are not expected to be accessed regularly. PixelNest Media wants to reduce storage costs automatically with minimal administration. What should the company do?  

- **A.** Configure Object Lifecycle Management on the bucket to change objects older than 45 days to Archive storage.
- **B.** Create a daily Cloud Scheduler job that invokes a Cloud Run function to delete objects older than 45 days.
- **C.** Configure a 45-day bucket retention policy and permanently lock the retention policy.
- **D.** Enable Object Versioning on the bucket and configure a lifecycle rule to delete noncurrent object versions after 45 days.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Cloud Storage Object Lifecycle Management is the native, fully managed mechanism for automatically taking an action when objects meet specified conditions. An age-based lifecycle rule can use the SetStorageClass action to move objects from Standard storage to Archive storage after they become older than 45 days. This reduces ongoing storage charges while preserving the files for possible future audits, and it does not require custom code, scheduled compute resources, or manual processing. Archive storage is designed for data that is retained for long periods and accessed very infrequently. The company should also consider Archive storage’s data retrieval charges and 365-day minimum storage duration because deleting or replacing an archived object before the minimum duration ends can result in early deletion charges.

**B is incorrect** because deleting the files would violate the requirement to retain older files for possible audits. It also introduces unnecessary components and operational complexity by requiring Cloud Scheduler, a Cloud Run function, custom deletion logic, permissions, error handling, monitoring, and retries. Although this architecture could delete old objects, Cloud Storage already provides Object Lifecycle Management for age-based transitions or deletions. A native lifecycle rule is simpler, less error-prone, and better aligned with the requirement to preserve the files while lowering their storage cost.

**C is incorrect** because a bucket retention policy controls when objects are allowed to be deleted or replaced; it does not move objects to a less expensive storage class. A 45-day retention policy would prevent objects from being deleted or replaced during their first 45 days, but objects would remain in Standard storage unless another process changed their storage class. Permanently locking the policy is intended for strict regulatory or compliance requirements and makes the retention configuration irreversible. It would not achieve the primary goal of automatically reducing the cost of older objects.

**D is incorrect** because Object Versioning preserves noncurrent versions when live objects are overwritten or deleted. It is intended to support recovery from accidental deletion or replacement, not to optimize the storage class of aging live objects. Enabling versioning can increase storage consumption because both live and noncurrent object versions are billed. A lifecycle rule that deletes noncurrent versions after 45 days would manage only previous versions; it would not transition the current older files from Standard storage to Archive storage. Therefore, it does not satisfy the cost-optimization requirement for the application’s existing live objects.

**Reference links**

- [docs.cloud.google.com/storage/docs/lifecycle](https://docs.cloud.google.com/storage/docs/lifecycle)
- [docs.cloud.google.com/storage/docs/storage-classes](https://docs.cloud.google.com/storage/docs/storage-classes)
- [docs.cloud.google.com/storage/docs/object-versioning](https://docs.cloud.google.com/storage/docs/object-versioning)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q28

> Northstar Retail deployed a new version of its inventory API to Google Kubernetes Engine (GKE) by using a rolling update. The new version is producing errors, and the platform team must restore the Deployment to its previous working revision. What should the team do?  

- **A.** Delete the Deployment and recreate it later.
- **B.** Run the kubectl rollout restart command for the Deployment.
- **C.** Run the kubectl rollout undo command for the Deployment.
- **D.** Manually reduce the number of new Pods and increase the number of old Pods.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because deleting the Deployment removes the Kubernetes controller and its declared desired state. By default, the Pods and ReplicaSets managed by the Deployment can also be removed through cascading deletion. Deleting and manually recreating the Deployment is unnecessary, introduces avoidable downtime and configuration risk, and does not use the Deployment’s stored revision history. Kubernetes provides a dedicated rollback operation, so the Deployment should remain in place.

**B is incorrect** because kubectl rollout restart starts a new rollout by restarting the Pods associated with the current Deployment specification. It does not restore the previous container image, configuration, or Deployment revision. Therefore, if the current Deployment specification contains the faulty application version, restarting the rollout creates replacement Pods that use the same faulty version rather than reverting to the last working version.

**C is correct** because kubectl rollout undo is specifically designed to roll back a Kubernetes Deployment to a previous revision. Running kubectl rollout undo deployment/inventory-api restores the Deployment’s preceding configuration and causes Kubernetes to perform another controlled rollout that replaces the faulty Pods with Pods based on the earlier ReplicaSet. The team can inspect available revisions by using kubectl rollout history deployment/inventory-api and can restore a specific revision by adding the --to-revision option. This approach uses Kubernetes-native Deployment history and preserves the benefits of a controlled rolling replacement.

**D is incorrect** because Deployment Pods and ReplicaSets are managed by the Deployment controller. Manually scaling the new and old ReplicaSets bypasses the normal declarative rollout process and can create inconsistencies between the Deployment’s desired state and the manually adjusted replica counts. The Deployment controller might also overwrite the manual changes during reconciliation. Using kubectl rollout undo is safer, repeatable, and less error-prone because Kubernetes automatically updates the Deployment specification and coordinates the rollback.

**Reference links**

- [kubernetes.io/docs/reference/kubectl/generated/kubectl_rollout/kubectl_rollout_undo](https://kubernetes.io/docs/reference/kubectl/generated/kubectl_rollout/kubectl_rollout_undo)
- [kubernetes.io/docs/concepts/workloads/controllers/deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment)
- [kubernetes.io/docs/tutorials/kubernetes-basics/update/update-intro](https://kubernetes.io/docs/tutorials/kubernetes-basics/update/update-intro)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q29

> StreamNest has completed a new release of its video-transcoding API and stored the production container image in Artifact Registry. The service receives intermittent requests, must have no running instances while idle, and must be released with minimal infrastructure configuration. What should the platform team do?  

- **A.** Create a Compute Engine instance template that runs the container, deploy a managed instance group, and expose it through an external Application Load Balancer.
- **B.** Create an app.yaml file for the containerized service and deploy the application to the App Engine flexible environment.
- **C.** Create Kubernetes Deployment and Service manifests for the container and apply them to a Google Kubernetes Engine cluster.
- **D.** Deploy the container image from Artifact Registry directly to a Cloud Run service.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a Compute Engine managed instance group and an external Application Load Balancer introduce several infrastructure components that must be configured and managed, including an instance template, health checks, a backend service, forwarding rules, firewall rules, and instance group settings. The option also does not configure autoscaling or set the managed instance group’s minimum size to zero, so creating the group does not inherently satisfy the scale-to-zero requirement. Even with additional autoscaling configuration, this architecture would be more complex and slower to implement than a serverless container platform designed to deploy container images directly.

**B is incorrect** because the App Engine flexible environment runs application containers on Compute Engine virtual machines and does not support scaling a service to zero instances. Its automatic scaling configuration requires min_num_instances to be at least 1, and the default minimum is higher than zero. Therefore, at least one instance normally remains allocated even when the application receives no traffic. App Engine flexible could run a containerized application, but it does not meet the explicit design requirement that the application must be able to scale to zero.

**C is incorrect** because a Kubernetes Deployment and Service only define how to run and expose the container inside GKE. They do not, by themselves, configure automatic scaling to zero. A standard Deployment normally maintains the number of replicas specified in its manifest, and Kubernetes Horizontal Pod Autoscaling generally requires additional configuration and does not automatically provide request-driven scale-from-zero behavior through these two manifests alone. Achieving scale to zero on GKE can require additional mechanisms such as KEDA, workload autoscaling configuration, and suitable cluster or node autoscaling. GKE would therefore add unnecessary cluster and Kubernetes management when the goal is to deploy the image as quickly as possible.

**D is correct** because Cloud Run is a fully managed serverless container platform that can deploy a container image directly from Artifact Registry. Cloud Run automatically creates revisions, provides an HTTPS endpoint, routes requests, performs health management, and scales the number of container instances according to incoming traffic. When the minimum instance setting is zero, which is the default for normal request-based Cloud Run services, Cloud Run can remove idle instances and scale the service to zero. When a new request arrives, Cloud Run starts an instance to process it. This approach meets both requirements: it supports scale to zero and provides the fastest production deployment path with minimal infrastructure administration.

**Reference links**

- [cloud.google.com/run/docs/deploying](https://cloud.google.com/run/docs/deploying)
- [cloud.google.com/run/docs/configuring/min-instances](https://cloud.google.com/run/docs/configuring/min-instances)
- [cloud.google.com/appengine/docs/flexible/reference/app-yaml](https://cloud.google.com/appengine/docs/flexible/reference/app-yaml)

**Related notes:** [Artifact Registry](../03-compute-containers/products/artifact-registry.md)

</details>

[Back to index](#index)

---

### Q30

> TrailPulse operates a fitness-tracking application on a Compute Engine VM instance. The application must write new audit records to a Cloud Storage bucket named trailpulse-audit-asia-south1. It must not read, overwrite, modify, or delete existing objects, and it must not access any other bucket in the Google Cloud project. You need to implement the principle of least privilege. What should you do?  

- **A.** -Create a dedicated service account for the TrailPulse application.  
  -Grant it the predefined roles/storage.objectCreator IAM role only on the trailpulse-audit-asia-south1 bucket, and attach the service account to the Compute Engine VM instance.
- **B.** Grant the Compute Engine default service account the predefined roles/storage.objectAdmin IAM role at the Google Cloud project level.
- **C.** -Create a dedicated service account for the TrailPulse application.  
  -Generate a service account key, grant the account the predefined roles/storage.admin IAM role on the trailpulse-audit-asia-south1 bucket, and store the key file on the VM instance.
- **D.** Grant the Compute Engine default service account the predefined roles/storage.objectCreator IAM role at the Google Cloud project level, and attach the service account to the VM instance.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because the predefined Storage Object Creator role, roles/storage.objectCreator, is designed for workloads that only need to create new objects. It permits the application to upload new audit records but does not permit it to view, delete, or overwrite existing objects. Granting the role directly on trailpulse-audit-asia-south1 limits the authorization boundary to that specific bucket, so the service account does not receive equivalent access to other buckets in the project. Creating a dedicated user-managed service account also isolates the application’s identity from other workloads. Attaching that service account to the Compute Engine VM allows the application to obtain short-lived credentials through the VM metadata service and Application Default Credentials, avoiding the need to create or store a service account key. This combination provides the required operation, limits the accessible resource, and follows the principle of least privilege.

**B is incorrect** because roles/storage.objectAdmin provides substantially more permissions than the application requires. A principal with this role can create, view, update, and delete Cloud Storage objects. Granting it at the Google Cloud project level would also make those permissions applicable to objects in every bucket within the project, subject to applicable IAM conditions and policies. The application only needs to create objects in one bucket, so both the selected role and the resource level are excessively broad. Using the Compute Engine default service account can also make permission management less isolated because that account might be used by other VM instances or workloads.

**C is incorrect** because roles/storage.admin provides broad administrative control over buckets and objects, including permissions that are unnecessary for a write-only logging workload. Even when the role is granted on only one bucket, it would allow the application to perform actions beyond creating new log objects, such as reading or deleting objects and changing aspects of the bucket’s configuration. Generating and storing a service account key on the VM is also unnecessary and introduces a long-lived credential that could be copied or exposed. A service account attached directly to the VM can provide automatically managed, short-lived credentials without requiring a key file.

**D is incorrect** because roles/storage.objectCreator is the appropriate create-only role, but granting it at the Google Cloud project level gives the service account permission to create objects in all applicable Cloud Storage buckets in that project. This violates the requirement that the application must access only trailpulse-audit-asia-south1. It also uses the Compute Engine default service account instead of creating a dedicated identity for the application. The role should be granted to a dedicated service account at the individual bucket level to restrict both the permitted actions and the accessible resource.

**Reference links**

- [docs.cloud.google.com/storage/docs/access-control/iam-roles](https://docs.cloud.google.com/storage/docs/access-control/iam-roles)
- [docs.cloud.google.com/compute/docs/access/service-accounts](https://docs.cloud.google.com/compute/docs/access/service-accounts)
- [docs.cloud.google.com/iam/docs/best-practices-service-accounts](https://docs.cloud.google.com/iam/docs/best-practices-service-accounts)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q31

> OrbitFleet is migrating its containerized logistics applications to Kubernetes clusters running on Google Cloud and two additional cloud providers. The platform team needs a single Infrastructure as Code solution to provision and manage Kubernetes clusters, networks, storage, and other cloud resources across all three providers. What should the team do?  

- **A.** Use Config Connector and Kubernetes custom resources to provision infrastructure for all three cloud providers.
- **B.** Use Terraform with the appropriate provider plugins to provision infrastructure for all three cloud providers.
- **C.** Develop Python programs that call each cloud provider’s SDK to create and manage the infrastructure.
- **D.** Use standard Kubernetes YAML manifests to provision all Kubernetes and cloud infrastructure resources.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Config Connector is designed to manage Google Cloud resources through Kubernetes APIs and Kubernetes custom resources. It provides a declarative Kubernetes-style method for provisioning resources such as Google Cloud networks, databases, storage buckets, and service accounts. However, Config Connector is specifically focused on Google Cloud resources and does not provide a unified, provider-neutral solution for provisioning infrastructure across Google Cloud and two other cloud providers. The organization would still need separate tools or custom integrations for resources hosted by the other providers. Therefore, Config Connector does not satisfy the requirement for one Infrastructure as Code solution that supports the complete multi-cloud environment.

**B is correct** because Terraform is a declarative Infrastructure as Code tool that supports Google Cloud and many other cloud platforms through provider plugins. The platform team can define Kubernetes clusters, networking, storage, identity resources, and other provider-specific infrastructure in reusable Terraform configurations while using a consistent provisioning workflow across all three cloud providers. Terraform maintains state to compare the declared configuration with deployed infrastructure, calculates an execution plan before making changes, and manages resource dependencies. The configurations can be stored in version control, reviewed through pull requests, reused as modules, and applied consistently to development, testing, and production environments. Because the organization requires a multi-cloud Infrastructure as Code solution rather than a Google Cloud-only tool, Terraform is the most appropriate option.

**C is incorrect** because Python and the individual cloud SDKs could technically provision resources across multiple providers, but this approach would require the company to design and maintain a custom imperative provisioning system. Developers would need to implement authentication, retries, error handling, dependency ordering, idempotency, resource updates, deletion behavior, state tracking, and rollback logic separately for each provider. Cloud SDK interfaces can also differ significantly, increasing the amount of provider-specific code and maintenance. Terraform already provides these Infrastructure as Code capabilities through a consistent declarative model and provider ecosystem. Building a custom Python solution would therefore introduce unnecessary development effort, operational complexity, and long-term maintenance costs.

**D is incorrect** because standard Kubernetes YAML manifests define Kubernetes API resources such as Deployments, Services, ConfigMaps, and StatefulSets. They do not independently provision the complete set of external cloud infrastructure resources, such as virtual networks, subnets, managed databases, cloud storage, IAM configurations, and provider-managed Kubernetes clusters. Custom Kubernetes operators could extend the Kubernetes API to manage external infrastructure, but separate operators or controllers would be required for each cloud provider, and standard YAML manifests alone would not provide this functionality. Terraform provides a more comprehensive and consistent Infrastructure as Code solution for managing both Kubernetes-related resources and the underlying infrastructure across multiple cloud providers.

**Reference links**

- [docs.cloud.google.com/docs/terraform/terraform-overview](https://docs.cloud.google.com/docs/terraform/terraform-overview)
- [developer.hashicorp.com/terraform/intro](https://developer.hashicorp.com/terraform/intro)
- [docs.cloud.google.com/config-connector/docs/overview](https://docs.cloud.google.com/config-connector/docs/overview)

**Related notes:** [Terraform](../08-iac-platform-ai/products/terraform.md)

</details>

[Back to index](#index)

---

### Q32

> NimbusCart is moving its retail applications from an on-premises environment to Google Cloud. The finance team is configuring Cloud Billing and needs resource-level usage and cost information available in BigQuery for detailed analysis. NimbusCart wants to capture the most comprehensive billing history possible from the beginning of its cloud adoption. What should the company do?  

- **A.** Enable Cloud Billing data export to BigQuery when creating the Cloud Billing account.
- **B.** Enable billing for each project, link the projects to a Cloud Billing account, and expect a billing table to appear automatically in BigQuery.
- **C.** Create a Cloud Billing account and enable the BigQuery Data Transfer Service API to export pricing information.
- **D.** Enable the BigQuery API, grant the BigQuery User IAM role, and configure a location for the BigQuery dataset.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Cloud Billing data export to BigQuery is the Google Cloud capability specifically designed to automatically send usage, cost, credit, adjustment, pricing, and related billing information to BigQuery tables. For granular analysis, the company can enable the Detailed usage cost export, which includes the standard billing fields and resource-level information for supported services, such as the individual virtual machine or persistent disk that generated a charge. Google recommends enabling the export when the Cloud Billing account is created so that the company collects the most comprehensive billing history possible. The company must also prepare a billing-enabled project and an eligible BigQuery dataset, and then configure the desired export type from the Cloud Billing account. After the export is enabled, Cloud Billing automatically creates and updates the relevant tables in the selected dataset.

**B is incorrect** because enabling billing on a project and linking it to a Cloud Billing account only allows the project to consume billable Google Cloud services and assigns its charges to that billing account. These actions do not automatically configure Cloud Billing data export or create Cloud Billing tables in BigQuery. A BigQuery billing data table appears only after an authorized administrator creates or selects an appropriate dataset and explicitly enables a Cloud Billing export, such as the Standard usage cost or Detailed usage cost export, for the billing account.

**C is incorrect** because enabling the BigQuery Data Transfer Service API is only a prerequisite for exporting Cloud Billing pricing data. It does not independently configure the pricing export, and pricing data alone does not provide the granular breakdown of actual resource usage and costs requested by the finance team. Pricing export contains information about services, SKUs, geographic metadata, pricing units, tiers, and account-specific prices. To analyze actual expenditure at a granular level, the company must enable usage cost data export, preferably the Detailed usage cost export. The BigQuery Data Transfer Service API can be enabled additionally when pricing data is also required.

**D is incorrect** because enabling the BigQuery API, assigning an IAM role, and selecting a dataset location only prepare some of the underlying BigQuery environment. These steps do not instruct Cloud Billing to export any billing information. The BigQuery User role can permit activities such as creating datasets and running jobs, but it does not replace the Cloud Billing permissions required to configure an export. The company must explicitly enable Cloud Billing data export from the relevant Cloud Billing account and select the destination project and dataset. The dataset must also use a location supported by Cloud Billing export.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery)
- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-setup](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-setup)
- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-tables/detailed-usage](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-tables/detailed-usage)

**Related notes:** [Cloud Billing](../07-operations-cost/products/cloud-billing.md)

</details>

[Back to index](#index)

---

### Q33

> BrightCart is launching an online storefront on a Compute Engine VM. The company has created a monthly Cloud Billing budget and configured an email alert when spending reaches 85% of the budget. To control costs, the team wants the VM to be stopped automatically when actual spending reaches the full budget amount. What should the team do?  

- **A.** Create a separate Cloud Billing account and move the BrightCart project to it so that additional charges do not count toward the existing budget.
- **B.** -Create a Pub/Sub topic and configure the budget to publish programmatic notifications to it.  
  -Deploy a Cloud Run function triggered by the topic, and have the function stop the Compute Engine VM when spending reaches 100% of the budget.
- **C.** Review forecasted costs in the Cloud Billing dashboard and continually increase the budget and notification threshold to match the forecast.
- **D.** Configure the Cloud Billing budget to automatically stop all billable resources when actual spending reaches 100%.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because moving the project to another Cloud Billing account does not prevent the project from generating charges. It only changes the Cloud Billing account responsible for paying for those charges. A budget monitors costs associated with its configured billing scope, but creating another billing account does not impose a spending limit or stop the Compute Engine VM. This approach would also complicate billing administration without providing the required automated cost-control action.

**B is correct** because Cloud Billing budgets can publish programmatic budget notifications to a Pub/Sub topic when configured spending thresholds are reached. A Pub/Sub-triggered Cloud Run function can process these notifications, inspect the reported budget amount and cost information, and call the Compute Engine API to stop the VM when spending reaches or exceeds 100% of the budget. The function’s service account should receive only the permissions required to stop the target instance, following the principle of least privilege. The function should also be designed to handle repeated Pub/Sub deliveries safely because messages can be delivered more than once. This solution creates an automated response to a budget threshold rather than relying only on email alerts. However, budget notifications are not instantaneous, billing data can be delayed, and stopping a VM does not eliminate every possible project charge. Persistent disks, snapshots, reserved resources, static external IP addresses, and other services can continue generating costs, so this mechanism reduces spending but does not guarantee an exact hard spending cap.

**C is incorrect** because reviewing forecasted spending and modifying the budget is a monitoring and planning activity, not an automated enforcement mechanism. Increasing the budget to match forecasted costs would merely move the threshold and permit additional spending. It would not stop the VM or prevent resources from continuing to incur charges after the original spending target is reached.

**D is incorrect** because Cloud Billing budgets and email alerts do not automatically stop resources, disable APIs, or disable billing when a threshold is crossed. A budget is primarily a monitoring and notification mechanism rather than a hard spending cap. To perform an automated action, the budget must send a programmatic notification through Pub/Sub, and a separate workload such as a Cloud Run function must process that notification and execute the required operation.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/budgets](https://docs.cloud.google.com/billing/docs/how-to/budgets)
- [docs.cloud.google.com/billing/docs/how-to/budgets-programmatic-notifications](https://docs.cloud.google.com/billing/docs/how-to/budgets-programmatic-notifications)
- [docs.cloud.google.com/billing/docs/how-to/control-usage](https://docs.cloud.google.com/billing/docs/how-to/control-usage)

**Related notes:** [Pub/Sub](../04-events-integration/products/pub-sub.md) · [Cloud Billing](../07-operations-cost/products/cloud-billing.md)

</details>

[Back to index](#index)

---

### Q34

> BrightCart runs an order-processing API on a regional Compute Engine managed instance group. The reliability team must receive a notification when the mean CPU utilization across the entire group remains above 68% for seven consecutive minutes. The solution should use managed Google Cloud services and require minimal operational maintenance. What should you do?  

- **A.** Create a logs-based metric in Cloud Logging that identifies messages associated with high processor usage, and configure a Cloud Monitoring alerting policy for that metric.
- **B.** Install the Ops Agent on every VM, deploy a separate Compute Engine VM that queries the collected CPU data every seven minutes, and have the VM send an email when utilization exceeds 68%.
- **C.** -Create a metric-threshold alerting policy in Cloud Monitoring for compute.googleapis.com/instance/cpu/utilization.  
  -Filter the monitored resources to the managed instance group, calculate the mean across its VM time series, set the threshold to 68% with a seven-minute retest window, and attach a notification channel.
- **D.** Configure the managed instance group autoscaler with a target CPU utilization of 68%, set a seven-minute initialization period, and configure the autoscaler to send notifications when the target is exceeded.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Compute Engine CPU utilization is already available as a native Cloud Monitoring metric. Logs-based metrics are designed to derive numeric measurements from matching Cloud Logging entries, but CPU utilization is not normally represented by periodic high-CPU log entries. Creating a logs-based metric would therefore be unnecessary and could produce incomplete or misleading results unless the application explicitly generated suitable log entries. The direct infrastructure metric provides structured time-series data and supports filtering, aggregation, threshold evaluation, retest windows, incident creation, and notification channels without converting logs into metrics.

**B is incorrect** because the built-in Compute Engine CPU utilization metric does not require the Ops Agent. The Ops Agent is useful when guest-level metrics, application metrics, or logs unavailable through standard platform telemetry must be collected. A custom polling VM would add unnecessary infrastructure, code, scheduling, credential management, failure handling, and email-delivery maintenance. Polling only once every seven minutes could also delay detection and would not reliably prove that the threshold remained continuously breached throughout the required interval. Cloud Monitoring evaluates incoming time-series data continuously and provides a scalable managed alerting system.

**C is correct** because compute.googleapis.com/instance/cpu/utilization is the standard Cloud Monitoring metric for the fraction of allocated CPU being used by a Compute Engine VM. The policy can be scoped to the VMs belonging to the relevant managed instance group and configured with cross-series aggregation using the mean reducer, producing the average utilization across the group instead of evaluating each VM independently. A threshold of 0.68 represents 68% utilization, and a seven-minute retest window requires the condition to remain true for seven consecutive minutes before an incident is opened. Attaching an email, SMS, Pub/Sub, webhook, or another supported notification channel delivers the required notification without custom monitoring infrastructure.

**D is incorrect** because an autoscaling policy controls the number of VM instances in a managed instance group; it is not a substitute for a Cloud Monitoring alerting policy. A target CPU utilization tells the autoscaler what average utilization it should attempt to maintain by adding or removing instances. It does not define a monitoring incident that opens only after the metric has remained above the target for a specified retest window. The initialization period also controls how long newly created instances are treated as initializing for autoscaling calculations; it does not represent a threshold-duration requirement. Additionally, autoscaler configuration does not provide Cloud Monitoring notification channels for sending threshold-breach alerts.

**Reference links**

- [cloud.google.com/monitoring/alerts/using-alerting-ui](https://cloud.google.com/monitoring/alerts/using-alerting-ui)
- [cloud.google.com/monitoring/api/metrics_gcp_c](https://cloud.google.com/monitoring/api/metrics_gcp_c)
- [cloud.google.com/compute/docs/autoscaler/scaling-cpu](https://cloud.google.com/compute/docs/autoscaler/scaling-cpu)

**Related notes:** [Cloud Monitoring](../07-operations-cost/products/cloud-monitoring.md)

</details>

[Back to index](#index)

---

### Q35

> Northstar Retail operates a production order-processing database on Spanner in a regional instance configuration. During peak demand, query latency increases as high-priority CPU utilization rises. The operations team wants to improve performance as quickly as possible while following Google-recommended utilization limits. What should the team do?  

- **A.** -Create a Cloud Monitoring alert for when high-priority CPU utilization reaches 45%.  
  -When the threshold is exceeded, increase the instance’s compute capacity by adding nodes.
- **B.** -Create a Cloud Monitoring alert for when high-priority CPU utilization reaches 45%.  
  -When the threshold is exceeded, use query statistics to locate CPU-intensive queries and rewrite them.
- **C.** -Create a Cloud Monitoring alert for when high-priority CPU utilization reaches 65%.  
  -When the threshold is exceeded, increase the instance’s compute capacity by adding nodes.
- **D.** -Create a Cloud Monitoring alert for when high-priority CPU utilization reaches 65%.  
  -When the threshold is exceeded, use query statistics to locate CPU-intensive queries and rewrite them.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because 45% is the recommended high-priority CPU utilization limit for dual-region and multi-region Spanner instance configurations, not regional configurations. A regional instance is generally provisioned to keep high-priority CPU utilization below 65%. Adding nodes would quickly provide more CPU resources, but triggering that action at 45% would apply the wrong recommended threshold to this regional instance. It could also cause unnecessary overprovisioning and additional cost when the instance still has capacity within the recommended regional operating range.

**B is incorrect** because it uses the 45% threshold that applies to dual-region and multi-region configurations rather than the 65% recommendation for a regional Spanner instance. Query statistics can help identify expensive queries, lock contention, inefficient execution plans, or queries that scan excessive amounts of data. Rewriting those queries can produce valuable long-term improvements, but investigation, testing, deployment, and validation normally take more time than increasing compute capacity. Therefore, this option uses the wrong threshold and does not provide the fastest method of improving production performance.

**C is correct** because Google recommends provisioning enough compute capacity to keep high-priority CPU utilization below 65% for a regional Spanner instance. Cloud Monitoring can notify the operations team when utilization reaches or exceeds that recommended limit. Adding nodes increases the instance’s compute capacity, giving Spanner more CPU resources for query processing and other database work. This is generally the quickest response to CPU-related performance pressure because compute capacity can be increased without first analyzing, rewriting, testing, and redeploying application queries. Query optimization should still be considered for long-term efficiency, but scaling the instance is the most direct way to improve performance in the shortest amount of time.

**D is incorrect** because it uses the appropriate 65% threshold for a regional Spanner instance, but its proposed response does not satisfy the requirement to improve performance as quickly as possible. Query statistics are useful for finding statements responsible for high CPU utilization, high latency, excessive row scanning, or inefficient execution. However, query optimization requires analysis and might also require schema changes, new indexes, application testing, and a controlled release. Increasing the instance’s compute capacity can relieve CPU pressure more immediately. Query investigation is a strong long-term optimization practice, but it is not the fastest corrective action in this scenario.

**Reference links**

- [docs.cloud.google.com/spanner/docs/instance-configurations](https://docs.cloud.google.com/spanner/docs/instance-configurations)
- [docs.cloud.google.com/spanner/docs/monitoring-cloud](https://docs.cloud.google.com/spanner/docs/monitoring-cloud)
- [docs.cloud.google.com/spanner/docs/create-manage-instances](https://docs.cloud.google.com/spanner/docs/create-manage-instances)

**Related notes:** [Spanner](../05-storage-databases-data/products/spanner.md)

</details>

[Back to index](#index)

---

### Q36

> ParcelPulse operates a package-tracking platform on Google Kubernetes Engine. Its real-time tracking API must remain continuously available, but its nightly analytics jobs can tolerate interruptions. You need to design the GKE Standard cluster to reduce compute costs while meeting these availability requirements. What should you do?  

- **A.** Create one node pool that uses standard VMs, and add the label cloud.google.com/gke-spot=true to the analytics Deployments.
- **B.** Create one node pool that uses Spot VMs, and add the label cloud.google.com/gke-spot=false to the real-time API Deployments.
- **C.** -Create a Spot VM node pool and a standard VM node pool.  
  -Schedule the real-time API on the Spot VM node pool and the analytics jobs on the standard VM node pool.
- **D.** -Create a Spot VM node pool and a standard VM node pool.  
  -Schedule the real-time API on the standard VM node pool and the analytics jobs on the Spot VM node pool.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a cluster containing only standard VM nodes cannot obtain Spot VM pricing merely by adding a label to a Deployment. The cloud.google.com/gke-spot=true label is automatically applied by GKE to nodes that actually use the Spot provisioning model. Workloads can use a nodeSelector or node affinity to target nodes with that label, but adding a similar label to a Deployment does not convert standard VMs into Spot VMs. Although placing every workload on standard VMs would provide greater availability, it would miss the opportunity to reduce the cost of the interruption-tolerant analytics jobs.

**B is incorrect** because a cluster containing only Spot VM nodes provides no standard VM capacity for the critical real-time API. Spot VMs cost less than standard VMs, but Compute Engine can reclaim them at any time, and their availability is not guaranteed. Setting cloud.google.com/gke-spot=false on a Deployment does not create standard nodes or prevent the Pods from running on Spot nodes when Spot nodes are the cluster’s only available capacity. Therefore, this configuration could interrupt the critical application components and would not meet the continuous-availability requirement.

**C is incorrect** because it assigns the workloads to the opposite of the appropriate node types. The critical real-time API would run on Spot VMs, which can be reclaimed at any time and are therefore unsuitable for application components that must remain continuously available. Meanwhile, the fault-tolerant analytics jobs would run on more expensive standard VMs even though they can tolerate interruptions. This design increases availability for the workloads that do not require it while exposing the critical workloads to avoidable disruption.

**D is correct** because separate node pools allow each workload category to use the provisioning model that matches its availability requirements. The critical real-time API should run on the standard VM node pool because standard VMs provide regular Compute Engine capacity and are not subject to Spot VM preemption. The interruption-tolerant analytics jobs should run on the Spot VM node pool because Spot VMs are offered at a substantial discount and are designed for stateless, batch, and fault-tolerant workloads. GKE automatically labels Spot VM nodes with cloud.google.com/gke-spot=true, so the analytics Pods can target those nodes by using a nodeSelector or node affinity. The critical Pods can target the standard node pool through its node-pool label, node affinity, or a combination of node labels and taints. This architecture maintains reliable capacity for critical services while reducing the compute cost of workloads that can recover from interruptions.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/spot-vms](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/spot-vms)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/spot-vms](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/spot-vms)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/node-pools](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/node-pools)

**Related notes:** [Spot VMs](../03-compute-containers/products/spot-vms.md) · [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q37

> Northstar Media deploys its streaming services to Google Kubernetes Engine (GKE) by applying Kubernetes YAML manifests through a GitOps pipeline. The platform team also wants to create and manage resources such as Cloud Storage buckets, Pub/Sub topics, and Cloud SQL instances through the same Kubernetes API, manifests, and deployment workflow. What should the team do?  

- **A.** Provision the additional Google Cloud resources manually through the Google Cloud console.
- **B.** Create shell scripts containing gcloud CLI commands and execute the scripts from an administrator workstation.
- **C.** Define the additional Google Cloud resources in Terraform configuration files and configure a Cloud Storage bucket as the Terraform state backend.
- **D.** Install Config Connector in a GKE cluster and represent the additional Google Cloud resources as Kubernetes custom resources in YAML manifests.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because the Google Cloud console provides an interactive interface for creating and modifying resources, but it does not use the same declarative Kubernetes workflow as the company’s application deployments. Manual console operations are difficult to reproduce consistently, review through source control, promote between environments, or execute through the existing GitOps pipeline. They can also cause configuration drift because the deployed state might differ from the configuration recorded by the development team. Although the console is useful for exploration, troubleshooting, and occasional administrative changes, it does not satisfy the requirement to manage Google Cloud infrastructure through Kubernetes manifests and tooling.

**B is incorrect** because shell scripts containing gcloud commands generally implement an imperative workflow. Each command tells Google Cloud to perform a specific operation, and the team must build additional logic to determine whether a resource already exists, compare its current configuration with the desired configuration, handle partial failures, process dependencies, and make repeated executions idempotent. Scripts can be stored in source control and automated, but they do not automatically make Google Cloud resources Kubernetes objects. They also do not provide Kubernetes reconciliation, in which a controller continuously attempts to make the actual resource configuration match the declared configuration.

**C is incorrect** because Terraform is a valid declarative infrastructure-as-code solution, and storing its state in a Cloud Storage backend is a recommended approach for team collaboration, state locking, durability, and separation of state from source control. However, Terraform introduces a separate configuration language, state-management mechanism, command-line workflow, and execution process. The requirement specifically calls for using the same Kubernetes-based approach and tooling already used for application deployments. Therefore, Terraform could manage the resources declaratively, but it would not allow the team to define them as Kubernetes custom resources and manage them through the Kubernetes API, kubectl, or the existing Kubernetes GitOps workflow.

**D is correct** because Config Connector enables Google Cloud resources to be represented and managed as Kubernetes custom resources. It installs Custom Resource Definitions and controllers that allow resources such as Cloud Storage buckets, Pub/Sub topics, service accounts, and databases to be described in Kubernetes YAML manifests. The team can store these manifests in the same source-control repositories, review them through the same change process, and apply them through the same kubectl or GitOps tooling used for GKE application deployments. Config Connector continuously reconciles the declared Kubernetes configuration with the corresponding Google Cloud resource, which provides a declarative and Kubernetes-native resource-management model that directly satisfies the requirement.

**Reference links**

- [cloud.google.com/config-connector/docs/overview](https://cloud.google.com/config-connector/docs/overview)
- [cloud.google.com/config-connector/docs/concepts/resources](https://cloud.google.com/config-connector/docs/concepts/resources)
- [cloud.google.com/docs/terraform/resource-management/store-state](https://cloud.google.com/docs/terraform/resource-management/store-state)

**Related notes:** [Config Connector](../08-iac-platform-ai/products/config-connector.md)

</details>

[Back to index](#index)

---

### Q38

> LedgerSpring Insurance generates daily financial reconciliation reports after business hours. The processing application runs once each night, completes a finite set of tasks, and exits. LedgerSpring wants a managed solution that incurs charges only while the processing tasks run and automatically restarts failed tasks. What should the company do?  

- **A.** Package the processing application in a container and deploy it as a Google Kubernetes Engine (GKE) CronJob.
- **B.** Build an HTTP application, deploy it as a Cloud Run service, and configure Cloud Scheduler to invoke its endpoint nightly.
- **C.** Package the processing application in a container, deploy it as a Cloud Run job, and use Cloud Scheduler to execute the job nightly.
- **D.** Build an HTTP application, deploy it as a Google Kubernetes Engine (GKE) Deployment, and configure Cloud Scheduler to invoke its endpoint nightly.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a GKE CronJob can schedule Kubernetes Jobs and can retry failed Pods according to the Job’s backoff policy, so it is technically capable of running the workload. However, it requires a GKE cluster and introduces cluster provisioning, administration, upgrades, capacity management, and cluster-related costs. Using an existing GKE environment might make this approach reasonable, but the scenario does not indicate that the company already operates a cluster. Creating and maintaining a Kubernetes environment solely for one nightly batch workload is less cost-effective and operationally more complex than using a fully managed Cloud Run job.

**B is incorrect** because a Cloud Run service is intended primarily for applications that listen for incoming HTTP requests. Cloud Scheduler can invoke such a service on a schedule, and Cloud Scheduler can retry unsuccessful HTTP deliveries when its retry settings are configured. However, this design requires the batch process to operate within a request-handling model and ties completion to HTTP request behavior. It also does not provide the task-oriented execution, completion status, configurable task retries, and extended task timeout capabilities that Cloud Run jobs provide specifically for finite batch workloads. A Cloud Run service is therefore less appropriate than a Cloud Run job for a process that starts, performs work, and exits.

**C is correct** because Cloud Run jobs are designed for finite containerized workloads that perform processing and terminate instead of continuously listening for requests. Cloud Scheduler can trigger the Cloud Run job every night by using a cron schedule. Each job execution can contain one or more tasks, and Cloud Run jobs provide a configurable maximum-retries setting that restarts a failed task automatically. The default maximum is three retries, although the company can adjust it according to its reliability requirements. Cloud Run is fully managed, so the company does not need to provision or maintain a Kubernetes cluster or keep compute capacity running between executions. The company primarily pays for the CPU and memory consumed while the job is executing, which makes this solution well suited to an overnight workload that remains idle for most of the day. The application should also make its operations idempotent and store checkpoints or intermediate results in durable storage so that retries do not create duplicate accounting entries.

**D is incorrect** because a GKE Deployment is designed to maintain a specified number of continuously running application replicas, typically for long-lived services. It is not the appropriate Kubernetes controller for a finite batch process that should run to completion once per night. Cloud Scheduler could invoke an HTTP endpoint exposed by the Deployment, but the company would still need to operate a GKE cluster and potentially keep application Pods available while no batch processing is occurring. A Deployment also does not directly provide the batch completion and retry semantics of a Kubernetes Job or Cloud Run job. This design therefore adds unnecessary infrastructure, operational complexity, and idle-resource costs.

**Reference links**

- [docs.cloud.google.com/run/docs/execute/jobs-on-schedule](https://docs.cloud.google.com/run/docs/execute/jobs-on-schedule)
- [docs.cloud.google.com/run/docs/configuring/max-retries](https://docs.cloud.google.com/run/docs/configuring/max-retries)
- [docs.cloud.google.com/run/docs/jobs-cost-optimization](https://docs.cloud.google.com/run/docs/jobs-cost-optimization)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md) · [Cloud Scheduler](../04-events-integration/products/cloud-scheduler.md)

</details>

[Back to index](#index)

---

### Q39

> PulseTrack is developing a public web application that responds asynchronously to events generated by several Google Cloud services. The development team wants to use a standardized event-delivery mechanism, avoid managing infrastructure, and ensure that the application can scale to zero when it receives no traffic or events. What should the team do?  

- **A.** Deploy the application to Google Kubernetes Engine (GKE), and use Pub/Sub to deliver events.
- **B.** Deploy the application to Compute Engine, and use Pub/Sub to deliver events.
- **C.** Deploy the application to Google Kubernetes Engine (GKE), and use Eventarc to deliver events.
- **D.** Deploy the application to Cloud Run, and use Eventarc to deliver events.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because GKE requires the organization to provision and manage a Kubernetes cluster, including cluster configuration, node capacity, upgrades, networking, security, and workload scaling. Standard GKE clusters generally continue to incur cluster management and node costs even when the application is not processing events. Although Autopilot can reduce infrastructure management, GKE is still more operationally complex than Cloud Run for a simple event-driven application. Pub/Sub can deliver asynchronous messages, but developers would need to configure subscriptions, message handling, authentication, retries, and potentially an HTTP push endpoint or subscriber process. This combination does not minimize development and operational costs as effectively as using Cloud Run with Eventarc.

**B is incorrect** because Compute Engine requires the team to manage virtual machine instances, operating systems, patches, startup behavior, availability, capacity, and application deployment. A running Compute Engine VM continues to incur charges even when the application is idle. The team could stop the VM to reduce compute charges, but a stopped VM cannot immediately receive public requests or Pub/Sub messages, and automation would be required to start it when needed. Pub/Sub supports asynchronous event delivery, but combining it with manually managed virtual machines introduces unnecessary infrastructure management and does not provide automatic scale-to-zero behavior.

**C is incorrect** because Eventarc is an appropriate standardized service for routing events from Google Cloud services, but deploying the application to GKE introduces unnecessary infrastructure and cost. The team would need to operate a Kubernetes cluster, configure the application as a Kubernetes workload, expose it through networking resources, and manage scaling behavior. Even when application Pods scale down, the underlying GKE cluster and its nodes can continue to generate costs. This option satisfies the event-delivery requirement but does not satisfy the requirement to minimize operational effort and avoid workload compute costs when the application is unused as effectively as Cloud Run.

**D is correct** because Cloud Run is a fully managed serverless application platform that can host an HTTP-based application and make it accessible through a public endpoint. The team does not need to provision virtual machines, manage Kubernetes nodes, patch operating systems, or administer a cluster. By default, a Cloud Run service can automatically scale its application instances according to incoming requests and scale to zero when no requests are being processed, provided that minimum instances are not configured. This minimizes compute costs during idle periods. Eventarc provides a standardized event-routing layer that can receive events from supported Google Cloud services, filter them through triggers, and deliver them to the Cloud Run service using the CloudEvents format. Eventarc also manages much of the underlying event-delivery infrastructure, reducing the amount of custom subscriber and integration code that developers must maintain. Cloud Run with Eventarc therefore provides public web accessibility, asynchronous event processing, standardized event delivery, low operational overhead, and scale-to-zero behavior.

**Reference links**

- [docs.cloud.google.com/run/docs/overview/what-is-cloud-run](https://docs.cloud.google.com/run/docs/overview/what-is-cloud-run)
- [docs.cloud.google.com/eventarc/docs](https://docs.cloud.google.com/eventarc/docs)
- [docs.cloud.google.com/eventarc/docs/roles-permissions](https://docs.cloud.google.com/eventarc/docs/roles-permissions)

**Related notes:** [Eventarc](../04-events-integration/products/eventarc.md)

</details>

[Back to index](#index)

---

### Q40

> AuroraFleet, a logistics analytics company, runs 11 Linux virtual machines on Compute Engine and expects to deploy several more next month. Administrators must connect to every current and future VM from their local SSH clients over the internet. The VMs must use only internal IP addresses, and the company wants to avoid configuring a separate connectivity mechanism for each VM. What should AuroraFleet configure?  

- **A.** Configure Identity-Aware Proxy to protect HTTPS applications.
- **B.** Configure Identity-Aware Proxy for SSH and TCP forwarding.
- **C.** Generate an SSH key pair and add the public key to project-wide metadata.
- **D.** Generate an SSH key pair and add the private key to project-wide metadata.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Identity-Aware Proxy protection for HTTPS applications is intended to control access to web applications and other HTTP or HTTPS resources. It authenticates and authorizes requests to supported web resources, but this configuration does not create a TCP tunnel to port 22 on a Compute Engine VM. SSH is a TCP-based protocol rather than an HTTPS application request, so configuring only the HTTPS functionality of Identity-Aware Proxy would not provide the administrators with the required SSH connectivity to VMs that have no external IP addresses.

**B is correct** because Identity-Aware Proxy TCP forwarding provides authenticated and authorized access to SSH and other TCP services without requiring the target Compute Engine instances to have external IP addresses. The administrator’s connection is sent through the Identity-Aware Proxy service and forwarded to the VM’s internal IP address. Access can be centrally controlled with IAM permissions, such as the Identity-Aware Proxy-secured Tunnel User role, instead of exposing port 22 directly to the public internet. A VPC firewall rule must permit SSH traffic from the Identity-Aware Proxy TCP forwarding address range, commonly 35.235.240.0/20, to the applicable VMs. These controls can be configured at the project, network, IAM, and firewall-rule levels so that existing VMs and future VMs matching the rule can be reached without assigning an external IP or creating a separate public-access configuration for every instance. Administrators can connect by using a command such as gcloud compute ssh with the --tunnel-through-iap flag or configure a compatible SSH client to use an Identity-Aware Proxy tunnel.

**C is incorrect** because adding a public SSH key to project-wide metadata addresses SSH authentication but does not provide network connectivity to the VMs. Eligible Compute Engine instances can obtain a project-wide public key from metadata and use it to verify a client that possesses the corresponding private key. However, a VM with only an internal IP address is not directly reachable from an SSH client on the public internet. The administrator would still need a network path such as Identity-Aware Proxy TCP forwarding, Cloud VPN, Cloud Interconnect, or a bastion host. Project-wide SSH keys can also be ignored by instances configured to block project-wide keys or use OS Login. Therefore, this option does not satisfy the central requirement of reaching private VMs over the internet.

**D is incorrect** because a private SSH key must remain confidential and be stored securely on the administrator’s client device or in an appropriate secrets-management system. Compute Engine metadata accepts public SSH keys for metadata-based SSH authentication; it should never contain the corresponding private key. Storing a private key in project metadata could expose it to users, services, or workloads that can read that metadata and would compromise every system that trusts the key. This option also fails to create a network route to instances that have no external IP addresses.

**Reference links**

- [docs.cloud.google.com/iap/docs/using-tcp-forwarding](https://docs.cloud.google.com/iap/docs/using-tcp-forwarding)
- [docs.cloud.google.com/compute/docs/connect/ssh-using-iap](https://docs.cloud.google.com/compute/docs/connect/ssh-using-iap)
- [docs.cloud.google.com/compute/docs/connect/add-ssh-keys](https://docs.cloud.google.com/compute/docs/connect/add-ssh-keys)

**Related notes:** [Identity-Aware Proxy (IAP)](../02-identity-security/products/identity-aware-proxy.md)

</details>

[Back to index](#index)

---

### Q41

> Lexora Health wants to fine-tune open large language models by using several terabytes of internal medical-support conversations stored in Google Cloud. The machine learning engineers need a flexible platform that can run containerized training frameworks, scale distributed training workloads across multiple nodes, and use GPUs or TPUs. What should you do?  

- **A.** Use Dataflow to execute the model fine-tuning workloads.
- **B.** Deploy Jupyter Notebooks on a Compute Engine managed instance group and execute the fine-tuning workloads.
- **C.** Use Cloud Run jobs with GPUs to execute the fine-tuning workloads.
- **D.** Use Google Kubernetes Engine (GKE) with hardware accelerators to execute the fine-tuning workloads.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Dataflow is primarily a fully managed service for executing Apache Beam batch and streaming data-processing pipelines. Dataflow ML can perform data preparation, feature transformation, and local or remote inference by using trained models, so it could help process Lexora Health’s proprietary dataset before training. However, Dataflow is not intended to be the primary platform for orchestrating distributed, accelerator-intensive LLM fine-tuning. It does not provide the same control over GPU or TPU topology, distributed training frameworks, container scheduling, specialized networking, and multi-node training configurations that GKE provides. Therefore, Dataflow can complement the solution as a data-processing layer, but it is not the best platform for the fine-tuning jobs themselves.

**B is incorrect** because Compute Engine virtual machines can use powerful GPU machine types and can technically run Jupyter Notebooks and model-training workloads. However, a managed instance group is intended to manage a group of similar virtual machine instances by using a common instance template. It is commonly used for stateless applications that require autoscaling, load balancing, automatic healing, or regional availability. Interactive Jupyter Notebook environments are generally stateful and user-specific, making them a poor match for a homogeneous managed instance group. The team would also need to manage notebook access, GPU drivers, distributed-training coordination, job scheduling, resource allocation, software environments, scaling behavior, storage integration, and failed training jobs. This approach creates significantly more operational work and offers less effective workload orchestration than GKE.

**C is incorrect** because Cloud Run jobs now support GPUs and can run containerized AI workloads, including LLM training and fine-tuning. Cloud Run is a strong serverless choice for smaller, independent, or single-GPU training tasks because it manages the underlying infrastructure and charges for resources while jobs execute. However, each Cloud Run instance can be configured with only one GPU, and Cloud Run provides less control over accelerator topology, node configuration, specialized networking, and tightly coordinated multi-node distributed training. Fine-tuning large models against a very large proprietary dataset can require multiple GPUs or TPUs, distributed training libraries, advanced scheduling, persistent high-performance storage, and customized infrastructure. Cloud Run jobs can be appropriate for limited fine-tuning workloads, but they are not as scalable or flexible as GKE for the large distributed training requirement described.

**D is correct** because Google Kubernetes Engine provides a managed Kubernetes platform designed to orchestrate containerized workloads across scalable clusters. GKE supports GPU-equipped node pools and Cloud TPUs, allowing the team to select accelerators based on model size, training framework, performance requirements, and cost. It can run distributed training frameworks such as PyTorch, TensorFlow, JAX, Ray, and Kubeflow while coordinating training processes across multiple nodes and accelerators. GKE also provides Kubernetes-native scheduling, autoscaling, workload isolation, job recovery, resource quotas, and integration with services such as Cloud Storage, Managed Lustre, Artifact Registry, and Cloud Operations Suite. The team can create specialized accelerator node pools, scale them according to demand, and use Spot VMs or flex-start provisioning where appropriate to reduce training costs. Google specifically recommends GKE when organizations need deep infrastructure control, portability, customized AI pipelines, and large-scale model training or fine-tuning. Therefore, GKE with hardware accelerators is the most scalable and flexible option for this requirement.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/machine-learning](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/machine-learning)
- [docs.cloud.google.com/kubernetes-engine/docs/tutorials/finetune-gemma-gpu](https://docs.cloud.google.com/kubernetes-engine/docs/tutorials/finetune-gemma-gpu)
- [docs.cloud.google.com/run/docs/configuring/jobs/gpu](https://docs.cloud.google.com/run/docs/configuring/jobs/gpu)

</details>

[Back to index](#index)

---

### Q42

> LedgerLoop operates many independent Google Cloud projects for its financial analytics teams. Each project has a defined monthly budget, and the responsible team must receive a message in its Slack channel when project spending reaches 85% of the budget. The solution should respond promptly, use managed services, and require minimal operational support. What should the cloud operations team do?  

- **A.** Enable detailed Cloud Billing data export to BigQuery, and create a scheduled Cloud Composer DAG that queries project costs and sends Slack messages.
- **B.** Configure programmatic budget notifications to publish messages to a Pub/Sub topic, and deploy a Pub/Sub-triggered Cloud Run function that sends the notifications to Slack.
- **C.** Configure programmatic budget notifications to publish messages to a Pub/Sub topic, and deploy a Compute Engine managed instance group that pulls the messages and sends them to Slack.
- **D.** Enable detailed Cloud Billing data export to BigQuery, and configure Cloud Scheduler to invoke a Cloud Run function that queries project costs and sends Slack messages.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because detailed Cloud Billing export to BigQuery is primarily intended for cost analysis, reporting, chargeback, and historical investigation. Building a Cloud Composer DAG to query the exported data requires the team to operate an Apache Airflow environment, write and maintain SQL queries, manage DAG scheduling, prevent duplicate notifications, track previously crossed thresholds, handle Slack API failures, and account for billing-export data latency. Because the DAG runs according to a schedule rather than directly in response to a budget event, the notification can also be delayed until the next execution. Cloud Composer is valuable for coordinating complex data workflows, but it is unnecessarily complex and costly for forwarding budget-threshold events to Slack.

**B is correct** because Cloud Billing budgets support programmatic notifications through Pub/Sub. The team can create project-specific budgets, define threshold rules such as 85% of the budget, and connect each budget to a Pub/Sub topic. When Cloud Billing publishes an updated budget notification, a Pub/Sub-triggered Cloud Run function can process the message, identify the affected project and threshold, format a Slack message, and send it to the appropriate Slack incoming webhook or Slack API endpoint. This design is event-driven, avoids continuously running infrastructure, automatically scales according to the number of messages, and requires minimal server and operating-system maintenance. The function should also securely retrieve the Slack webhook or token from Secret Manager, validate the budget notification fields, and handle retries idempotently so that duplicate Pub/Sub deliveries do not produce unwanted duplicate Slack messages. Budget notifications report spending conditions but do not automatically cap or stop project expenditure.

**C is incorrect** because programmatic budget notifications delivered through Pub/Sub are appropriate, but a Compute Engine managed instance group is unnecessary for processing a small, event-driven notification workload. The team would need to configure instance templates, machine images, startup scripts, service accounts, autoscaling, health checks, operating-system updates, application deployment, subscription pulling, message acknowledgment, retry handling, and monitoring. The instances might also remain running when there are no budget events, increasing cost and maintenance. A managed instance group is useful for persistent VM-based workloads, but a Pub/Sub-triggered Cloud Run function is simpler and can scale from zero when messages arrive.

**D is incorrect** because Cloud Scheduler and a Cloud Run function would provide a serverless scheduled solution, but the team would still need to build a custom budget-evaluation system around the BigQuery billing export. The function would have to query cumulative project spending, compare it with configured budgets, determine whether a threshold had just been crossed, record notification state, suppress duplicate Slack messages, and compensate for billing-data availability delays. Cloud Scheduler also introduces polling latency because the notification is generated only when the scheduled job executes. Google Cloud already provides budget threshold evaluation and programmatic Pub/Sub notifications, so recreating this logic with scheduled BigQuery queries adds complexity and maintenance without improving the requirement.

**Reference links**

- [cloud.google.com/billing/docs/how-to/budgets-programmatic-notifications](https://cloud.google.com/billing/docs/how-to/budgets-programmatic-notifications)
- [cloud.google.com/run/docs/triggering/pubsub-triggers](https://cloud.google.com/run/docs/triggering/pubsub-triggers)
- [cloud.google.com/billing/docs/how-to/export-data-bigquery](https://cloud.google.com/billing/docs/how-to/export-data-bigquery)

**Related notes:** [Pub/Sub](../04-events-integration/products/pub-sub.md) · [Cloud Billing](../07-operations-cost/products/cloud-billing.md)

</details>

[Back to index](#index)

---

### Q43

> BrightPath Media manages several production projects inside a folder named Digital Operations. The cloud administrator needs to activate Gemini Cloud Assist for the existing projects in that folder through a single folder-level configuration. A Google Cloud CLI command cannot perform the setup at the folder scope. What should the administrator do?  

- **A.** Generate a service account key and install Gemini CLI on a Compute Engine VM in every project.
- **B.** Open the Admin for Gemini page in the Google Cloud console, select the Digital Operations folder, and enable the required Cloud Assist APIs.
- **C.** Enable only the Cloud Asset API on the organization resource.
- **D.** Create an Application Design Center space associated with the Digital Operations folder.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because running Gemini CLI from a Compute Engine VM does not enable Gemini Cloud Assist for the projects in a folder. Gemini CLI is a command-line interface that users can run to interact with Gemini capabilities, but it is not the administrative mechanism for activating Gemini Cloud Assist across a resource hierarchy. Creating long-lived service account keys would also introduce unnecessary credential-management and security risks. The administrator does not need to deploy a VM or configure a separate Gemini CLI installation in every project.

**B is correct** because folder-level Gemini Cloud Assist setup must be performed through the Google Cloud console. The administrator should open the Admin for Gemini page, use the resource selector to choose the folder, select Enable Cloud Assist APIs, review the required and recommended APIs, and enable Gemini Cloud Assist. This operation enables the required APIs for the existing projects in the selected folder. Google Cloud CLI and direct API methods support project-level setup but do not support setting up Gemini Cloud Assist at the folder level. The administrator must also grant appropriate folder-level IAM roles, such as Gemini Cloud Assist User and Cloud Asset Viewer, to the intended users. Projects added to the folder later are not automatically enabled, so Gemini Cloud Assist must be enabled separately for those new projects.

**C is incorrect** because the Cloud Asset API provides access to resource inventory and metadata, but it is only one supporting API used by Gemini Cloud Assist. Enabling it alone does not activate the Gemini Cloud Assist service, its underlying Gemini for Google Cloud capabilities, or other required application and optimization APIs. Enabling an API at the organization root also does not replace the documented folder-level Gemini Cloud Assist setup workflow.

**D is incorrect** because an Application Design Center space is used to design, standardize, and manage application infrastructure. It does not activate Gemini Cloud Assist for every project in a folder. Application management can be enabled at the folder level when Gemini Cloud Assist will work with applications, but that is an additional configuration step rather than the primary procedure for enabling Cloud Assist APIs across existing folder projects.

**Reference links**

- [docs.cloud.google.com/cloud-assist/set-up-gemini](https://docs.cloud.google.com/cloud-assist/set-up-gemini)
- [docs.cloud.google.com/cloud-assist/iam-requirements](https://docs.cloud.google.com/cloud-assist/iam-requirements)
- [docs.cloud.google.com/cloud-assist/admin-settings](https://docs.cloud.google.com/cloud-assist/admin-settings)

**Related notes:** [Gemini Cloud Assist](../08-iac-platform-ai/products/gemini-cloud-assist.md)

</details>

[Back to index](#index)

---

### Q44

> AsterPeak Manufacturing is migrating its SAP HANA database to Compute Engine. The database storage layer must sustain bursts above 230,000 IOPS, and the database files must remain available after VM restarts, host maintenance, and other instance lifecycle events. Which storage option should the cloud team use?  

- **A.** Attach Hyperdisk Extreme volumes for the SAP HANA data files.
- **B.** Create in-memory RAM disks for the SAP HANA data files.
- **C.** Attach Local SSD disks for the SAP HANA data files.
- **D.** Attach Hyperdisk Throughput volumes for the SAP HANA data files.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Hyperdisk Extreme is durable, high-performance network block storage designed for demanding database workloads such as SAP HANA, Oracle, and high-end SQL Server. A single Hyperdisk Extreme volume can be provisioned with up to 350,000 IOPS, subject to the selected volume size, Compute Engine machine type, and per-instance performance limits. This capacity satisfies a workload that frequently exceeds 230,000 IOPS. Because Hyperdisk storage is independent of the physical host running the VM, its data persists when the VM is restarted or moved during supported lifecycle operations. Hyperdisk Extreme also allows IOPS to be provisioned independently from storage capacity, enabling the team to allocate the performance required by SAP HANA without relying only on increasing disk size. The team must still select an SAP HANA-certified machine type and verify that the machine’s aggregate Hyperdisk limits can deliver the provisioned performance.

**B is incorrect** because a RAM disk stores data in the VM’s volatile memory rather than in durable block storage. RAM disks can provide extremely low latency and high I/O performance, but their contents can be lost when the VM stops, terminates, crashes, or experiences an unrecoverable failure. They also consume memory that would otherwise be available to SAP HANA, which is itself an in-memory database with substantial memory requirements. A RAM disk might be appropriate for temporary caches, scratch files, or data that can be regenerated, but it is unsuitable for persistent SAP HANA data and log volumes.

**C is incorrect** because Local SSD provides very high IOPS and low latency by attaching physically local flash storage to the Compute Engine host. However, Local SSD is not a fully durable storage option for critical database data. Its contents are preserved during some events, such as a normal guest operating system reboot or supported live migration, but data can be lost during instance deletion, certain stop operations, preemption, host failure, or an unsuccessful Local SSD recovery. Local SSD data also cannot be protected with standard disk snapshots or disk clones. Consequently, Local SSD can be useful for temporary SAP HANA working data or caches when the application can tolerate data loss, but it should not be the authoritative storage location for persistent SAP HANA application data.

**D is incorrect** because Hyperdisk Throughput is optimized for bandwidth-intensive, sequential workloads that require high throughput but relatively low IOPS, such as analytics, data processing, and large streaming reads or writes. Its IOPS are derived from its configured throughput and are limited to approximately 9,600 IOPS per volume, which is far below the requirement of more than 230,000 IOPS. Hyperdisk Throughput is durable and would preserve data through VM restarts, but it cannot satisfy the workload’s random I/O performance requirement. Hyperdisk Extreme is the appropriate Hyperdisk type when extremely high provisioned IOPS are required.

**Reference links**

- [cloud.google.com/compute/docs/disks/hd-types/hyperdisk-extreme](https://cloud.google.com/compute/docs/disks/hd-types/hyperdisk-extreme)
- [cloud.google.com/compute/docs/disks/hd-types/hyperdisk-throughput](https://cloud.google.com/compute/docs/disks/hd-types/hyperdisk-throughput)
- [cloud.google.com/sap/docs/sap-hana-planning-guide](https://cloud.google.com/sap/docs/sap-hana-planning-guide)

**Related notes:** [Hyperdisk](../03-compute-containers/products/hyperdisk.md)

</details>

[Back to index](#index)

---

### Q45

> HarborCart operates an online marketplace supported by 32 development squads. Each squad regularly provisions a frontend, an API service, and a database on Google Cloud. However, independently written Terraform configurations often exclude mandatory audit logging, resource labels, and network security settings. The cloud enablement team needs to offer developers a self-service method for deploying organization-approved application architectures while allowing the team to maintain and revise the standard architecture centrally. Requiring a reviewer to approve every deployment would reduce development velocity. What should the cloud enablement team do?  

- **A.** Grant all developers the Project Editor role and instruct them to generate Terraform configurations with Gemini CLI.
- **B.** Build and share standardized application templates in Application Design Center, and allow developers to deploy applications from those templates.
- **C.** Run Gemini Cloud Assist investigations after deployment to identify resources that do not comply with the architecture standards.
- **D.** Configure a Cloud Build pipeline that requires approval from the security team before every Terraform apply operation.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because granting every developer the Project Editor role provides broad permissions to create, update, and delete many resources within a project, which conflicts with the principle of least privilege. Gemini CLI can assist developers with designing infrastructure and generating Terraform, but independently generated configurations do not by themselves guarantee that every deployment contains the platform team’s required logging, labels, topology, and network controls. Developers could receive different generated configurations, modify the code, or omit important controls. This option also does not provide a centrally governed catalog of approved architectures or a controlled mechanism for distributing revisions to deployed applications.

**B is correct** because Application Design Center is designed for platform teams to create, verify, publish, and share reusable application templates. The platform team can define the complete architecture, including the frontend, application tier, database, logging configuration, labels, network relationships, and security settings. Developers can then create and deploy applications from the approved templates without independently assembling every resource or writing inconsistent Terraform. The templates generate Terraform while preserving the architecture established by the platform team. This provides self-service deployment without requiring manual approval for every request. Application Design Center also supports template revisions, allowing the platform team to update the standard design centrally and enabling applications based on the template to adopt newer revisions. This combination of reusable templates, centralized architectural control, consistent infrastructure generation, and developer self-service directly satisfies the requirements.

**C is incorrect** because Gemini Cloud Assist investigations are primarily intended for troubleshooting, root-cause analysis, and diagnosing operational problems across applications and infrastructure. They can analyze signals such as logs, metrics, alerts, configurations, and application behavior to help identify the cause of an incident. They are not a preventive architecture-standardization mechanism that ensures every application is initially deployed with mandatory controls. Detecting missing logging, labels, or network restrictions only after resources have been deployed is reactive and can leave noncompliant resources running until someone reviews and remediates them. This option also does not give developers a reusable, centrally managed, self-service architecture.

**D is incorrect** because Cloud Build can gate a triggered build by requiring manual approval, and a pipeline could run Terraform validation or deployment steps. However, requiring the security team to approve every Terraform apply creates the exact manual bottleneck that the organization wants to avoid. It would increase review workload and slow application delivery as the number of development teams and deployments grows. Approval gates can be appropriate for exceptional or especially sensitive changes, but they are not the best primary solution when developers need routine self-service access to approved architectures. Publishing governed templates in Application Design Center moves the controls into the architecture itself instead of relying on repeated human reviews.

**Reference links**

- [docs.cloud.google.com/application-design-center/docs/overview](https://docs.cloud.google.com/application-design-center/docs/overview)
- [docs.cloud.google.com/application-design-center/docs/design-application-templates](https://docs.cloud.google.com/application-design-center/docs/design-application-templates)
- [docs.cloud.google.com/application-design-center/docs/deploy-applications](https://docs.cloud.google.com/application-design-center/docs/deploy-applications)

**Related notes:** [Application Design Center](../08-iac-platform-ai/products/application-design-center.md)

</details>

[Back to index](#index)

---

### Q46

> MetroPulse operates a city transit application that occasionally fails to process ticket purchases and returns HTTP 502 errors. The request path includes Cloud Run services, a Cloud SQL database, and an external Application Load Balancer. The operations team has access to logs, metrics, errors, and recent infrastructure changes, but manually comparing this information across multiple Google Cloud products is delaying incident resolution. Which tool should the team use first to obtain an assisted root-cause analysis across the distributed application?  

- **A.** Start a Gemini Cloud Assist investigation.
- **B.** Model the affected application in Application Design Center.
- **C.** Run Gemini CLI against the application’s source code repository.
- **D.** Export Cloud Asset Inventory data to BigQuery and analyze the asset records.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Gemini Cloud Assist investigations are specifically designed to perform assisted root-cause analysis for applications and infrastructure running in complex, distributed Google Cloud environments. An investigation can gather and correlate relevant evidence such as logs, metrics, errors, alerts, resource configurations, recent changes, and relationships between application components. It uses this evidence to generate observations, develop and evaluate hypotheses, identify likely causes, and recommend remediation steps. This is particularly useful when a failure crosses service boundaries, such as a request passing through an Application Load Balancer to Cloud Run and then Cloud SQL. Instead of requiring operators to manually move between separate product consoles and construct a timeline themselves, Gemini Cloud Assist investigations synthesize the available operational signals into a unified troubleshooting analysis. Because the immediate requirement is to diagnose intermittent production errors rather than redesign or inventory the environment, starting an investigation is the most direct and appropriate first action.

**B is incorrect** because Application Design Center is intended for designing, deploying, sharing, and managing application architectures on Google Cloud. Platform teams can use it to create standardized application templates, represent relationships between cloud resources, generate Terraform, and help developers deploy applications that follow organizational standards. Although it can provide an application-centric representation of infrastructure, it is not primarily an incident investigation or root-cause analysis service. Creating a design in Application Design Center would not automatically correlate the application’s current logs, metrics, errors, and recent configuration changes to explain an intermittent production failure. It may help improve the application’s architecture or deployment process later, but it is not the appropriate first tool for diagnosing the active issue.

**C is incorrect** because Gemini CLI is an AI-powered command-line assistant that can help developers inspect source files, explain code, generate code, modify project files, and perform development-related tasks from a terminal. Reviewing the source repository might reveal a software defect, but the available evidence indicates that the failure spans multiple managed services and infrastructure components. A source-code-focused analysis would not, by itself, comprehensively correlate Cloud Run runtime metrics, Cloud SQL behavior, load-balancer logs, infrastructure configurations, and recent Google Cloud changes. It would also begin with the unsupported assumption that the root cause exists in the application code. Gemini Cloud Assist investigations are better suited to analyzing the complete distributed environment before the team decides whether detailed source-code investigation is necessary.

**D is incorrect** because Cloud Asset Inventory provides information about Google Cloud resources, IAM policies, organization policies, and asset metadata. Exporting its data to BigQuery can be useful for inventory reporting, governance analysis, compliance checks, security reviews, and querying resource configurations at scale. However, an asset export is primarily a structured snapshot of resource metadata; it is not a purpose-built root-cause analysis workflow. It does not automatically synthesize runtime logs, performance metrics, error patterns, recent operational events, and dependencies into hypotheses about an intermittent application failure. The team could manually join exported asset information with other datasets, but that would require additional engineering and would continue the manual correlation problem described in the question.

**Reference links**

- [docs.cloud.google.com/cloud-assist/investigations](https://docs.cloud.google.com/cloud-assist/investigations)
- [docs.cloud.google.com/application-design-center/docs/overview](https://docs.cloud.google.com/application-design-center/docs/overview)
- [docs.cloud.google.com/asset-inventory/docs/export-bigquery](https://docs.cloud.google.com/asset-inventory/docs/export-bigquery)

**Related notes:** [Gemini Cloud Assist](../08-iac-platform-ai/products/gemini-cloud-assist.md)

</details>

[Back to index](#index)

---

### Q47

> HealthAxis operates a patient analytics platform backed by a Bigtable instance with five nodes. The tables contain protected personal and medical information. The security team must send records of all table reads, table writes, metadata reads, and configuration reads to the company’s Security Information and Event Management system. What should the team do?  

- **A.** -In Cloud Monitoring, create a custom monitoring configuration for the Bigtable instance to detect database changes.  
  -Configure a webhook alert whose destination is the SIEM endpoint.
- **B.** -On the Audit Logs page, enable only Admin Write audit logs for Bigtable.  
  -Deploy a Cloud Run function that periodically copies matching Cloud Logging entries to the SIEM.
- **C.** -On the Audit Logs page, enable Data Read, Data Write, and Admin Read audit logs for Bigtable.  
  -Create a Cloud Logging sink with a Pub/Sub topic as its destination, and configure the SIEM as a subscriber to the topic.
- **D.** -Install the Ops Agent on each Bigtable node.  
  -Create a service account with permission to read the Bigtable instance, and run a custom Dataflow pipeline that sends the collected logs to the SIEM.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Cloud Monitoring collects metrics that describe resource health, performance, utilization, and availability. Metrics and alerts can indicate conditions such as elevated latency, high CPU utilization, storage growth, or error rates, but they do not create a security audit record for every principal that reads or writes Bigtable data. A monitoring alert also does not capture metadata and configuration read operations with the caller identity, method name, resource, timestamp, and authorization details required for security investigations. Webhooks are intended to deliver alert notifications when metric conditions are met, not to stream individual Bigtable audit events to a SIEM.

**B is incorrect** because Admin Write operations are recorded in Admin Activity audit logs, which are enabled by default and cannot be disabled. These logs capture administrative changes such as creating, updating, or deleting certain Bigtable resources, but they do not capture table data reads, table data writes, or read-only access to metadata and configuration. Enabling only Admin Write logging therefore does not satisfy the requirement to record every data and administrative read operation. A custom Cloud Run function would also introduce unnecessary code, scheduling, error handling, monitoring, and maintenance. Cloud Logging provides native log routing through sinks, so a custom function is not the recommended integration method.

**C is correct** because Bigtable operations that require DATA_READ, DATA_WRITE, or ADMIN_READ permissions generate Data Access audit logs. Data Read logs capture operations that retrieve table data, Data Write logs capture operations that modify table data, and Admin Read logs capture operations that retrieve metadata or configuration information. These Data Access categories generally must be explicitly enabled. Administrative changes that use ADMIN_WRITE permissions are already recorded automatically as Admin Activity audit logs. A Cloud Logging sink can filter the required Bigtable audit logs and route them to a Pub/Sub topic in near real time. The SIEM can subscribe to that topic directly or through its supported connector, providing a managed and scalable mechanism for ingesting the audit records without operating a custom log-export service. Because Bigtable can process a high volume of requests, the company should also evaluate Cloud Logging ingestion and retention costs before enabling comprehensive Data Read and Data Write logging.

**D is incorrect** because Bigtable is a fully managed Google Cloud service, and customers do not have operating-system access to its nodes. The Ops Agent is installed on supported virtual machines or other customer-managed hosts; it cannot be installed on managed Bigtable nodes. A service account with Bigtable read permissions would allow a Dataflow pipeline to read database information, but it would not generate historical audit records identifying every user or workload that accessed the data. Building a custom Dataflow export pipeline would also add unnecessary processing costs and operational complexity when Cloud Audit Logs and a Cloud Logging sink provide the required native functionality.

**Reference links**

- [docs.cloud.google.com/bigtable/docs/audit-logging](https://docs.cloud.google.com/bigtable/docs/audit-logging)
- [docs.cloud.google.com/logging/docs/audit/configure-data-access](https://docs.cloud.google.com/logging/docs/audit/configure-data-access)
- [docs.cloud.google.com/logging/docs/export/pubsub](https://docs.cloud.google.com/logging/docs/export/pubsub)

**Related notes:** [Pub/Sub](../04-events-integration/products/pub-sub.md) · [Cloud Audit Logs](../02-identity-security/products/cloud-audit-logs.md)

</details>

[Back to index](#index)

---

### Q48

> Northstar Labs maintains a local repository containing a Python API, automated tests, and infrastructure modules. An engineer wants an AI coding agent that operates inside the terminal, reads and modifies repository files, runs permitted shell commands, and diagnoses failing tests. The engineer does not need commands for administering Gemini Code Assist or Gemini Cloud Assist resources. Which tool should the engineer use?  

- **A.** Use the gcloud gemini command group.
- **B.** Start a Gemini Cloud Assist investigation.
- **C.** Use Gemini CLI.
- **D.** Import the project into Application Design Center.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the gcloud gemini command group is part of the Google Cloud CLI and is used to manage resources associated with Gemini Code Assist and Gemini Cloud Assist. The official command documentation explicitly distinguishes these commands from Gemini CLI. Although both tools include the word Gemini and can be invoked from a terminal, gcloud gemini is an administrative command group for interacting with Google Cloud resources and operations. It is not the local, agentic coding interface intended to inspect a repository, edit source files, run tests, or execute development tools on the engineer’s workstation. The question also states that the engineer does not need to manage Gemini Cloud Assist resources, which further eliminates this option.

**B is incorrect** because Gemini Cloud Assist investigations are intended for assisted root-cause analysis of operational problems in distributed cloud applications and infrastructure. Investigations can correlate information such as logs, metrics, alerts, configurations, and recent changes to help diagnose incidents affecting deployed Google Cloud workloads. They are appropriate when an operations team needs to investigate a production failure across resources and services. They are not primarily designed to work as a local coding agent that navigates repository files, edits Go or Python code, invokes local test commands, and iteratively fixes failing unit tests.

**C is correct** because Gemini CLI is an open-source AI agent that provides access to Gemini directly from a terminal. It can inspect files in the current repository, read and write source code, search the project, execute approved terminal commands, and use built-in or externally configured tools. Its agentic workflow allows it to reason about a task, select appropriate tools, run tests, examine failures, modify code, and repeat the process until the issue is resolved or additional developer input is required. This makes Gemini CLI suitable for a repository containing application code, unit tests, and Terraform modules. It also supports tool approval and configurable execution controls, allowing the developer to review sensitive actions instead of granting unrestricted command execution. The standalone gemini command launches Gemini CLI, whereas gcloud gemini manages Google Cloud resources associated with Gemini products.

**D is incorrect** because Application Design Center is used by platform and development teams to design, standardize, share, and deploy application architectures on Google Cloud. It can represent cloud components and their relationships, create reusable application templates, and generate or manage Terraform-based application deployments. It is useful for self-service infrastructure delivery and centralized architectural governance, but it is not a terminal-based coding agent. It would not be the appropriate first tool for inspecting local application files, executing unit tests, interpreting test failures, and editing source code to correct those failures.

**Reference links**

- [docs.cloud.google.com/gemini/docs/codeassist/gemini-cli](https://docs.cloud.google.com/gemini/docs/codeassist/gemini-cli)
- [docs.cloud.google.com/sdk/gcloud/reference/gemini](https://docs.cloud.google.com/sdk/gcloud/reference/gemini)
- [docs.cloud.google.com/cloud-assist/investigations](https://docs.cloud.google.com/cloud-assist/investigations)

**Related notes:** [Gemini CLI](../08-iac-platform-ai/products/gemini-cli.md)

</details>

[Back to index](#index)

---

### Q49

Choose 2.

> BrightTrail Media has validated Terraform modules for VPC networking, Cloud Run services, and Cloud SQL databases. The cloud enablement team wants to use these existing modules as building blocks in a visual design environment and offer product teams a deployable web application architecture through self-service. The approved Terraform implementations must be reused rather than recreated, and the completed architecture must be available as a repeatable template. Which two actions should the cloud enablement team take? (Choose two.)  

- **A.** Import the validated Terraform modules as components into Application Design Center.
- **B.** Turn on Gemini Cloud Assist investigations in every product team’s project.
- **C.** Create an Application Design Center template that connects the imported components, and share the template with the product teams.
- **D.** Place separate copies of the Terraform modules in every engineer’s Cloud Shell home directory.
- **E.** Grant product teams the Organization Administrator role so they can create any components that are unavailable.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A, C

**Explanation**

**A is correct** because Application Design Center supports imported components based on an organization’s existing Terraform modules. When the platform team imports a Terraform module, Application Design Center creates a corresponding component template that can be used as a building block in an application design. This enables the team to retain and reuse the networking, Cloud Run, and Cloud SQL implementations that have already passed its review process instead of rebuilding equivalent components manually. The imported components can expose the module’s configurable inputs while preserving the approved infrastructure logic behind them. This action addresses the requirement to incorporate the existing Terraform modules into a visual application-design workflow.

**B is incorrect** because Gemini Cloud Assist investigations are intended for operational troubleshooting and assisted root-cause analysis. They help teams correlate signals such as logs, metrics, alerts, resource configurations, and recent changes when diagnosing problems in deployed applications. Enabling investigations does not convert existing Terraform modules into visual components, assemble those components into an architecture, or publish a reusable deployment pattern. Although investigations may be useful after an application is running, they do not satisfy the platform engineering requirement described in the question.

**C is correct** because an Application Design Center application template packages components, their configuration, and their connections into a reusable architecture. After importing the approved networking, Cloud Run, and Cloud SQL modules as components, the platform team can place them on the design canvas and define the relationships required for the three-tier application. For example, it can connect the Cloud Run workload to the network and Cloud SQL components and establish the intended deployment configuration. The team can then share the completed template directly with members of the relevant space or publish it to a catalog for broader reuse across spaces. Development teams can create and deploy applications from the template without designing the architecture from the beginning, providing the required governed self-service experience.

**D is incorrect** because copying Terraform modules into individual Cloud Shell home directories creates unmanaged and disconnected copies. Developers could modify their copies, use different versions, or fail to receive later updates from the platform team. Cloud Shell home directories are personal development environments and do not provide a visual design workflow, a centrally managed component catalog, or a reusable application template. This approach would weaken governance and increase configuration drift instead of preserving a single approved implementation.

**E is incorrect** because the Organization Administrator role grants highly privileged control over organization-level resources and should not be assigned merely to let developers create application components. This would violate the principle of least privilege and introduce substantial security and governance risks. Developers do not need organization-wide administrative access to consume templates shared through Application Design Center. The platform team should create and govern the approved components and templates, while development teams receive only the permissions needed to configure and deploy applications from those templates.

**Reference links**

- [docs.cloud.google.com/application-design-center/docs/import-components](https://docs.cloud.google.com/application-design-center/docs/import-components)
- [docs.cloud.google.com/application-design-center/docs/design-application-templates](https://docs.cloud.google.com/application-design-center/docs/design-application-templates)
- [docs.cloud.google.com/application-design-center/docs/manage-catalogs](https://docs.cloud.google.com/application-design-center/docs/manage-catalogs)

**Related notes:** [Application Design Center](../08-iac-platform-ai/products/application-design-center.md)

</details>

[Back to index](#index)

---

### Q50

> ClearRoute Insurance has finished testing an AI agent that helps employees summarize claims and recommend the next processing steps. The company now needs to run the agent in production on Google Cloud. The selected service must deploy the agent, automatically scale its infrastructure, and provide operational management without requiring the engineering team to build and maintain a separate hosting control plane. The agent must also work with other capabilities in Gemini Enterprise Agent Platform. What should the company use?  

- **A.** Host the agent on a manually administered Compute Engine virtual machine that uses a startup script.
- **B.** Deploy the agent to Agent Runtime on Gemini Enterprise Agent Platform.
- **C.** Represent the agent architecture in Application Design Center without using a runtime service.
- **D.** Store the agent files in a Cloud Storage bucket configured for static website hosting.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because a Compute Engine instance can technically host custom agent code, but the engineering team would be responsible for designing and operating most of the production environment. The team would need to manage operating system updates, software dependencies, instance health, capacity planning, autoscaling, load balancing, deployment automation, security controls, logging, monitoring, and recovery procedures. A startup script can install software and launch a process when an instance starts, but it does not provide a complete managed agent runtime or remove the need to build a hosting control plane. This approach therefore creates unnecessary operational work and does not provide the closest integration with the agent-specific services in Gemini Enterprise Agent Platform.

**B is correct** because Agent Runtime is the managed production runtime in Gemini Enterprise Agent Platform for deploying, managing, and scaling AI agents. It handles the underlying runtime infrastructure so developers can concentrate on agent instructions, tools, orchestration, and business logic instead of implementing their own deployment and lifecycle-management platform. An agent can be deployed from supported development artifacts such as source files, an agent object, a Dockerfile, a container image, or a connected Git repository. Agent Runtime also integrates with the broader platform’s agent services, including capabilities for sessions, memory, identity, governance, observability, and secure communication. It directly satisfies the requirements for a Google Cloud-hosted, production-ready runtime with managed scaling and operations. Agent Runtime is the current name for the capability previously called Agent Engine.

**C is incorrect** because Application Design Center is an application architecture design and self-service deployment capability rather than an execution environment for AI agents. A team can use it to visually model cloud architectures, connect infrastructure components, and publish reusable application templates. However, a design by itself does not execute agent logic, process requests, scale agent workers, maintain agent sessions, or manage the operational lifecycle of a running agent. The team would still need to select and configure a runtime service. Application Design Center could potentially describe supporting infrastructure, but it cannot replace Agent Runtime for this requirement.

**D is incorrect** because Cloud Storage static website hosting serves static files such as HTML, CSS, JavaScript, and images. It does not execute server-side application code or maintain a continuously running AI agent process. A production agent needs a runtime capable of receiving requests, invoking models and tools, maintaining relevant state, applying identities and permissions, and scaling based on workload. Placing source files or other agent artifacts in a bucket would only store or distribute those files; it would not deploy them as an operational agent. Cloud Storage can be used as supporting storage in an agent solution, but it is not a substitute for Agent Runtime.

**Reference links**

- [docs.cloud.google.com/gemini-enterprise-agent-platform/build/runtime](https://docs.cloud.google.com/gemini-enterprise-agent-platform/build/runtime)
- [docs.cloud.google.com/gemini-enterprise-agent-platform/scale/runtime/deploy-an-agent](https://docs.cloud.google.com/gemini-enterprise-agent-platform/scale/runtime/deploy-an-agent)
- [docs.cloud.google.com/gemini-enterprise-agent-platform/overview](https://docs.cloud.google.com/gemini-enterprise-agent-platform/overview)

**Related notes:** [Gemini Enterprise Agent Platform: Agent Runtime](../08-iac-platform-ai/products/agent-runtime.md)

</details>

[Back to index](#index)

---
