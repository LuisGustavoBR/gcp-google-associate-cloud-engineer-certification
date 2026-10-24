# Practice Exam 3

[Previous](exam-2.md) · [All exams](README.md) · [Next](exam-4.md)

50 questions in the original English. Open "Show answer" under each question to see the correct answer and the explanation.

## Index

| Q | Question |
|---|---|
| [Q1](#q1) | ParcelForge is deploying a three-tier logistics platform in a dedicated Google Cloud proje... |
| [Q2](#q2) | LedgerLeaf, a financial reporting platform, stores confidential transaction records in a B... |
| [Q3](#q3) | FinSight Retail operates several Google Cloud projects for its engineering, analytics, and... |
| [Q4](#q4) | TradePulse operates an on-premises PostgreSQL database that processes high-volume financia... |
| [Q5](#q5) | BrightPath Retail has adopted Google Cloud for its internal analytics platform. Only emplo... |
| [Q6](#q6) | Northstar Media has acquired three digital publishing companies: BrightLeaf, PixelPress, a... |
| [Q7](#q7) | EventSphere is deploying a public ticket-booking website on Compute Engine virtual machine... |
| [Q8](#q8) | Northstar Health is launching an employee scheduling portal behind an internal Application... |
| [Q9](#q9) | BrightCart, an online retail company, performs a monthly review of its Google Cloud projec... |
| [Q10](#q10) | NorthPeak Rentals operates an internal application that tracks equipment checkouts, custom... |
| [Q11](#q11) | NovaCart uses Google Workspace to manage employee accounts. The company expects its workfo... |
| [Q12](#q12) | StreamHive Media runs a video-processing application in a single-zone Google Kubernetes En... |
| [Q13](#q13) | OrbitLend, a digital lending website, stores customer applications in a Cloud SQL for Post... |
| [Q14](#q14) | StreamWave operates a media-processing platform with hundreds of containerized services in... |
| [Q15](#q15) | AeroVista Logistics uses several hundred service accounts for warehouse applications runni... |
| [Q16](#q16) | CedarPay uses a Cloud KMS symmetric encryption key as a customer-managed encryption key fo... |
| [Q17](#q17) | CareBridge Portal, a healthcare operations company, has created one stateless web applicat... |
| [Q18](#q18) | ParcelPilot runs a shipment-tracking API on Compute Engine VMs in a managed instance group... |
| [Q19](#q19) | BluePeak Robotics manages several Google Cloud projects for application development, testi... |
| [Q20](#q20) | BlueOrbit Travel operates a reservation platform on Google Cloud. During an incident, an e... |
| [Q21](#q21) | BrightFrame Studios stores completed animation render files on a local network-attached st... |
| [Q22](#q22) | StreamForge operates a live-event notification platform that provisions Google Cloud resou... |
| [Q23](#q23) | Northstar HR has built a containerized employee benefits portal that authenticated staff m... |
| [Q24](#q24) | BrightTrail Logistics runs a shipment-tracking service on a Compute Engine VM connected to... |
| [Q25](#q25) | PixelForge Media runs a single video-processing job on an on-premises server. The job take... |
| [Q26](#q26) | MealMetric, a food-delivery analytics company, stores order and customer activity data in ... |
| [Q27](#q27) | NovaCart operates a set of Compute Engine VMs that process customer orders. The security t... |
| [Q28](#q28) | DataBridge Logistics is developing an application that receives shipping files from 2,500 ... |
| [Q29](#q29) | PixelForge Media is launching a collaborative video-editing portal. The application uses a... |
| [Q30](#q30) | AsterPeak Logistics discovers that 11 external contractor accounts have IAM access to reso... |
| [Q31](#q31) | HarborCart operates an online grocery delivery platform and manages its Google Cloud resou... |
| [Q32](#q32) | Skyline Analytics needs to provision identical networking, Compute Engine, and Cloud Stora... |
| [Q33](#q33) | TicketNest, an event-booking platform, runs its web service on Cloud Run and connects to a... |
| [Q34](#q34) | BlueHarbor Analytics operates five isolated VPC networks in a single Google Cloud project.... |
| [Q35](#q35) | CloudVista Media operates its customer-facing platform in a dedicated Google Cloud product... |
| [Q36](#q36) | VaultBridge stores confidential legal documents in a private Cloud Storage bucket. Complia... |
| [Q37](#q37) | Northstar Retail is running its order-processing application on a Compute Engine VM named ... |
| [Q38](#q38) | GlobeCart operates an international online marketplace and plans to modernize three existi... |
| [Q39](#q39) | PulseCart, an online retail platform, stores application logs in Cloud Logging. Its analyt... |
| [Q40](#q40) | Northwind Health hosts a patient portal on a Compute Engine VM. A project administrator cr... |
| [Q41](#q41) | BrightCart operates order-processing applications on Compute Engine in a Google Cloud VPC ... |
| [Q42](#q42) | BrightPath Health runs patient-processing and analytics VMs in multiple Google Cloud proje... |
| [Q43](#q43) | SkyRoute Media stores uploaded video files in a Cloud Storage bucket located in its applic... |
| [Q44](#q44) | BrightCart Commerce runs its application servers on Compute Engine virtual machines in a c... |
| [Q45](#q45) | MercuryMart operates a retail analytics platform and needs to install a third-party applic... |
| [Q46](#q46) | TransitPulse, a city transport tracking company, has built a stateless application that de... |
| [Q47](#q47) | LedgerNest stores monthly compliance reports in Cloud Storage. Each report is uploaded onc... |
| [Q48](#q48) | BrightForge Labs gives each of its 12 application developers a separate Google Cloud proje... |
| [Q49](#q49) | Meridian BioLabs operates several Google Cloud projects that store regulated research data... |
| [Q50](#q50) | ParcelPilot, a package-delivery platform, runs its production workloads across several Goo... |

---

### Q1

> ParcelForge is deploying a three-tier logistics platform in a dedicated Google Cloud project. The platform requires more than 1,500 internal IP addresses and must be securely isolated. The frontend tier receives public requests, the processing tier accepts traffic only from the frontend tier, and the data tier accepts traffic only from the processing tier. ParcelForge wants to minimize networking cost, configuration complexity, and ongoing administration. What should it do?  

- **A.** Create a Shared VPC with a /23 address range, allocate a subnet to each tier, and use VPC firewall rules with network tags.
- **B.** Create one custom mode VPC, allocate a /16 private address space across three subnets, place each tier in its own subnet, and use VPC firewall rules with source IP ranges to control communication between the tiers.
- **C.** Create a separate custom mode VPC with a /16 address range for each tier, connect the networks with VPC Network Peering, and maintain firewall rules separately in every VPC.
- **D.** Create a separate /24 VPC for each tier, assign network tags to the instances, and implement firewall rules for communication between the networks.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because a /23 IPv4 range does not provide enough addresses for an application requiring more than 1,500 internal IP addresses. It contains only 512 total IPv4 addresses, and some addresses in each subnet are unavailable for resource assignment. Shared VPC is also primarily designed to let resources in multiple service projects use a centrally managed network in a host project. ParcelForge is deploying this application in one dedicated project, so introducing Shared VPC would add host-project configuration, IAM roles, and delegated network-administration responsibilities without providing a necessary benefit. Although separate subnets and network-tag-based firewall rules could provide logical segmentation, the address capacity and unnecessary Shared VPC administration make this option unsuitable.

**B is correct** because one custom mode VPC provides sufficient address-planning flexibility while keeping all three tiers in a single centrally managed network. A /16 allocation contains 65,536 total IPv4 addresses, providing ample capacity for more than 1,500 resources and future expansion. ParcelForge can divide that address space into appropriately sized, non-overlapping regional subnets for the frontend, processing, and data tiers. VPC firewall rules can then allow public traffic only to the frontend subnet, allow the processing tier to receive traffic only from the frontend subnet’s source range on required ports, and allow the data tier to receive traffic only from the processing subnet’s source range. Other ingress traffic can remain denied by the implied deny-ingress rule. This architecture provides logical tier isolation without requiring multiple VPC networks, peering connections, or duplicate firewall configurations, thereby minimizing cost, complexity, and administrative overhead.

**C is incorrect** because three separate VPC networks and VPC Network Peering connections are unnecessary for the required tier segmentation. Peering would provide private routing between the networks, but it would require administrators to create matching peering configurations, plan non-overlapping subnet ranges, and manage security rules independently in each VPC. VPC Network Peering exchanges routes but does not exchange VPC firewall rules or firewall policies, so ParcelForge would need to maintain coordinated rules on multiple networks. Peering is useful when independently administered networks require private connectivity, but it adds operational complexity compared with using subnets and firewall rules inside one custom mode VPC.

**D is incorrect** because three /24 ranges provide fewer than 768 total IPv4 addresses before Google Cloud’s reserved subnet addresses are considered, which is insufficient for more than 1,500 required IP addresses. Network tags can identify firewall-rule targets within a VPC, but tags do not automatically provide routing between separate VPC networks. ParcelForge would still need an additional connectivity mechanism, such as VPC Network Peering, Network Connectivity Center, or another networking solution. Operating several small VPC networks would also require separate routing, connectivity, and firewall administration, increasing complexity without improving the required three-tier isolation.

**Reference links**

- [docs.cloud.google.com/vpc/docs/vpc](https://docs.cloud.google.com/vpc/docs/vpc)
- [docs.cloud.google.com/vpc/docs/subnets](https://docs.cloud.google.com/vpc/docs/subnets)
- [docs.cloud.google.com/firewall/docs/firewalls](https://docs.cloud.google.com/firewall/docs/firewalls)

**Related notes:** [VPC, Subnets, and IPs](../06-networking/products/vpc-subnets-and-ips.md)

</details>

[Back to index](#index)

---

### Q2

> LedgerLeaf, a financial reporting platform, stores confidential transaction records in a BigQuery table. After a suspected data exposure, a security analyst must identify the authenticated identity that queried or otherwise read the table’s rows. The analyst has the roles/logging.viewer role but cannot access the relevant entries stored in the project’s _Default log bucket. Which change should the security team make?  

- **A.** Ensure that the required BigQuery Data Access audit logs are generated, and grant the analyst the roles/logging.privateLogViewer role.
- **B.** Enable only VPC Flow Logs for the VPC network associated with the project.
- **C.** Grant the analyst the Compute Instance Admin role.
- **D.** Investigate only Admin Activity audit logs because they automatically contain every BigQuery table-read operation.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because reading rows from a BigQuery table is a data-access operation rather than merely an administrative configuration change. BigQuery Data Access audit logs can record events such as TableDataRead and query operations that require the bigquery.tables.getData permission. These entries can include the affected resource, operation details, timestamp, and authenticated principal information needed to determine who accessed the data. BigQuery Data Access audit logging is generally enabled by default, although the team should still verify that the relevant operation is covered, that the logs have not been excluded or aged out, and that any related BigQuery service requiring explicit configuration is enabled. The immediate access problem is that roles/logging.viewer does not permit a user to read Data Access audit logs in the _Default bucket. Granting roles/logging.privateLogViewer provides read-only access to these private log entries while avoiding unnecessary administrative permissions. After receiving this role at the appropriate project, folder, organization, or log-view level, the analyst can query for the bigquery.googleapis.com service and data_access log stream and inspect the principal identity and table-read details.

**B is incorrect** because VPC Flow Logs record network-flow metadata such as source and destination addresses, ports, protocols, traffic volume, and connection outcomes. They do not provide BigQuery-level audit information about which authenticated user, service account, or workload queried a table or read specific table data. BigQuery is a managed service, and its logical data-access activity must be investigated through BigQuery Data Access audit logs rather than through network-flow telemetry. Enabling VPC Flow Logs might assist with a separate network investigation, but it does not resolve the analyst’s inability to view private audit logs.

**C is incorrect** because the Compute Instance Admin role grants broad permissions for managing Compute Engine resources and has no appropriate relationship to viewing BigQuery Data Access audit logs. It would not provide the specific Cloud Logging permission required to access private log entries in the _Default bucket. Granting this role would also violate the principle of least privilege by giving the analyst extensive permissions to create, modify, start, stop, or delete virtual machine resources that are unrelated to the investigation. The purpose-built roles/logging.privateLogViewer role is the appropriate access grant.

**D is incorrect** because Admin Activity audit logs primarily record administrative write operations, such as creating, updating, or deleting datasets, tables, and IAM policies. They do not serve as the complete record of users reading table rows. BigQuery operations requiring DATA_READ permissions generate Data Access audit logs, and a TableDataRead event can indicate that a consumer accessed table data. Admin Activity logs are always written and can be viewed with roles/logging.viewer, but relying on them alone would omit the evidence required to identify the principal responsible for the data read.

**Reference links**

- [docs.cloud.google.com/bigquery/docs/reference/auditlogs](https://docs.cloud.google.com/bigquery/docs/reference/auditlogs)
- [docs.cloud.google.com/logging/docs/access-control](https://docs.cloud.google.com/logging/docs/access-control)
- [docs.cloud.google.com/logging/docs/audit/configure-data-access](https://docs.cloud.google.com/logging/docs/audit/configure-data-access)

**Related notes:** [Cloud Audit Logs](../02-identity-security/products/cloud-audit-logs.md)

</details>

[Back to index](#index)

---

### Q3

> FinSight Retail operates several Google Cloud projects for its engineering, analytics, and marketing departments. Each department must receive notifications when its spending reaches defined limits and must be able to build custom dashboards from detailed cost and usage data. FinSight Retail wants to use managed Google Cloud capabilities and avoid maintaining custom billing infrastructure. What should it do?  

- **A.** Run Grafana on Compute Engine, build a dashboard for every department by querying the Cloud Billing API, and have each department configure cost alerts in Cloud Monitoring.
- **B.** Configure spending threshold notifications for each department, develop a shell script that retrieves costs from the Cloud Billing API and writes them to BigQuery, and grant the departments access to the dataset.
- **C.** Run Grafana on Compute Engine, create department dashboards from the Cloud Billing Budget API, and configure spending alerts directly in Grafana.
- **D.** Create Cloud Billing budgets and threshold alerts for each department, enable Cloud Billing data export to BigQuery, and grant department members appropriate access to the billing dataset.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because deploying Grafana on Compute Engine introduces unnecessary infrastructure and administrative work. The company would need to provision, secure, patch, monitor, back up, and scale the Grafana deployment and its underlying virtual machines. In addition, the Cloud Billing API is primarily used to manage billing accounts, project billing associations, services, SKUs, and related billing configuration; it is not the recommended source for exporting detailed historical usage and cost records for analytics. Cloud Monitoring alerts are also not the standard managed mechanism for notifying teams when spending crosses budget thresholds. Cloud Billing budgets and alerts provide this capability directly, while Cloud Billing export automatically sends detailed cost data to BigQuery.

**B is incorrect** because the custom shell script creates avoidable engineering and operational overhead. The company would need to schedule the script, handle authentication, manage retries, account for API errors, prevent duplicate records, maintain the destination schema, and update the code when requirements change. The Cloud Billing API is not a replacement for the managed Cloud Billing data export, which automatically writes billing data to BigQuery throughout the day. Although configuring budget alerts and granting controlled BigQuery access are appropriate actions, creating a custom export process violates the requirement to minimize engineering costs.

**C is incorrect** because the Cloud Billing Budget API is used to create and manage budgets, threshold rules, and notification settings; it does not provide the detailed resource-level usage and cost records needed for comprehensive dashboards. Grafana would also require the company to operate additional Compute Engine infrastructure and create a custom data integration. Configuring alerts in Grafana would duplicate the built-in capabilities of Cloud Billing budgets and alerts. This approach is therefore more complex and less aligned with Google-recommended managed services.

**D is correct** because Cloud Billing budgets can be scoped by billing account, project, service, label, or other supported dimensions and can send notifications when actual or forecasted spending crosses configured percentage thresholds. Separate budgets can be created for different teams according to how their projects or resources are organized. Cloud Billing data export automatically sends standard or detailed usage cost data to a BigQuery dataset, where team members can run queries and create dashboards using tools such as Looker Studio or another supported business intelligence platform. Access can be granted at the dataset, table, or authorized-view level so that each team receives only the billing information it is permitted to see. This solution uses managed Google Cloud capabilities, supports detailed analysis, avoids custom extraction scripts and self-managed Grafana infrastructure, and minimizes ongoing engineering costs.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/budgets](https://docs.cloud.google.com/billing/docs/how-to/budgets)
- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery)
- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-tables/detailed-usage](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-tables/detailed-usage)

</details>

[Back to index](#index)

---

### Q4

> TradePulse operates an on-premises PostgreSQL database that processes high-volume financial transactions and complex analytical queries. The company wants to move the database to a fully managed Google Cloud service that provides high performance for both workload types, synchronously protects data across zones, and automatically manages an optimized, scalable storage layer. What should TradePulse do?  

- **A.** Migrate the PostgreSQL database to Cloud SQL for PostgreSQL by using Database Migration Service.
- **B.** Create a Cloud SQL for PostgreSQL instance, install the psql client on a Compute Engine VM, and manually transfer the database.
- **C.** Migrate the PostgreSQL database to AlloyDB for PostgreSQL by using Database Migration Service.
- **D.** Create a Compute Engine VM, install PostgreSQL, configure its storage and replication, and manually migrate the database.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Cloud SQL for PostgreSQL is a fully managed relational database service and Database Migration Service can migrate an on-premises PostgreSQL database to it. A highly available Cloud SQL instance can also synchronously replicate writes to persistent disks in two zones. However, Cloud SQL is not the best match for the complete set of requirements. The scenario emphasizes demanding transactional and analytical workloads together with an optimized storage layer. AlloyDB for PostgreSQL is specifically designed for demanding enterprise PostgreSQL workloads and uses a cloud-native, distributed storage engine that is separate from compute, persists data across multiple zones, scales automatically, and includes performance features such as intelligent caching, adaptive database management, read pools, and a columnar engine for accelerating analytical queries. Therefore, Cloud SQL is a valid managed PostgreSQL option but is not the most suitable answer for these stated performance and storage requirements.

**B is incorrect** because psql is a PostgreSQL command-line client used to connect to a PostgreSQL server and run SQL commands. Installing it on a Compute Engine instance does not provide a managed migration workflow, continuous replication, migration monitoring, or automated cutover. A manual migration performed through psql could require database dumps, data restoration, custom scripts, outage planning, error handling, and validation. This option also selects Cloud SQL rather than AlloyDB, so it does not provide the storage architecture and combined transactional and analytical optimization required by TradePulse. Database Migration Service is the appropriate managed migration tool because it can coordinate the initial data movement and ongoing replication before the destination is promoted.

**C is correct** because AlloyDB for PostgreSQL is a fully managed, PostgreSQL-compatible database service designed for demanding transactional and analytical workloads. AlloyDB separates compute from its cloud-native distributed storage layer, allowing both layers to scale and operate more efficiently. Its storage engine automatically grows as the database expands and persists data across multiple availability zones. A highly available AlloyDB primary instance uses redundant nodes in different zones and supports automatic failover, while the storage layer protects data independently of the database compute nodes. AlloyDB also provides an optimized row-based engine for transactional processing and a columnar engine that can accelerate analytical queries without requiring a separate analytical database. Database Migration Service supports migrations from on-premises PostgreSQL to AlloyDB, manages the initial database snapshot and ongoing replication, provides migration status information, and supports a controlled promotion process after replication delay reaches zero. This combination satisfies the managed-service, performance, synchronous data protection, optimized storage, and migration requirements.

**D is incorrect** because PostgreSQL installed on Compute Engine is self-managed rather than a fully managed database service. TradePulse would be responsible for provisioning and securing the VM, installing and upgrading PostgreSQL, applying operating system and database patches, configuring backups, monitoring performance, managing storage capacity, implementing replication, testing failover, and recovering from failures. Standard Compute Engine storage also does not automatically provide AlloyDB’s database-aware, distributed, disaggregated storage architecture or its built-in analytical acceleration. Although a self-managed deployment offers extensive control, it creates substantial operational overhead and does not satisfy the requirement to use a fully managed Google Cloud database service.

**Reference links**

- [docs.cloud.google.com/alloydb/docs/overview](https://docs.cloud.google.com/alloydb/docs/overview)
- [docs.cloud.google.com/database-migration/docs/postgresql-to-alloydb/quickstart](https://docs.cloud.google.com/database-migration/docs/postgresql-to-alloydb/quickstart)
- [docs.cloud.google.com/alloydb/docs/migrate-with-dms](https://docs.cloud.google.com/alloydb/docs/migrate-with-dms)

**Related notes:** [AlloyDB](../05-storage-databases-data/products/alloydb.md) · [Database Migration Service](../05-storage-databases-data/products/database-migration-service.md)

</details>

[Back to index](#index)

---

### Q5

> BrightPath Retail has adopted Google Cloud for its internal analytics platform. Only employees in the Platform Engineering and Business Intelligence departments should receive Google Cloud identities. The company stores all employee accounts in a central LDAP directory, and each department has a separate organizational unit. Identity provisioning must automatically reflect new hires, departures, and transfers between departments. What should BrightPath Retail do?  

- **A.** -Build a containerized service that queries the Platform Engineering and Business Intelligence OUs in LDAP and uses the Admin SDK Directory API to manage Cloud Identity accounts.  
  -Run the service periodically as a Cloud Run job.
- **B.** -Build a containerized service that queries the selected LDAP OUs and uses the Identity Platform Admin SDK to synchronize those employees as Identity Platform users.  
  -Run the service periodically as a Cloud Run job.
- **C.** -Export the employees in the selected LDAP OUs to a CSV file and import the file into Cloud Identity.  
  -Ask the Human Resources team to repeat the export and import whenever employee records change.
- **D.** Configure Google Cloud Directory Sync to synchronize users from the selected LDAP OUs to Cloud Identity, and schedule regular synchronization runs.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because the Admin SDK Directory API can create, update, suspend, and manage Cloud Identity or Google Workspace user accounts, so a custom solution could technically be developed. However, the company would have to build and maintain all synchronization logic, including detecting new users, identifying changed attributes, handling department transfers, suspending or deleting departed users, preventing duplicate accounts, managing API errors, and reconciling differences between LDAP and Cloud Identity. It would also need to secure credentials, implement logging and retries, and schedule the Cloud Run job through an appropriate scheduling mechanism. Google Cloud Directory Sync already provides these capabilities for LDAP-based directories, making a custom application unnecessarily complex and operationally burdensome.

**B is incorrect** because Identity Platform and Cloud Identity serve different purposes. Identity Platform provides authentication and user management for customers or other users of web and mobile applications. Its Admin SDK manages application identities inside an Identity Platform-enabled Google Cloud project. These application users do not become organizational Cloud Identity accounts and cannot be used as the company’s centrally managed workforce identities for Google Cloud access. The requirement is to provision employee identities that can be referenced in Google Cloud IAM policies, so the users must be managed through Cloud Identity or Google Workspace rather than Identity Platform.

**C is incorrect** because a CSV-based import is a manual, point-in-time provisioning method. It does not continuously reconcile Cloud Identity with the LDAP directory. New employees might not receive accounts promptly, departed employees could retain access until the next manual import, and employees transferring into or out of the selected departments might be handled incorrectly. Assigning the process to Human Resources also introduces delays and human error. The requirement explicitly calls for identities to update automatically as employees join, leave, or change departments, so a repeated manual import does not satisfy the lifecycle-management requirement.

**D is correct** because Google Cloud Directory Sync is designed to synchronize users, groups, organizational information, and other directory data from an LDAP-compatible directory into Cloud Identity or Google Workspace. BrightPath Retail can configure LDAP search bases, queries, and exclusion rules so that only users in the Platform Engineering and Business Intelligence OUs are included. During scheduled synchronization runs, Google Cloud Directory Sync compares the source LDAP directory with Cloud Identity and applies the configured changes, including creating accounts for newly eligible employees, updating existing accounts, and suspending or removing access for users who leave the company or move outside the synchronized OUs. LDAP remains the authoritative identity source, while scheduled synchronization provides automatic and consistent employee lifecycle management without requiring a custom application.

**Reference links**

- [cloud.google.com/identity/docs/how-to/create-cloud-identity-user-accounts](https://cloud.google.com/identity/docs/how-to/create-cloud-identity-user-accounts)
- [cloud.google.com/architecture/identity/federating-gcp-with-active-directory-introduction](https://cloud.google.com/architecture/identity/federating-gcp-with-active-directory-introduction)
- [cloud.google.com/identity-platform/docs/admin/manage-users](https://cloud.google.com/identity-platform/docs/admin/manage-users)

**Related notes:** [Cloud Identity and Google Cloud Directory Sync](../02-identity-security/products/cloud-identity-and-google-cloud-directory-sync.md)

</details>

[Back to index](#index)

---

### Q6

> Northstar Media has acquired three digital publishing companies: BrightLeaf, PixelPress, and UrbanScope. Northstar wants to apply common IAM and organization policies to all Google Cloud resources through one resource hierarchy. Each acquired company maintains an independent cost center and must receive a separate monthly invoice for its Google Cloud usage. What should Northstar Media do?  

- **A.** Create one Google Cloud organization with a folder for each acquired company, link all projects to one Cloud Billing account, and separate the companies’ costs by using detailed billing export data.
- **B.** Create one Google Cloud organization with a folder for each acquired company, and link each company’s projects to a separate Cloud Billing account.
- **C.** Create a separate Google Cloud organization and a separate Cloud Billing account for each acquired company.
- **D.** Create a separate Google Cloud organization for each acquired company, link all projects to one Cloud Billing account, and divide the charges by using detailed billing export data.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because using one Google Cloud organization with separate folders provides the required centralized resource management, but sharing one Cloud Billing account does not satisfy the separate-invoice requirement. Detailed billing export data can be sent to BigQuery and used to analyze or allocate costs by project, folder, label, or other attributes, but this process only provides internal cost attribution. It does not cause Google Cloud to generate a separate invoice for each startup. For an invoiced billing arrangement, charges from projects linked to the same Cloud Billing account normally appear on the invoice associated with that billing account.

**B is correct** because one Google Cloud organization provides a single administrative boundary in which Northstar Media can centrally manage IAM policies, organization policies, folders, projects, and other resources. A separate folder for each acquired company creates a logical structure for delegating administration and grouping that company’s projects. Each company’s projects should then be linked to its own Cloud Billing account. Because invoicing is generally performed at the Cloud Billing account level, using three separate invoiced Cloud Billing accounts allows each acquired company’s consumption to be represented on a separate monthly invoice while all resources remain centrally governed under the same organization. Cloud Billing accounts are linked to projects rather than directly to folders, so Northstar must ensure that every project within a company’s folder is linked to that company’s designated billing account.

**C is incorrect** because separate Cloud Billing accounts would support separate invoices, but creating a different Google Cloud organization for each acquired company conflicts with the requirement to centrally manage all resources under one organization. An organization is the root of a Google Cloud resource hierarchy and establishes the primary administrative and policy boundary. Multiple organizations would require Northstar to manage IAM, organization policies, security controls, and governance separately across independent hierarchies. Separate organizations are unnecessary because multiple Cloud Billing accounts can be used with projects that belong to the same Google Cloud organization.

**D is incorrect** because it fails both major requirements. Creating separate organizations prevents the acquired companies’ resources from being governed through one centralized resource hierarchy. In addition, linking all projects to one Cloud Billing account generally produces billing documents for that shared account rather than a distinct monthly invoice for each acquired company. Detailed billing exports can help Northstar allocate charges internally, but they do not replace separate Cloud Billing accounts when separate Google-issued invoices are required.

**Reference links**

- [docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy](https://docs.cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)
- [docs.cloud.google.com/billing/docs/concepts](https://docs.cloud.google.com/billing/docs/concepts)
- [docs.cloud.google.com/billing/docs/how-to/read-invoice](https://docs.cloud.google.com/billing/docs/how-to/read-invoice)

</details>

[Back to index](#index)

---

### Q7

> EventSphere is deploying a public ticket-booking website on Compute Engine virtual machines in a managed instance group. The platform team wants to provide encrypted client connections, distribute HTTP and HTTPS requests across healthy instances, and make the website publicly accessible by using its domain name. Which configuration should the team use?  

- **A.** Configure a global external proxy Network Load Balancer with a target SSL proxy for the managed instance group, and create an A record in a Cloud DNS private zone that points to the load balancer’s IP address.
- **B.** Configure a global external proxy Network Load Balancer with a target SSL proxy for the managed instance group, and create a CNAME record in a Cloud DNS public zone that contains the load balancer’s IP address.
- **C.** Configure a global external Application Load Balancer for the managed instance group, and create a CNAME record in a Cloud DNS private zone that contains the load balancer’s IP address.
- **D.** Configure a global external Application Load Balancer for the managed instance group, and create an A record in a Cloud DNS public zone that points to the load balancer’s IP address.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a global external proxy Network Load Balancer with a target SSL proxy operates primarily at Layer 4 and is intended for encrypted TCP workloads rather than application-aware HTTP and HTTPS traffic management. It does not provide the URL maps, host-based routing, path-based routing, HTTP redirects, or other Layer 7 capabilities available with an Application Load Balancer. More importantly, a Cloud DNS private zone is visible only to authorized Virtual Private Cloud networks and associated private environments. Internet users cannot resolve records that exist exclusively in a private zone. Although an A record can correctly map a hostname to an IPv4 address, placing that record in a private zone would prevent public users from resolving the website’s domain name.

**B is incorrect** because a global external proxy Network Load Balancer with a target SSL proxy is not the Google-recommended load-balancing choice for a conventional HTTP and HTTPS web application when an Application Load Balancer can provide Layer 7 request processing, TLS termination, health-based traffic distribution, and application-aware routing. Additionally, a CNAME record cannot contain an IPv4 address as its target. A CNAME record creates an alias from one DNS hostname to another DNS hostname. When the load balancer provides an IPv4 address, the appropriate DNS record is an A record. Although using a public DNS zone is appropriate for an internet-facing website, the incorrect load-balancer type and invalid use of a CNAME record make this option unsuitable.

**C is incorrect** because a global external Application Load Balancer is the appropriate type of load balancer for a public HTTP and HTTPS web application. It can terminate TLS connections, distribute requests across healthy instances in a managed instance group, use health checks, and support host-based and path-based routing. However, the DNS configuration is incorrect in two ways. First, a CNAME record must refer to another hostname and cannot directly contain the load balancer’s IPv4 address. Second, a private DNS zone is intended for private name resolution within authorized VPC networks, not for a public website that internet users must access. Therefore, external users would not be able to resolve the application’s domain through the private zone.

**D is correct** because a global external Application Load Balancer is designed for internet-facing HTTP and HTTPS applications. It provides a globally accessible frontend, TLS termination, health checks, and Layer 7 request distribution across healthy Compute Engine instances in the managed instance group. The load balancer can continue directing requests to available instances when an individual VM becomes unhealthy, supporting the application’s availability requirements. For stronger availability, the managed instance group can also be regional or the load balancer can use backends in multiple regions. A Cloud DNS public zone makes the application’s DNS record resolvable from the internet. Because the load balancer exposes an IPv4 address, an A record correctly maps the application’s hostname to that address. This combination provides the appropriate secure, highly available, and publicly accessible architecture for the web application.

**Reference links**

- [docs.cloud.google.com/load-balancing/docs/https](https://docs.cloud.google.com/load-balancing/docs/https)
- [docs.cloud.google.com/load-balancing/docs/https/setup-global-ext-https-compute](https://docs.cloud.google.com/load-balancing/docs/https/setup-global-ext-https-compute)
- [docs.cloud.google.com/dns/docs/set-up-dns-records-domain-name](https://docs.cloud.google.com/dns/docs/set-up-dns-records-domain-name)

**Related notes:** [Cloud DNS](../06-networking/products/cloud-dns.md)

</details>

[Back to index](#index)

---

### Q8

> Northstar Health is launching an employee scheduling portal behind an internal Application Load Balancer. The portal must be reachable from resources in its VPC network and from its on-premises offices by using the domain name staff.northstar.internal. The domain name must not be resolvable from the public internet. The on-premises network connects to Google Cloud through Cloud VPN, and an inbound DNS server policy is already configured. Northstar Health wants to provide name resolution with minimal administrative effort. What should it do?  

- **A.** Add an A record to the on-premises DNS server that maps staff.northstar.internal to the internal Application Load Balancer’s IP address.
- **B.** Create a Cloud DNS managed private zone, authorize the VPC network to query the zone, and create an A record that maps staff.northstar.internal to the internal Application Load Balancer’s IP address.
- **C.** Create a Cloud DNS managed public zone and create an A record that maps staff.northstar.internal to the internal Application Load Balancer’s IP address.
- **D.** Modify the HOSTS file on every employee workstation to map staff.northstar.internal to the internal Application Load Balancer’s IP address.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because creating the record only on the on-premises DNS server directly provides name resolution for on-premises clients, but it does not automatically make the record resolvable by resources in the Google Cloud VPC network. Additional Cloud DNS forwarding configuration would be required so that VPC clients could send queries for the domain to the on-premises DNS server. This introduces another DNS dependency and increases administrative overhead. It also makes the on-premises DNS infrastructure authoritative for a name representing a Google Cloud-hosted resource. Because the application and internal Application Load Balancer are located in Google Cloud, storing the record in a Cloud DNS private zone provides a simpler, centrally managed design for both environments.

**B is correct** because a Cloud DNS managed private zone makes its records available only to the VPC networks authorized to use the zone. The A record can map the private application domain directly to the internal IP address of the internal Application Load Balancer. Resources in the authorized VPC network can resolve the record through Cloud DNS without exposing it publicly. The configured inbound DNS server policy provides inbound forwarding addresses that on-premises DNS servers can query across Cloud VPN. Consequently, on-premises DNS servers can forward requests for the private domain to Cloud DNS, allowing on-premises clients to resolve the same record. This creates one authoritative DNS record for both environments, prevents public DNS resolution, and requires less administration than maintaining duplicate records or custom forwarding designs.

**C is incorrect** because records in a Cloud DNS public zone are published through publicly accessible authoritative DNS servers. Even when the A record points to a private IP address that cannot normally be reached from the public internet, the domain name and its private IP address would still be publicly resolvable. This violates the requirement that the name must not be resolvable from the public internet. Publishing internal IP addresses in public DNS can also disclose information about the organization’s internal addressing scheme. A managed private zone is specifically intended for private names that should be visible only from authorized VPC networks and connected environments using DNS forwarding.

**D is incorrect** because HOSTS file entries must be created and maintained independently on every workstation. This approach does not provide centralized DNS management, does not automatically cover servers or other resources in the VPC network, and becomes difficult to manage as the number of users and devices grows. Any change to the load balancer’s IP address or application domain would require updating every affected workstation. Devices that do not receive the update could retain stale mappings, creating inconsistent application access. A Cloud DNS private zone provides centralized resolution and avoids manual endpoint configuration.

**Reference links**

- [docs.cloud.google.com/dns/docs/zones/zones-overview](https://docs.cloud.google.com/dns/docs/zones/zones-overview)
- [docs.cloud.google.com/dns/docs/server-policies-overview](https://docs.cloud.google.com/dns/docs/server-policies-overview)
- [docs.cloud.google.com/dns/docs/best-practices](https://docs.cloud.google.com/dns/docs/best-practices)

**Related notes:** [Cloud DNS](../06-networking/products/cloud-dns.md)

</details>

[Back to index](#index)

---

### Q9

> BrightCart, an online retail company, performs a monthly review of its Google Cloud project. The security team needs to identify which users, groups, and service accounts have permissions that allow them to view data stored in project resources. What should the team do?  

- **A.** Enable Cloud Audit Logs for every API associated with data storage.
- **B.** Review IAM role assignments and the permissions included in roles that provide data access.
- **C.** Review the Identity-Aware Proxy configuration for every resource in the project.
- **D.** Create a Sensitive Data Protection inspection job.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Cloud Audit Logs record activities performed within Google Cloud resources, such as administrative changes and data-access events. Data Access audit logs can help determine which principal previously accessed particular data, when the access occurred, and what operation was performed. However, audit logs do not provide the most direct view of all users, groups, and service accounts that currently have permission to access data. A principal might possess data-viewing permissions without having generated any recent audit log entries. Therefore, enabling Cloud Audit Logs is valuable for monitoring and investigating actual access, but it does not replace reviewing the project’s current IAM policies and role permissions.

**B is correct** because Identity and Access Management controls which principals can access Google Cloud resources and what actions they can perform. The team should review the project’s IAM allow policies to identify the users, groups, service accounts, and other principals that have been assigned roles. It should then examine the permissions contained in those roles to determine whether they permit reading or viewing data in services such as Cloud Storage, BigQuery, Firestore, or other storage systems. The review must include predefined roles, basic roles, custom roles, inherited access from folders or the organization, and access granted through group membership. This provides the clearest assessment of who is currently authorized to view the project’s stored data.

**C is incorrect** because Identity-Aware Proxy controls access to supported web applications and resources, such as applications running behind an external Application Load Balancer. It can require authenticated and authorized access before a user reaches an application. However, it does not provide a complete inventory of permissions for data stored across a Google Cloud project. Data could be accessed directly through service APIs, client libraries, command-line tools, or service accounts without passing through Identity-Aware Proxy. Reviewing its configuration would therefore cover only resources protected by Identity-Aware Proxy, not all project data.

**D is incorrect** because Sensitive Data Protection is used to discover, inspect, classify, and de-identify sensitive information. An inspection job can scan data in services such as Cloud Storage and BigQuery to identify information types including personal, financial, or credential-related data. It analyzes the contents of stored data rather than determining which principals have permission to access that data. Consequently, it can help the company understand what sensitive information it stores, but it cannot provide the required access-control review.

**Reference links**

- [docs.cloud.google.com/iam/docs/overview](https://docs.cloud.google.com/iam/docs/overview)
- [docs.cloud.google.com/iam/docs/roles-overview](https://docs.cloud.google.com/iam/docs/roles-overview)
- [docs.cloud.google.com/logging/docs/audit](https://docs.cloud.google.com/logging/docs/audit)

</details>

[Back to index](#index)

---

### Q10

> NorthPeak Rentals operates an internal application that tracks equipment checkouts, customer deposits, inventory availability, and return inspections. Employees use the application from a single rental depot. Each checkout must update several related tables atomically, and staff need low-latency queries with strongly consistent results. The application currently runs on PostgreSQL, and the company wants to migrate it to Google Cloud without significantly rewriting the application. Which database should NorthPeak Rentals use?  

- **A.** Bigtable
- **B.** BigQuery
- **C.** Cloud SQL
- **D.** Firestore

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Bigtable is a wide-column NoSQL database designed for extremely large, high-throughput workloads such as time-series data, telemetry, financial market data, personalization, and operational analytics. It provides low-latency access at massive scale, but it does not provide the PostgreSQL relational model required by this application. Bigtable organizes data around row keys rather than relational tables, joins, foreign keys, and standard PostgreSQL queries. Its atomic operations are primarily scoped to an individual row, so it is not suitable for conventional ACID transactions that update several related relational tables. Migrating the existing PostgreSQL application to Bigtable would require substantial changes to the schema, queries, transaction logic, and application data-access layer.

**B is incorrect** because BigQuery is a serverless analytical data platform intended for large-scale reporting, data exploration, business intelligence, and data warehouse workloads. It is optimized for scanning and analyzing large volumes of data rather than processing frequent, low-latency operational transactions. Although BigQuery supports SQL and certain multi-statement transactions, it is not a PostgreSQL-compatible online transaction processing database. Using it for equipment checkouts and inventory updates would produce a poor application architecture and require significant code and schema modifications. BigQuery could be useful later for analyzing historical rental activity, but it should not serve as the application’s primary transactional database.

**C is correct** because Cloud SQL supports fully managed PostgreSQL databases and preserves the relational database capabilities expected by the existing application. It supports relational tables, joins, indexes, constraints, strongly consistent reads, and ACID transactions involving multiple tables. Because the first version already uses PostgreSQL, the company can retain most of its existing SQL statements, schema design, PostgreSQL drivers, and transaction logic, resulting in minimal code changes. Cloud SQL also handles infrastructure responsibilities such as backups, maintenance, patching, monitoring integration, replication, and optional high availability. Since employees use the application from one physical location and there is no stated requirement for global horizontal scalability, a Cloud SQL for PostgreSQL instance in a nearby Google Cloud region is the most appropriate and straightforward solution.

**D is incorrect** because Firestore is a serverless NoSQL document database rather than a PostgreSQL-compatible relational database. Firestore provides strong consistency and supports ACID transactions across multiple documents, so it can support many transactional application patterns. However, its document-oriented data model does not provide traditional PostgreSQL tables, relational joins, foreign-key constraints, or full PostgreSQL query compatibility. Migrating the application to Firestore would require redesigning the relational schema as documents and collections, rewriting queries, and modifying transaction and data-access logic. Firestore is therefore less appropriate when preserving an existing PostgreSQL application with minimal code changes is a primary requirement.

**Reference links**

- [docs.cloud.google.com/sql/docs/postgres](https://docs.cloud.google.com/sql/docs/postgres)
- [docs.cloud.google.com/bigtable/docs/overview](https://docs.cloud.google.com/bigtable/docs/overview)
- [docs.cloud.google.com/bigquery/docs/introduction](https://docs.cloud.google.com/bigquery/docs/introduction)

**Related notes:** [Cloud SQL](../05-storage-databases-data/products/cloud-sql.md)

</details>

[Back to index](#index)

---

### Q11

> NovaCart uses Google Workspace to manage employee accounts. The company expects its workforce to grow from 120 employees to 1,200 employees during the next 18 months, and most employees will require access to Google Cloud resources. You need an identity and access management approach that scales efficiently, remains easy to administer, and protects employee accounts. What should you do?  

- **A.** Move all employee identities to Active Directory, integrate the Human Resources platform with Active Directory, enable Google Cloud Directory Sync for Cloud Identity, and configure identity federation between Cloud Identity and Active Directory.
- **B.** Organize employee identities into groups in Cloud Identity and enforce multi-factor authentication for the users.
- **C.** Configure identity federation between Cloud Identity and Google Workspace and enforce multi-factor authentication for domain-wide delegation.
- **D.** Federate Google Cloud with a third-party identity provider and continuously synchronize employee identities from Google Workspace to that provider.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because migrating an organization that already manages employee identities successfully in Google Workspace to Active Directory would introduce an additional identity system without a stated business requirement. The organization would need to operate Active Directory, integrate it with the Human Resources system, configure Google Cloud Directory Sync, maintain federation, monitor synchronization failures, and resolve identity lifecycle conflicts. This increases operational complexity and creates more components that can fail as the company grows. Google Cloud Directory Sync is useful when Active Directory or another LDAP directory is already the authoritative identity source, but the scenario states that Google Workspace currently manages the employee accounts. Identity federation also normally delegates Google authentication to an external identity provider; describing Cloud Identity as federating identities to Active Directory does not provide the simple, scalable access-management model required here.

**B is correct** because Google groups provide a scalable method for managing authorization in Google Cloud. Administrators can create groups based on departments, job functions, environments, or access requirements and grant IAM roles to those groups rather than assigning roles separately to hundreds or thousands of individual employees. When an employee joins, changes roles, or leaves the company, administrators update the employee’s group membership, and the corresponding Google Cloud permissions are inherited or removed automatically. This reduces administrative effort, limits inconsistent permissions, supports least-privilege access, and scales cleanly as the workforce grows from 120 to 1,200 employees. Enforcing multi-factor authentication, called 2-Step Verification in Google Workspace administration, adds an important security layer by requiring users to provide an additional authentication factor. Because Google Workspace and Cloud Identity use Google-managed identities, the company can continue using its existing identity environment without introducing an unnecessary external directory or federation layer.

**C is incorrect** because Cloud Identity and Google Workspace are not separate external identity providers that need to be federated with each other. Both use Google’s identity infrastructure and can manage users and groups under the organization’s verified domain. An existing Google Workspace customer can use its Workspace identities to access Google Cloud and can enable Cloud Identity for employees who need Google Cloud access without requiring a paid Google Workspace license. In addition, domain-wide delegation is an authorization mechanism that allows a service account or application to impersonate users when calling Google Workspace APIs. It is not the mechanism for enforcing multi-factor authentication for employees. Multi-factor authentication should be enforced for user sign-ins through the Google Admin console.

**D is incorrect** because introducing a third-party identity provider is unnecessary when Google Workspace already serves as the organization’s identity system. It would add federation configuration, synchronization processes, another administrative platform, and additional security and availability dependencies. The proposed synchronization direction is also problematic because organizations normally designate one authoritative identity source and provision identities from that source into Google Workspace or Cloud Identity. Synchronizing users from Google Workspace into a third-party provider and then federating authentication back through that provider creates an unnecessarily circular architecture. A third-party identity provider can be appropriate when an organization already uses one as its authoritative directory, but no such requirement exists in this scenario.

**Reference links**

- [docs.cloud.google.com/iam/docs/groups-best-practices](https://docs.cloud.google.com/iam/docs/groups-best-practices)
- [docs.cloud.google.com/docs/enterprise/cloud-setup](https://docs.cloud.google.com/docs/enterprise/cloud-setup)
- knowledge.workspace.google.com/admin/security/deploy-2-step-verification

**Related notes:** [Cloud Identity and Google Cloud Directory Sync](../02-identity-security/products/cloud-identity-and-google-cloud-directory-sync.md)

</details>

[Back to index](#index)

---

### Q12

> StreamHive Media runs a video-processing application in a single-zone Google Kubernetes Engine cluster in europe-west1-b. After successful testing, the company plans to launch the application for production users. The production environment must remain available during a zonal failure, and StreamHive wants Google Cloud to manage the underlying cluster infrastructure according to recommended practices. What should StreamHive do?  

- **A.** Run gcloud container clusters create with --enable-multi-networking and --enable-autoscaling to create an autoscaling zonal cluster, and deploy the application to the new cluster.
- **B.** Run gcloud container clusters create-auto with the location set to europe-west1 to create an Autopilot cluster, and deploy the application to the new cluster.
- **C.** Run gcloud container clusters update with --region europe-west1 to convert the existing cluster into a regional cluster, and deploy the production application to it.
- **D.** Run gcloud container clusters update with --node-locations europe-west1-b,europe-west1-c to distribute the existing cluster’s nodes across two zones, and deploy the production application to those nodes.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because a zonal GKE cluster has a control plane located in only one zone. Enabling node autoscaling can automatically increase or decrease the number of nodes according to workload demand, but autoscaling does not make the cluster’s control plane regional or protect it from a failure of its control-plane zone. The --enable-multi-networking option enables multiple network interfaces for Pods and is unrelated to control-plane or workload availability across zones. Although a zonal cluster can use nodes in multiple zones, its control plane remains zonal. Google recommends regional clusters for production workloads because their control planes are replicated across multiple zones.

**B is correct** because gcloud container clusters create-auto creates a GKE Autopilot cluster, and Autopilot clusters are always regional. A regional cluster replicates its control plane across multiple zones in the selected region, so a failure in one zone does not make the entire control plane unavailable. Autopilot also manages nodes, scaling, security settings, upgrades, and other infrastructure configuration according to Google Cloud best practices. Nodes and workloads can be distributed across zones, improving resilience to a zonal failure. The application should also be deployed with multiple Pod replicas, appropriate topology-spread or anti-affinity settings, readiness probes, and a PodDisruptionBudget where appropriate so that the application itself can benefit from the cluster’s regional architecture. Creating a new regional Autopilot cluster is preferable because the existing zonal cluster cannot be converted into a regional cluster.

**C is incorrect** because the location type of an existing GKE cluster cannot be changed from zonal to regional by using gcloud container clusters update. The --region option identifies the region of a regional resource when running supported commands; it is not a migration option that converts a zonal control plane into a regional control plane. Cluster location and control-plane availability architecture are determined when the cluster is created. StreamHive must create a new regional cluster and migrate or redeploy the application to it.

**D is incorrect** because changing node locations can distribute worker nodes across multiple zones, but it does not convert the existing zonal control plane into a regional control plane. The cluster would continue to depend on the control plane in its original zone. During an outage of that zone, Pods that are already running in another zone might temporarily continue serving traffic, but Kubernetes API access, scheduling, scaling, and cluster configuration could become unavailable. In addition, using only two explicitly selected node zones provides less zonal distribution than the default multi-zone architecture of a regional cluster. For a highly available production environment, both the control plane and the workload nodes should be designed for multi-zone resilience.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/regional-clusters](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/regional-clusters)
- [docs.cloud.google.com/kubernetes-engine/docs/how-to/creating-an-autopilot-cluster](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/creating-an-autopilot-cluster)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/configuration-overview](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/configuration-overview)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md)

</details>

[Back to index](#index)

---

### Q13

> OrbitLend, a digital lending website, stores customer applications in a Cloud SQL for PostgreSQL instance encrypted with a customer-managed encryption key. Following an IAM security cleanup, the instance becomes inaccessible even though no Cloud SQL settings were changed. Audit logs show that Cloud KMS key version 5 was disabled and the Cloud SQL service agent no longer has the roles/cloudkms.cryptoKeyEncrypterDecrypter role on the key. Which action should the operations team take first to begin recovering the instance?  

- **A.** Provision a replacement Cloud SQL instance and permanently discard the existing encrypted storage.
- **B.** Re-enable Cloud KMS key version 5 so that it can be used to decrypt the existing data.
- **C.** Give the allUsers principal permission to decrypt the Cloud KMS key.
- **D.** Assign a different private IP address to the Cloud SQL instance.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because creating a replacement Cloud SQL instance does not recover the data encrypted by the existing CMEK. The original data remains dependent on the Cloud KMS key version that encrypted its data encryption keys. Because the required key version was disabled rather than destroyed, the situation is recoverable and does not justify abandoning the instance or its storage. Replacing the database would also introduce unnecessary downtime, migration work, and potential data loss.

**B is correct** because a disabled Cloud KMS key version cannot perform cryptographic operations. Re-enabling key version 5 is therefore an immediate and reversible recovery action that makes the required key material usable again. However, re-enabling the key version is only the first recovery step in this scenario. The operations team must also restore the roles/cloudkms.cryptoKeyEncrypterDecrypter role on the CryptoKey to the Cloud SQL service agent. The instance cannot successfully access its CMEK unless both conditions are satisfied: the required key version must be enabled, and the service agent must have permission to encrypt and decrypt by using the key. Among the available choices, re-enabling the existing key version is the only valid first action toward restoring the encrypted database.

**C is incorrect** because granting cryptographic access to allUsers would expose the key to unauthenticated public access and violate the principle of least privilege. CMEK permissions should be granted only to the specific Google Cloud service agent or other authorized principals that need to use the key. The appropriate remediation is to restore the Cloud KMS CryptoKey Encrypter/Decrypter role to the Cloud SQL service agent, not to make the key publicly accessible.

**D is incorrect** because the database IP address controls network connectivity and has no effect on the availability or permissions of a Cloud KMS key. Changing the private IP address would not enable the disabled key version, restore the service agent’s IAM role, or allow Cloud SQL to decrypt the protected data. The failure is caused by key availability and authorization, not by network addressing.

**Reference links**

- [docs.cloud.google.com/kms/docs/enable-disable](https://docs.cloud.google.com/kms/docs/enable-disable)
- [docs.cloud.google.com/sql/docs/postgres/configure-cmek](https://docs.cloud.google.com/sql/docs/postgres/configure-cmek)
- [docs.cloud.google.com/kms/docs/use-keys-google-cloud](https://docs.cloud.google.com/kms/docs/use-keys-google-cloud)

**Related notes:** [Cloud KMS](../02-identity-security/products/cloud-kms.md)

</details>

[Back to index](#index)

---

### Q14

> StreamWave operates a media-processing platform with hundreds of containerized services in a Google Kubernetes Engine (GKE) cluster. Each service runs as a Kubernetes Deployment, and its containers have CPU and memory requests and limits configured. Monitoring data shows that many services are either overprovisioned or underprovisioned. The platform team wants GKE to recommend and automatically apply appropriate CPU and memory allocations based on actual workload usage. What should the team do?  

- **A.** Configure a Vertical Pod Autoscaler for each service.
- **B.** Change the node pool to use a machine type with additional CPU and memory.
- **C.** Configure a Horizontal Pod Autoscaler for each service.
- **D.** Enable GKE cluster autoscaling for the node pools.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a Vertical Pod Autoscaler analyzes the historical and current CPU and memory consumption of the containers in a workload and generates recommendations for appropriately sized resource requests. Depending on the configured update mode, the Vertical Pod Autoscaler can provide recommendations only or automatically apply updated resource allocations to Pods. In its automatic modes, it can recreate Pods when necessary so that they start with the recommended CPU and memory values. GKE Vertical Pod Autoscaling can also adjust resource limits while preserving the configured relationship between requests and limits when RequestsAndLimits is used. Configuring a Vertical Pod Autoscaler for each microservice therefore directly addresses the requirement to right-size the CPU and memory assigned to each workload. This reduces resource waste from overprovisioning and helps prevent performance problems, throttling, scheduling failures, and out-of-memory terminations caused by underprovisioning.

**B is incorrect** because changing the node pool machine type increases or decreases the CPU and memory available on each Kubernetes node, but it does not correct the resource requests or limits configured for individual containers. A microservice with an excessively high memory limit would retain that limit after being scheduled on a larger node, and a container with an insufficient CPU limit could still be throttled. Larger nodes might temporarily hide capacity problems, but they could also increase costs while leaving the underlying workload configurations unchanged. Node sizing is a cluster-capacity decision, whereas the requirement is to right-size resources separately for each microservice.

**C is incorrect** because a Horizontal Pod Autoscaler changes the number of Pod replicas for a workload based on metrics such as CPU utilization, memory utilization, custom metrics, or external metrics. It scales a microservice horizontally by adding Pods when demand increases and removing Pods when demand decreases. It does not primarily determine the appropriate CPU and memory requests or limits for each individual Pod. In addition, CPU-based horizontal scaling relies on resource requests when calculating utilization, so inaccurate requests can cause the Horizontal Pod Autoscaler to make unsuitable scaling decisions. A Horizontal Pod Autoscaler can complement a Vertical Pod Autoscaler in carefully designed configurations, but it does not independently satisfy the requirement to right-size each container’s CPU and memory allocation.

**D is incorrect** because GKE cluster autoscaling adjusts the number of nodes in a node pool according to workload scheduling requirements. It can add nodes when Pods cannot be scheduled because the cluster lacks capacity and remove underutilized nodes when their workloads can be placed elsewhere. However, it does not modify the CPU or memory requests and limits defined for containers. Incorrectly sized workloads would remain incorrectly configured, and the cluster autoscaler might provision unnecessary nodes to accommodate overprovisioned requests. Cluster autoscaling manages infrastructure capacity at the node level, while Vertical Pod Autoscaling manages resource sizing at the workload and container level.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/concepts/verticalpodautoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/verticalpodautoscaler)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/horizontalpodautoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/horizontalpodautoscaler)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler)

**Related notes:** [HPA, VPA, and cluster autoscaler](../03-compute-containers/products/hpa-vpa-and-cluster-autoscaler.md)

</details>

[Back to index](#index)

---

### Q15

> AeroVista Logistics uses several hundred service accounts for warehouse applications running in private data centers and multiple external cloud environments. These applications use service account keys to call Google Cloud APIs. The security team must audit keys across the entire Google Cloud organization and identify those created more than 120 days ago. What should AeroVista Logistics do?  

- **A.** Execute the gcloud asset search-all-resources --scope="organizations/[ORGANIZATION_ID]" --query="createTime &lt; [DATE_120_DAYS_AGO]" --asset-types="apikeys.googleapis.com/Key" --order-by="createTime" command.
- **B.** Execute the gcloud iam service-accounts list --filter="createTime &lt; [DATE_120_DAYS_AGO]" command.
- **C.** Execute the gcloud iam service-accounts keys list --iam-account="[SERVICE_ACCOUNT_EMAIL]" --created-before="[DATE_120_DAYS_AGO]" command.
- **D.** Execute the gcloud asset search-all-resources --scope="organizations/[ORGANIZATION_ID]" --query="createTime &lt; [DATE_120_DAYS_AGO]" --asset-types="iam.googleapis.com/ServiceAccountKey" --order-by="createTime" command.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because apikeys.googleapis.com/Key represents API keys managed by the API Keys API, not private keys associated with IAM service accounts. API keys are generally used to identify a calling project or application when accessing supported APIs, but they do not authenticate an application as a service account. Although Cloud Asset Inventory can search resources across an organization and the createTime query can identify old resources, this command searches the wrong asset type. It would return API key resources created before the specified date rather than the service account keys that the security team needs to audit.

**B is incorrect** because gcloud iam service-accounts list returns service account resources, not the keys belonging to those service accounts. Filtering the results by createTime would identify service accounts created before the specified date, which does not establish the age of any keys associated with them. A service account created several years ago might have a newly rotated key, while a recently created service account might have a key that already violates a shorter key-rotation policy. Additionally, the command normally lists service accounts within a selected project rather than performing a single organization-wide inventory of all service account keys.

**C is incorrect** because gcloud iam service-accounts keys list can list keys created before a specified date, but it requires the --iam-account flag and operates on one service account at a time. To audit hundreds of service accounts across many projects, the organization would first need to enumerate every project and service account and then repeatedly execute this command for each account. That approach requires custom scripting, pagination handling, permission management, error handling, and result aggregation. It is useful when investigating a particular service account, but it is not the most efficient organization-wide auditing method.

**D is correct** because Cloud Asset Inventory provides a centralized inventory that can search supported resources across an entire Google Cloud organization. The organization scope includes resources from projects and folders beneath that organization, subject to the caller having the required permissions. The asset type iam.googleapis.com/ServiceAccountKey restricts the results specifically to IAM service account key resources. The createTime comparison returns only keys created before the calculated cutoff date, and order-by="createTime" arranges the results by age. This provides a single organization-wide command for discovering old service account keys without creating a custom loop for every project and service account. After reviewing the results, the security team can coordinate key rotation by creating replacement keys, updating the external applications, disabling the old keys, validating that the applications still work, and finally deleting the retired keys. Google recommends avoiding long-lived service account keys when possible and using alternatives such as Workload Identity Federation for workloads running outside Google Cloud.

**Reference links**

- [docs.cloud.google.com/iam/docs/key-rotation](https://docs.cloud.google.com/iam/docs/key-rotation)
- [docs.cloud.google.com/sdk/gcloud/reference/asset/search-all-resources](https://docs.cloud.google.com/sdk/gcloud/reference/asset/search-all-resources)
- [docs.cloud.google.com/sdk/gcloud/reference/iam/service-accounts/keys/list](https://docs.cloud.google.com/sdk/gcloud/reference/iam/service-accounts/keys/list)

**Related notes:** [Cloud Asset Inventory](../02-identity-security/products/cloud-asset-inventory.md)

</details>

[Back to index](#index)

---

### Q16

> CedarPay uses a Cloud KMS symmetric encryption key as a customer-managed encryption key for transaction records stored in Google Cloud. The security team configures the key to rotate every 75 days. After a scheduled rotation, the new primary key version protects newly created records, while older records remain unchanged. The team plans to destroy every previous key version immediately. What should the cloud security architect advise?  

- **A.** Previous key versions can always be destroyed because rotation automatically re-encrypts all existing records.
- **B.** Rotation changes the protected records to Google-managed encryption, making previous key versions unnecessary.
- **C.** Previous key versions must remain available to decrypt data protected by them unless that data is explicitly re-encrypted with the new key version.
- **D.** Rotating the key requires deleting and recreating the complete key ring.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because rotating a symmetric Cloud KMS key creates a new key version and makes that version the primary version, but it does not automatically re-encrypt data that was protected by earlier versions. New encryption operations generally use the new primary version, while existing ciphertext or wrapped data encryption keys remain associated with the versions originally used to protect them. Immediately destroying those earlier versions can therefore make existing data permanently inaccessible. The team should first identify all resources that depend on each old version, explicitly re-encrypt or migrate the protected data where the integrated service supports that process, verify that the old version is no longer needed, and only then consider scheduling its destruction.

**B is incorrect** because Cloud KMS key rotation does not change the encryption model from customer-managed encryption keys to Google-managed encryption. The resource remains protected by a CMEK, and the customer continues to control the key, its versions, IAM permissions, rotation schedule, and destruction lifecycle. Rotation simply adds a new version to the existing Cloud KMS CryptoKey and designates it as the primary version for new encryption operations. Previous versions remain relevant because they may still be required to unwrap data encryption keys or decrypt ciphertext created before the rotation.

**C is correct** because data encrypted under an older symmetric key version continues to depend on that specific version until the data is re-encrypted. Cloud KMS records the key version used during encryption and can select the appropriate version during decryption, provided that the version remains enabled and usable. Rotation does not modify existing ciphertext or automatically move it to the new primary version. For CMEK-integrated services, earlier key versions commonly remain necessary to unwrap the data encryption keys that protect older resources. Destroying a required version destroys its key material and can result in permanent loss of access to the associated data. The administrator should retain old versions until dependency checks and re-encryption or resource migration are complete. Disabling an old version can sometimes be used as a reversible test before destruction, but it can still interrupt access to dependent data and must be planned carefully.

**D is incorrect** because rotation occurs at the CryptoKey version level and does not require deleting or recreating the key ring. A key ring is a regional container for Cloud KMS keys, while a symmetric CryptoKey can contain multiple key versions. Automatic or manual rotation creates a new version inside the existing CryptoKey and sets that version as primary. The key ring, CryptoKey resource name, IAM configuration, and service integrations can remain in place. Deleting and rebuilding the key hierarchy would be unnecessary, disruptive, and inconsistent with the normal Cloud KMS rotation process.

**Reference links**

- [docs.cloud.google.com/kms/docs/key-rotation](https://docs.cloud.google.com/kms/docs/key-rotation)
- [docs.cloud.google.com/kms/docs/re-encrypt-data](https://docs.cloud.google.com/kms/docs/re-encrypt-data)
- [docs.cloud.google.com/kms/docs/cmek-rotation](https://docs.cloud.google.com/kms/docs/cmek-rotation)

**Related notes:** [Cloud KMS](../02-identity-security/products/cloud-kms.md)

</details>

[Back to index](#index)

---

### Q17

> CareBridge Portal, a healthcare operations company, has created one stateless web application that provides a browser-based interface and several HTTP endpoints. Employees must access the application through an internal IP address from both the company’s private VPC network and its on-premises network. The development team releases changes several times each day and wants to minimize deployment effort and infrastructure administration. What should the company do?  

- **A.** Deploy the application to a GKE Standard cluster and configure an internal Ingress.
- **B.** Deploy the application to Cloud Run and enable Private Google Access.
- **C.** Deploy the application to Cloud Run and configure Private Service Connect.
- **D.** Deploy the application to a GKE Autopilot cluster and enable Private Google Access.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a GKE Standard cluster with an internal Ingress can expose the application through an internal Application Load Balancer and make it accessible from the VPC and a connected on-premises network. However, GKE Standard requires the team to manage more infrastructure and Kubernetes configuration, including clusters, node pools, workloads, Services, Ingress resources, scaling, upgrades, and security settings. That operational overhead is unnecessary for a single stateless web application that is updated multiple times per day. Cloud Run provides a simpler deployment model and manages the underlying compute infrastructure automatically.

**B is incorrect** because Cloud Run is appropriate for a frequently updated stateless web application, but Private Google Access does not assign the Cloud Run service an internal IP address. Private Google Access primarily allows resources without external IP addresses to reach supported Google APIs and services through Google-owned external IP address ranges while keeping traffic on Google’s network. Although Cloud Run can be reached from a VPC or on-premises environment by using Private Google Access with the required routing and DNS configuration, this option does not directly satisfy the explicit requirement to access the application through an internal IP address.

**C is correct** because Cloud Run is a fully managed serverless platform that is well suited to a single stateless web application with a web interface and multiple HTTP endpoints. Developers can deploy new container revisions several times per day without managing virtual machines, Kubernetes nodes, cluster upgrades, or application load-balancer infrastructure. A Private Service Connect endpoint for Google APIs provides an internal IP address in the company’s VPC network. By configuring a private DNS zone for the Cloud Run run.app domain, requests to the application can resolve to that Private Service Connect endpoint. Resources in the VPC can then access Cloud Run through the internal IP address. On-premises systems connected through Cloud VPN or Cloud Interconnect can also be configured to route to and resolve the endpoint. The Cloud Run service should additionally use an appropriate restrictive ingress setting and authentication controls to prevent unauthorized public access.

**D is incorrect** because GKE Autopilot reduces node-management responsibilities compared with GKE Standard, but the team must still manage Kubernetes resources such as Deployments, Services, Ingress configuration, namespaces, manifests, and workload policies. More importantly, Private Google Access does not expose the application through an internal IP address. It enables eligible resources to reach Google APIs and services and is not a substitute for an internal Ingress, an internal LoadBalancer Service, or a Private Service Connect endpoint. This option therefore neither provides the specified internal application endpoint nor minimizes application-platform management as effectively as Cloud Run with Private Service Connect.

**Reference links**

- [docs.cloud.google.com/run/docs/securing/private-networking](https://docs.cloud.google.com/run/docs/securing/private-networking)
- [docs.cloud.google.com/vpc/docs/private-service-connect](https://docs.cloud.google.com/vpc/docs/private-service-connect)
- [docs.cloud.google.com/vpc/docs/private-google-access](https://docs.cloud.google.com/vpc/docs/private-google-access)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md) · [Private Service Connect](../06-networking/products/private-service-connect.md)

</details>

[Back to index](#index)

---

### Q18

> ParcelPilot runs a shipment-tracking API on Compute Engine VMs in a managed instance group. Cloud Logging indicates that the message-processing service on one member VM has stopped responding, while the remaining VMs are operating normally. You need to immediately rebuild only the affected VM by using the managed instance group’s current configuration. What should you do?  

- **A.** Run the gcloud compute instances update command for the affected VM and specify a REFRESH action.
- **B.** Run the gcloud compute instance-groups managed recreate-instances command for the affected VM.
- **C.** Select the managed instance group in the Google Cloud console and start a Replace VMs operation for the group.
- **D.** Modify the instance template and apply the updated template to the managed instance group.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because a REFRESH action is intended for applying non-disruptive configuration changes, such as changes to metadata, labels, tags, additional disks, or certain network interface properties. It does not delete and rebuild an unhealthy VM. In addition, gcloud compute instances update operates on an individual Compute Engine VM rather than instructing the managed instance group to recreate one of its managed members from the group’s desired configuration. Because the unresponsive process requires a clean replacement of the VM, refreshing configuration would not reliably resolve the problem.

**B is correct** because gcloud compute instance-groups managed recreate-instances is specifically designed to recreate one or more selected VMs in a managed instance group. The command causes the underlying VM to be deleted and recreated according to the MIG’s current configuration, including its latest applicable instance template and any relevant per-instance or stateful configuration. You can identify only the malfunctioning VM with the --instances flag, so the healthy VMs remain unaffected. This provides the most direct and targeted way to replace the problematic member without initiating an update across the entire group. A typical command is gcloud compute instance-groups managed recreate-instances MIG_NAME --instances=INSTANCE_NAME --zone=ZONE for a zonal MIG, or with --region=REGION for a regional MIG.

**C is incorrect** because the Restart/replace VMs operation in the Google Cloud console is designed for a rolling restart or replacement of the VMs in the managed instance group. Starting a Replace VMs operation at the group level can replace every VM according to the selected rolling-update parameters, rather than targeting only the single malfunctioning VM. Although this operation can refresh an entire group, it introduces unnecessary disruption and is broader than the requirement. The recreate-instances command provides precise control over the individual VM that must be rebuilt.

**D is incorrect** because an instance template should be changed when the desired VM configuration itself needs to change, such as when deploying a different machine type, boot image, startup script, network configuration, or application version. In this case, there is no indication that the MIG configuration is incorrect; only one existing VM has a nonresponsive process. Applying an instance template can also initiate a selective or automatic rollout that affects multiple VMs, depending on the MIG’s update policy. Recreating the affected VM from the existing configuration is faster, more targeted, and avoids making an unnecessary infrastructure change.

**Reference links**

- [docs.cloud.google.com/compute/docs/instance-groups/working-with-managed-instances](https://docs.cloud.google.com/compute/docs/instance-groups/working-with-managed-instances)
- [docs.cloud.google.com/sdk/gcloud/reference/compute/instance-groups/managed/recreate-instances](https://docs.cloud.google.com/sdk/gcloud/reference/compute/instance-groups/managed/recreate-instances)
- [docs.cloud.google.com/compute/docs/instance-groups/rolling-out-updates-to-managed-instance-groups](https://docs.cloud.google.com/compute/docs/instance-groups/rolling-out-updates-to-managed-instance-groups)

**Related notes:** [Managed Instance Group (MIG)](../03-compute-containers/products/managed-instance-group.md)

</details>

[Back to index](#index)

---

### Q19

> BluePeak Robotics manages several Google Cloud projects for application development, testing, and production. Every developer must receive an identical set of permissions across all projects, and company policy allows developers to work only with Compute Engine, Cloud Run functions, and Cloud SQL resources. You want to implement and maintain this access model with the least administrative effort. What should you do?  

- **A.** Create a project-level custom role containing the required Compute Engine, Cloud Run functions, and Cloud SQL permissions in one project, copy the custom role to every other project by using the gcloud iam roles copy command, and grant each copied role to the developers in its respective project.
- **B.** Add all developers to a Google group managed through Google Workspace, and grant the predefined Compute Admin role to the group at the organization level.
- **C.** Add all developers to a Google group in Cloud Identity, and grant separate predefined roles for Compute Engine, Cloud Run functions, and Cloud SQL to the group individually in every project.
- **D.** Add all developers to a Google group in Cloud Identity, create an organization-level custom role containing the required Compute Engine, Cloud Run functions, and Cloud SQL permissions, and grant that custom role to the group at the organization level.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a project-level custom role is defined only within the project in which it is created. Copying the role to every project would create independent custom-role definitions that must be separately managed. The administrators would also need to grant the copied role in every existing project and repeat the process whenever a new project is created. Later permission changes would have to be copied or applied across all of those independent roles because updating the original role would not automatically update its copies. Although this approach could provide the required permissions, it creates unnecessary duplication and ongoing administrative overhead.

**B is incorrect** because the Compute Admin predefined role primarily grants broad administrative permissions for Compute Engine resources. It does not provide the required permissions for Cloud Run functions or Cloud SQL. Therefore, developers would not receive the complete access required by the company. The Compute Admin role could also provide more Compute Engine permissions than the developers need, depending on their responsibilities. Assigning the role at the organization level would make its permissions available throughout descendant projects, but the role does not satisfy the requirement to provide a controlled combination of permissions across all three specified services.

**C is incorrect** because managing developers through a Cloud Identity group is appropriate, and predefined roles could potentially provide the necessary service permissions. However, assigning several roles separately in every project requires repeated IAM configuration across the organization. Administrators would need to add the role bindings whenever a project is created and update multiple project policies whenever the access model changes. This approach does not meet the requirement to implement the policy with minimal effort when the same permission set must apply consistently across every project.

**D is correct** because an organization-level custom role provides one centrally managed collection of the required permissions for Compute Engine, Cloud Run functions, and Cloud SQL. Granting this role to a Cloud Identity group at the organization level causes the role binding to be inherited by projects and other supported descendant resources in the organization. Existing developers can be added to the group, and new developers can receive the same permissions simply by being added to that group. Newly created projects under the organization also inherit the organization-level role binding without requiring separate project-level assignments. This design centralizes both permission management and developer membership, avoids duplicated custom roles and IAM bindings, and implements the company’s security policy with the least administrative effort.

**Reference links**

- [docs.cloud.google.com/iam/docs/creating-custom-roles](https://docs.cloud.google.com/iam/docs/creating-custom-roles)
- [docs.cloud.google.com/iam/docs/resource-hierarchy-access-control](https://docs.cloud.google.com/iam/docs/resource-hierarchy-access-control)
- [docs.cloud.google.com/iam/docs/groups-best-practices](https://docs.cloud.google.com/iam/docs/groups-best-practices)

</details>

[Back to index](#index)

---

### Q20

> BlueOrbit Travel operates a reservation platform on Google Cloud. During an incident, an engineer discovers unfamiliar and difficult-to-interpret error entries in Cloud Logging. The entries contain no personally identifiable information or other sensitive data. The engineer must quickly understand what the entries mean and identify the most appropriate troubleshooting steps. What should the engineer do first?  

- **A.** Copy each error message and manually search public technical forums and product documentation.
- **B.** Use Cloud Profiler to examine the application’s CPU and memory behavior when the errors occurred.
- **C.** Select “Explain this log entry” in Logs Explorer and continue the investigation through a conversation with Gemini.
- **D.** Search the entire application codebase for the text contained in each error message.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because manually searching forums and documentation is slower and requires the engineer to leave the Google Cloud troubleshooting workflow, copy individual messages, compare potentially irrelevant search results, and determine whether those results apply to the application’s environment. Public search results might refer to different software versions, configurations, or products. Although searching official documentation can become useful after the engineer identifies the likely source of the problem, it is not the fastest first action when Logs Explorer provides integrated Gemini assistance for interpreting an unfamiliar log entry. Even when a log contains no PII, engineers should still avoid publishing proprietary configuration data, credentials, tokens, internal addresses, or other sensitive operational information in public forums.

**B is incorrect** because Cloud Profiler is designed to continuously collect and analyze application profiling information, such as CPU consumption, heap usage, memory allocation, and execution time attributed to application source code. It is useful when investigating performance problems, including excessive CPU usage, memory pressure, inefficient functions, and latency caused by resource-intensive code. However, an unfamiliar error message does not necessarily represent a performance problem. Cloud Profiler would not directly explain the meaning of the log entry or recommend actions based on its textual contents. The engineer should first interpret the error and then use Cloud Profiler only if the explanation indicates a CPU, memory, or code-performance issue.

**C is correct** because the integrated Gemini capability in Logs Explorer can analyze the selected log entry, summarize its contents in plain language, explain relevant fields, and help the engineer understand a cryptic message without manually moving the information into another tool. Continuing the investigation as a conversation with Gemini allows the engineer to ask follow-up questions about possible causes, troubleshooting procedures, affected components, and recommended next actions. This is the most efficient first step because it provides immediate context within the Cloud Logging interface. The engineer must still validate Gemini’s suggestions against the application configuration, surrounding logs, metrics, traces, documentation, and source code before making production changes. The statement that the entries contain no PII is important because log content selected for explanation is processed by the Gemini assistance feature; sensitive information should not be included unnecessarily.

**D is incorrect** because searching the source code before understanding the error can be inefficient, especially when the message originates from a Google Cloud service, operating system component, third-party library, container runtime, or managed platform rather than from a literal string in the application. The message might also be dynamically generated, parameterized, or transformed before being written to Cloud Logging, meaning an exact text search could return no useful results. Source-code inspection is a reasonable later step after Gemini helps identify the probable component, function, dependency, or configuration involved, but it is not the fastest initial method for interpreting an unfamiliar log entry.

**Reference links**

- [docs.cloud.google.com/logging/docs/view/summarize-log-entries-gemini](https://docs.cloud.google.com/logging/docs/view/summarize-log-entries-gemini)
- [docs.cloud.google.com/logging/docs/view/logs-explorer-interface](https://docs.cloud.google.com/logging/docs/view/logs-explorer-interface)
- [docs.cloud.google.com/profiler/docs/about-profiler](https://docs.cloud.google.com/profiler/docs/about-profiler)

**Related notes:** [Gemini Cloud Assist](../08-iac-platform-ai/products/gemini-cloud-assist.md)

</details>

[Back to index](#index)

---

### Q21

> BrightFrame Studios stores completed animation render files on a local network-attached storage system. The company wants to archive these files in Cloud Storage and automatically copy newly created render files to the archive bucket. You need to implement a simple solution with minimal development effort. What should you do?  

- **A.** -Create a Pub/Sub topic and configure a Cloud Storage event trigger for the topic.  
  -Develop an application that publishes every render file to the Pub/Sub topic.
- **B.** Create a script that uses the gcloud storage rsync command to synchronize the local render directory with the Cloud Storage bucket, and schedule the script as a cron job.
- **C.** -Create a Pub/Sub topic and deploy a Cloud Run function that receives messages from the topic and writes their contents to Cloud Storage.  
  -Develop an application that publishes every render file to the topic.
- **D.** Open Cloud Storage in the Google Cloud console and manually upload newly created render files to the archive bucket.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because a Cloud Storage event trigger responds to events involving objects that are already being created, updated, or deleted in Cloud Storage. It does not monitor an on-premises directory or initiate uploads from local storage. Additionally, Pub/Sub is an asynchronous messaging service rather than a bulk file-transfer mechanism. Publishing complete render files as Pub/Sub message payloads would introduce message-size limitations, encoding overhead, additional application development, and unnecessary operational complexity. Pub/Sub could notify another service that a file is available, but it would not independently transfer files from the local storage system.

**B is correct** because gcloud storage rsync is specifically designed to synchronize a local directory with a Cloud Storage bucket. It compares the source and destination and copies files that are new or have changed, avoiding the need to upload every file during every execution. Scheduling the command as a cron job provides the required automation with minimal custom development. The script can use a command such as gcloud storage rsync /data/renders gs://brightframe-render-archive --recursive. The identity running the script must have appropriate permissions, such as permission to list and create objects in the destination bucket. For an archive, the script should normally avoid options that delete unmatched destination objects unless deletion from Cloud Storage is explicitly required.

**C is incorrect** because this design introduces Pub/Sub, a publisher application, and a Cloud Run function when the requirement can be satisfied directly with a synchronization command. Sending complete files through Pub/Sub is unsuitable for potentially large binary objects because Pub/Sub messages have fixed size limits and may require base64 encoding when sent through the REST API. Pub/Sub also provides at-least-once delivery, so the function would need idempotency and duplicate-handling logic. Publishing only file metadata would not solve the problem either, because the Cloud Run function would still need network access to retrieve the file from the on-premises storage system. Although this architecture could be engineered, it is unnecessarily complex for periodic directory synchronization.

**D is incorrect** because uploading files through the Google Cloud console is a manual process. It may be suitable for a one-time upload or a small number of files, but it does not continuously detect and transfer newly created files. It also depends on an administrator repeatedly performing the upload and therefore does not meet the automation requirement.

**Reference links**

- [docs.cloud.google.com/sdk/gcloud/reference/storage/rsync](https://docs.cloud.google.com/sdk/gcloud/reference/storage/rsync)
- [docs.cloud.google.com/storage/docs/working-with-big-data](https://docs.cloud.google.com/storage/docs/working-with-big-data)
- [docs.cloud.google.com/pubsub/docs/overview](https://docs.cloud.google.com/pubsub/docs/overview)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q22

> StreamForge operates a live-event notification platform that provisions Google Cloud resources through Config Connector. A Pub/Sub topic named archived-alerts is represented by a PubSubTopic Kubernetes resource and is no longer required. You need to permanently remove both the Kubernetes resource and the underlying Pub/Sub topic from the Google Cloud project. What should you do?  

- **A.** Use kubectl to add a deleted-by-cnrm label with the value true to the PubSubTopic resource.
- **B.** Use kubectl to delete the PubSubTopic resource.
- **C.** Use the gcloud CLI to delete the underlying Pub/Sub topic directly.
- **D.** Use the gcloud CLI to change the topic’s managed-by-cnrm label to false.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Config Connector does not recognize a deleted-by-cnrm label as an instruction to delete a Google Cloud resource. Kubernetes labels are generally metadata used to organize, identify, and select resources. Adding an arbitrary label does not initiate deletion of either the PubSubTopic Kubernetes resource or the corresponding Pub/Sub topic. Config Connector deletion behavior is controlled through deletion of the Kubernetes resource and, when necessary, the cnrm.cloud.google.com/deletion-policy annotation.

**B is correct** because Config Connector manages Google Cloud resources through Kubernetes custom resources. Deleting the PubSubTopic resource with kubectl instructs Config Connector to delete the associated Pub/Sub topic from Google Cloud. By default, the cnrm.cloud.google.com/deletion-policy annotation has the value none, which means deletion of the Config Connector resource also deletes the underlying Google Cloud resource. For example, kubectl delete pubsubtopic archived-alerts removes the Kubernetes object, and Config Connector reconciles that deletion by deleting the corresponding Pub/Sub topic. Before using this approach, you should verify that the resource is not configured with cnrm.cloud.google.com/deletion-policy: abandon, because the abandon policy would remove only the Kubernetes object while preserving the Pub/Sub topic in Google Cloud.

**C is incorrect** because directly deleting the Pub/Sub topic with the gcloud CLI bypasses Config Connector’s desired-state management process. The PubSubTopic Kubernetes resource would continue to exist and declare that the topic should exist. During a subsequent reconciliation, Config Connector could detect that the underlying topic is missing and recreate it. This approach also leaves the Kubernetes resource out of synchronization with the actual Google Cloud environment. Resources managed by Config Connector should normally be modified or deleted through their Kubernetes resource definitions.

**D is incorrect** because managed-by-cnrm is not a Config Connector control label that transfers ownership or stops reconciliation when its value is changed. Changing a Pub/Sub topic label through the gcloud CLI only modifies the topic’s metadata. It does not delete the topic, remove the corresponding Kubernetes resource, or instruct Config Connector to stop managing the resource. Config Connector could also reconcile the label back to the value declared in the PubSubTopic specification.

**Reference links**

- [docs.cloud.google.com/config-connector/docs/how-to/managing-deleting-resources](https://docs.cloud.google.com/config-connector/docs/how-to/managing-deleting-resources)
- [docs.cloud.google.com/config-connector/docs/reference/annotations](https://docs.cloud.google.com/config-connector/docs/reference/annotations)
- [docs.cloud.google.com/config-connector/docs/reference/resource-docs/pubsub/pubsubtopic](https://docs.cloud.google.com/config-connector/docs/reference/resource-docs/pubsub/pubsubtopic)

**Related notes:** [Config Connector](../08-iac-platform-ai/products/config-connector.md)

</details>

[Back to index](#index)

---

### Q23

> Northstar HR has built a containerized employee benefits portal that authenticated staff members use only on weekdays from 7:30 a.m. to 6:30 p.m. The application is being deployed in a newly created Google Cloud project with no existing infrastructure. Northstar HR wants the application runtime to stop consuming compute resources when no employees are using it. What should Northstar HR do?  

- **A.** Deploy the container with Knative serving on GKE Enterprise, and configure the minimum number of container instances as zero.
- **B.** Deploy the container on Cloud Run, and configure the minimum number of instances as zero.
- **C.** Deploy the container in the App Engine flexible environment with automatic scaling, and configure min_num_instances as zero in app.yaml.
- **D.** Deploy the container in the App Engine flexible environment with manual scaling, and configure instances as zero in app.yaml.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Knative serving can scale an application revision to zero container instances when it receives no traffic, but it operates on Google Kubernetes Engine infrastructure. Northstar HR would first need to create and maintain a GKE cluster because the new project has no existing infrastructure. Scaling the application’s containers to zero does not necessarily scale the underlying cluster nodes and other cluster components to zero. Charges associated with the GKE cluster, its worker nodes, networking, and any applicable GKE Enterprise features can therefore continue outside business hours. This option does not meet the requirement to avoid paying for continuously provisioned compute infrastructure.

**B is correct** because Cloud Run is a fully managed serverless container platform that does not require Northstar HR to provision or maintain virtual machines or a Kubernetes cluster. With the minimum instance setting configured as zero, Cloud Run can scale the service down to zero instances when it is not receiving requests. When an authenticated employee sends a request, Cloud Run starts an instance to process it and automatically scales the service according to demand. Under request-based billing, idle instances that are not maintained through a minimum-instance configuration are not charged for idle compute time. This makes Cloud Run the most appropriate option for a containerized application that is used only during specific hours. Identity and Access Management and Cloud Run ingress settings can also be configured separately to restrict access to authorized internal employees. Other resources used by the solution, such as stored container images or retained logs, can still have separate charges, but Cloud Run avoids continuously running application compute instances.

**C is incorrect** because the App Engine flexible environment cannot scale an active application version down to zero instances. Each active version must maintain at least one running instance, and the min_num_instances value for automatic scaling must be one or greater. Configuring min_num_instances as zero is therefore invalid. App Engine flexible environment instances are based on Compute Engine virtual machines, so at least one instance continues running and generating charges even when the application receives no traffic outside business hours.

**D is incorrect** because manual scaling in the App Engine flexible environment maintains a fixed number of continuously running instances. The instances setting must specify at least one instance and cannot be configured as zero for a deployed active version. Manual scaling is intended for applications that require a fixed amount of capacity or continuously available instances. It does not provide scale-to-zero behavior and would result in compute charges outside the hours when employees use the portal.

**Reference links**

- [docs.cloud.google.com/run/docs/about-instance-autoscaling](https://docs.cloud.google.com/run/docs/about-instance-autoscaling)
- [docs.cloud.google.com/run/docs/configuring/min-instances](https://docs.cloud.google.com/run/docs/configuring/min-instances)
- [docs.cloud.google.com/appengine/docs/flexible/how-instances-are-managed](https://docs.cloud.google.com/appengine/docs/flexible/how-instances-are-managed)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md)

</details>

[Back to index](#index)

---

### Q24

> BrightTrail Logistics runs a shipment-tracking service on a Compute Engine VM connected to an IPv4-only subnet in a VPC network. Other applications in the same VPC must always reach this VM by using the same IP address. BrightTrail wants to follow Google Cloud recommended practices and avoid unnecessary networking charges. What should BrightTrail do?  

- **A.** Promote the VM’s current IP address to a static external IPv4 address.
- **B.** Promote the VM’s current IP address to a static internal IPv4 address.
- **C.** Reserve a new static external IPv6 address and attach it to the VM.
- **D.** Reserve a new static external IPv4 address and attach it to the VM.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because a static external IPv4 address provides a stable publicly routable address, but the communicating services are located inside the same VPC network and do not require public connectivity. Using an external address would unnecessarily expose an additional network path that must be protected with firewall rules and would incur external IPv4 address charges. It also does not follow the recommended practice of using internal addresses for private communication between resources in a VPC. Although promoting the existing address avoids changing the address used by clients, promoting it as an external address solves the wrong connectivity requirement.

**B is correct** because a static internal IPv4 address provides a fixed private address that other resources in the same VPC network can use to communicate with the VM. Google Cloud permits an in-use ephemeral internal IP address to be promoted to a static internal IP address. After promotion, the address remains reserved for the project until it is explicitly released, instead of being returned to the subnet’s available address pool when the VM is deleted or reconfigured. Promoting the existing address also avoids changing the endpoint already used by dependent services. Static and ephemeral internal IP addresses do not have an hourly IP address charge, so this approach meets the fixed-address requirement while minimizing cost and avoiding unnecessary public exposure.

**C is incorrect** because an external IPv6 address is intended for communication through publicly routable IPv6 connectivity, not private communication between services in the same VPC. An IPv4-only single-stack network interface cannot be assigned an IPv6 address; the interface would need to connect to a dual-stack or IPv6-only subnet with the appropriate IPv6 configuration. Assigning a new address would also require dependent services to update their configurations. Even where external IPv6 is supported, using it for an internal VPC communication requirement introduces unnecessary public addressing and does not represent the recommended private-connectivity design.

**D is incorrect** because reserving and assigning a new static external IPv4 address would provide a fixed address, but external addressing is unnecessary when all clients are in the same VPC network. External IPv4 addresses assigned to VM instances are billable, whereas internal IP addresses have no separate address charge. A new address would also force other services to update the destination IP they currently use. Promoting the existing ephemeral internal IP address to static is simpler, less disruptive, more secure, and less expensive.

**Reference links**

- [docs.cloud.google.com/vpc/docs/reserve-static-internal-ip-address](https://docs.cloud.google.com/vpc/docs/reserve-static-internal-ip-address)
- [docs.cloud.google.com/vpc/docs/ip-addresses](https://docs.cloud.google.com/vpc/docs/ip-addresses)
- [cloud.google.com/vpc/network-pricing](https://cloud.google.com/vpc/network-pricing)

**Related notes:** [Compute Engine](../03-compute-containers/products/compute-engine.md)

</details>

[Back to index](#index)

---

### Q25

> PixelForge Media runs a single video-processing job on an on-premises server. The job takes approximately 34 hours to finish, runs once every six weeks, and does not need to process data in real time. The job cannot resume from a checkpoint and must start again from the beginning if the underlying server is interrupted. PixelForge Media wants to migrate the workload to Google Cloud while keeping costs as low as possible. What should the company do?  

- **A.** -Create an instance template that uses Spot VMs.  
  -Create a managed instance group from the template, configure target CPU utilization, and migrate the job to the group.
- **B.** Migrate the job to a standard Compute Engine VM, and start and stop the VM when required.
- **C.** Migrate the job to a Google Kubernetes Engine cluster that uses Spot VM nodes.
- **D.** Migrate the job to a standalone Compute Engine Spot VM.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because a managed instance group is designed to operate and scale a collection of similar VM instances, making it useful for distributed, stateless, or horizontally scalable workloads. This scenario involves only one long-running batch process that cannot divide its work among multiple instances and cannot continue from a saved checkpoint. Target CPU utilization would not provide a meaningful scaling signal for a single monolithic job. Although a managed instance group can attempt to recreate a Spot VM after preemption, recreating the VM does not restore the interrupted application process. The entire 34-hour job would still have to begin again. This design therefore introduces unnecessary instance templates, autoscaling configuration, and managed instance group administration without solving the interruption problem.

**B is correct** because a standard Compute Engine VM provides stable compute capacity for the complete execution of the non-fault-tolerant batch job. The company can start the VM when the job is scheduled, allow it to run for approximately 34 hours, and stop it immediately after the job completes. While the VM is stopped, Google Cloud does not charge for its vCPU and memory usage, although attached storage and certain reserved networking resources can continue to incur charges. Because the job runs only once every six weeks, this start-and-stop approach prevents the company from paying for an idle VM between executions. It also avoids the risk of Spot VM preemption, which would force the entire long-running job to restart and could waste many hours of already-paid processing. A standard Compute Engine VM therefore provides the best balance of reliability, simplicity, and cost control for this workload.

**C is incorrect** because Google Kubernetes Engine is intended for deploying and orchestrating containerized workloads, particularly applications that benefit from scheduling, service discovery, scaling, and automated workload management. A full GKE cluster is unnecessary for one batch process that currently runs on a single server. Spot nodes can also be preempted at any time, so the pod running the job could be terminated before the 34-hour process completes. Kubernetes can create a replacement pod, but the replacement would restart the job from the beginning unless the application supports checkpointing or divides the work into independently retryable tasks. Containerizing the application and operating a Kubernetes cluster would add complexity without providing a meaningful benefit.

**D is incorrect** because Spot VMs can be preempted by Compute Engine at any time when Google Cloud needs to reclaim capacity. Modern Spot VMs do not have a fixed maximum runtime, so a Spot VM could theoretically run for the entire 34-hour period. However, there is no guarantee that it will remain available for that duration. This workload is not fault-tolerant because an interruption discards all progress and requires the complete job to restart. A preemption near the end of processing could waste almost 34 hours of compute work, and repeated preemptions could delay completion and reduce or eliminate the expected cost savings. Spot VMs are better suited to checkpointable, distributed, stateless, or independently retryable batch workloads.

**Reference links**

- [docs.cloud.google.com/compute/docs/instances/spot](https://docs.cloud.google.com/compute/docs/instances/spot)
- [docs.cloud.google.com/compute/docs/instances/stop-start-instance](https://docs.cloud.google.com/compute/docs/instances/stop-start-instance)
- [docs.cloud.google.com/compute/docs/instance-groups](https://docs.cloud.google.com/compute/docs/instance-groups)

**Related notes:** [Spot VMs](../03-compute-containers/products/spot-vms.md)

</details>

[Back to index](#index)

---

### Q26

Choose 2.

> MealMetric, a food-delivery analytics company, stores order and customer activity data in BigQuery. When a data analyst runs a query for the weekly operations dashboard, BigQuery returns a quotaExceeded error. The cloud administrator must determine which quota or limit caused the failure. What should the administrator do? (Choose two.)  

- **A.** Use BigQuery BI Engine to investigate the failed query.
- **B.** Query the BigQuery INFORMATION_SCHEMA views to examine job activity and quota usage.
- **C.** Configure Cloud Trace to inspect the execution path of the failed query.
- **D.** Search for quota-related errors in Cloud Audit Logs.
- **E.** Review application errors in Cloud Monitoring.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B, D

**Explanation**

**A is incorrect** because BigQuery BI Engine is an in-memory analysis service designed to accelerate SQL queries, dashboards, and reports that access BigQuery data. It improves query performance by caching frequently used data and reducing response times for business intelligence workloads. It does not provide diagnostic information about failed BigQuery jobs or identify which project-level, table-level, API, query, load, copy, or extract quota produced a quotaExceeded error.

**B is correct** because BigQuery INFORMATION_SCHEMA views provide near-real-time metadata about BigQuery jobs and resource usage. Views such as INFORMATION_SCHEMA.JOBS, INFORMATION_SCHEMA.JOBS_BY_PROJECT, and INFORMATION_SCHEMA.JOBS_BY_USER can be queried to examine recently submitted jobs, their job types, creation times, users, states, error results, and other execution details. An administrator can aggregate query, load, extract, or copy jobs over a selected period and compare the observed workload with the corresponding BigQuery quota. This helps determine whether the error resulted from excessive job submissions, queued queries, table modifications, data processed, or another quota-controlled operation.

**C is incorrect** because Cloud Trace is a distributed tracing service for analyzing request latency and execution paths across applications and services. It is useful for following requests through components such as APIs, microservices, and application backends. A BigQuery quotaExceeded response is generated when a documented quota or system limit is reached, not because of an application request-latency issue. Cloud Trace therefore does not provide the BigQuery job and quota metadata needed to identify the exceeded limit.

**D is correct** because BigQuery administrative and data-access activity can be recorded in Cloud Audit Logs, including failed operations and their status messages. Using Logs Explorer, the administrator can filter BigQuery resource entries for status messages containing terms such as Quota exceeded or limit. The matching log entry can reveal the affected project or dataset, the operation that failed, the caller, the time of failure, and the detailed error message identifying the applicable quota. This is one of the recommended methods for investigating BigQuery quota and limit errors.

**E is incorrect** because Cloud Monitoring is primarily used to collect metrics, create dashboards, monitor resource health, and configure alerts. It can help administrators observe quota-related metrics or recognize a broader usage trend, but its general error views do not provide the same query-job metadata and detailed quota failure messages available through BigQuery INFORMATION_SCHEMA and Cloud Audit Logs. For diagnosing the specific cause of this quotaExceeded query failure, INFORMATION_SCHEMA and Cloud Audit Logs are the more direct tools.

**Reference links**

- [docs.cloud.google.com/bigquery/docs/troubleshoot-quotas](https://docs.cloud.google.com/bigquery/docs/troubleshoot-quotas)
- [docs.cloud.google.com/bigquery/docs/information-schema-jobs](https://docs.cloud.google.com/bigquery/docs/information-schema-jobs)
- [docs.cloud.google.com/logging/docs/audit](https://docs.cloud.google.com/logging/docs/audit)

**Related notes:** [BigQuery](../05-storage-databases-data/products/bigquery.md)

</details>

[Back to index](#index)

---

### Q27

> NovaCart operates a set of Compute Engine VMs that process customer orders. The security team recently added an egress deny rule to prevent these VMs from connecting to a restricted external network. An analyst must verify whether that exact firewall rule is denying connections and determine the number of affected connections. Which feature should the team enable?  

- **A.** Enable Cloud Trace on the external destination service.
- **B.** Review only Admin Activity audit logs.
- **C.** Enable Firewall Rules Logging on the applicable egress deny rule.
- **D.** Enable object versioning on a Cloud Storage bucket.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because Cloud Trace collects latency and execution-path information for requests processed by instrumented applications. It can help identify performance bottlenecks across services, but it does not record which Cloud NGFW or VPC firewall rule allowed or denied a network connection. The prohibited destination might also be outside the company’s control and therefore unavailable for instrumentation. Cloud Trace cannot provide authoritative evidence that a specific egress deny rule matched the VMs’ connections.

**B is incorrect** because Admin Activity audit logs record administrative operations that modify Google Cloud resources, such as creating or updating a firewall policy or firewall rule. They can show who deployed the deny rule and when the configuration changed, but they do not record each data-plane connection evaluated against that rule. Consequently, reviewing only Admin Activity audit logs cannot show whether the deny rule matched network traffic or how many connections it denied.

**C is correct** because Firewall Rules Logging records connection information when traffic matches a firewall rule for which logging is enabled. For a relevant egress deny rule, the generated logs can identify the matched firewall rule, the source and destination details, the protocol and port, and the deny disposition. The analyst can query these records in Logs Explorer to confirm that the intended rule is being evaluated and denying connections. The analyst can also aggregate or count matching log entries to estimate how many connections are affected. Logging should be enabled specifically on the relevant rule to obtain useful evidence while avoiding unnecessary log volume and cost from unrelated firewall traffic.

**D is incorrect** because Cloud Storage object versioning preserves previous versions of objects when they are replaced or deleted in a bucket. It is a data-protection feature for stored objects and has no role in evaluating VM network traffic, recording firewall decisions, or identifying connections denied by an egress rule. Enabling it would not provide any evidence about whether the firewall rule is matching connections.

**Reference links**

- [docs.cloud.google.com/firewall/docs/firewall-rules-logging](https://docs.cloud.google.com/firewall/docs/firewall-rules-logging)
- [docs.cloud.google.com/firewall/docs/using-firewall-rules-logging](https://docs.cloud.google.com/firewall/docs/using-firewall-rules-logging)
- [docs.cloud.google.com/logging/docs/view/logs-explorer-interface](https://docs.cloud.google.com/logging/docs/view/logs-explorer-interface)

**Related notes:** [Firewall Rules Logging and VPC Flow Logs](../06-networking/products/firewall-rules-logging-and-vpc-flow-logs.md)

</details>

[Back to index](#index)

---

### Q28

Choose 2.

> DataBridge Logistics is developing an application that receives shipping files from 2,500 partner companies. The application must protect the uploaded data and automatically remove outdated files. Each partner must be able to access only its own data, receive write access for only 25 minutes, and have its files deleted after 60 days. The development schedule is short, and the solution must require minimal ongoing maintenance. Which two strategies should you use? (Choose two.)  

- **A.** Configure an Object Lifecycle Management rule to delete Cloud Storage objects after 60 days.
- **B.** Generate signed URLs that give each partner time-limited write access to its designated Cloud Storage objects.
- **C.** Deploy an SFTP server and create an individual operating-system user account for every partner.
- **D.** Deploy a Cloud Run function that starts a 60-day timer whenever an object is uploaded and deletes the object when the timer expires.
- **E.** Develop a scheduled script that examines every Cloud Storage bucket and deletes buckets created more than 60 days ago.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A, B

**Explanation**

**A is correct** because Cloud Storage Object Lifecycle Management is a native, server-side feature that automatically performs actions on objects when configured conditions are satisfied. An age-based lifecycle rule with the Delete action can remove objects after they reach 60 days of age. The company does not need to maintain a scheduler, database, timer, or custom cleanup application. Cloud Storage periodically evaluates the objects and performs eligible lifecycle actions asynchronously. This approach directly addresses the data-expiration requirement while minimizing development effort and operational maintenance. The lifecycle rule should be applied to the bucket containing the partner files, and the company should also review Cloud Storage soft-delete settings if the files must become immediately unrecoverable after lifecycle deletion.

**B is correct** because a signed URL provides limited, time-bound access to a specific Cloud Storage resource without requiring the partner to have a Google Cloud identity or permanent IAM permissions. The application can generate a signed URL that authorizes an upload operation to a unique object name assigned to that partner and configure the URL to expire after 25 minutes. Because each URL is generated for a specific object or upload destination, partners can upload only to the locations authorized by the application. After the expiration time, Cloud Storage rejects attempts to use the URL. This satisfies the temporary write-access requirement and supports supplier isolation without creating and maintaining thousands of Google Cloud accounts. The application must generate unpredictable, partner-specific object paths and must not expose another partner’s signed URLs.

**C is incorrect** because operating and securing an SFTP server would create substantial development and maintenance work. The company would need to provision and patch the server, manage storage capacity, maintain thousands of user accounts and credentials, configure directory isolation, monitor availability, and implement its own file-expiration process. Although separate SFTP users could restrict partners to their own directories, SFTP accounts do not natively provide 25-minute write authorization for individual uploads. This option conflicts with the short development cycle and minimal-maintenance requirements.

**D is incorrect** because starting and maintaining an individual 60-day timer for every uploaded object is unnecessary and difficult to operate reliably at scale. A Cloud Run function invocation cannot remain active for 60 days, so the company would need another service, such as Cloud Tasks, Workflows, or a database-backed scheduling mechanism, to store and execute the future deletion operations. The solution would also need retry handling, failure monitoring, duplicate-event handling, and logic for files that are replaced or deleted early. Cloud Storage Object Lifecycle Management already provides managed age-based deletion without this custom infrastructure.

**E is incorrect** because the requirement is to delete data objects after 60 days, not to delete entire buckets based on the buckets’ creation dates. A bucket can contain both recent and old objects, so deleting a 60-day-old bucket could remove files that were uploaded only recently. Conversely, keeping a newer bucket would leave objects older than 60 days undeleted. The script would also require scheduling, permissions, logging, retry handling, and ongoing maintenance. Object Lifecycle Management evaluates the age of each object independently and is therefore the appropriate managed solution.

**Reference links**

- [docs.cloud.google.com/storage/docs/lifecycle](https://docs.cloud.google.com/storage/docs/lifecycle)
- [docs.cloud.google.com/storage/docs/access-control/signed-urls](https://docs.cloud.google.com/storage/docs/access-control/signed-urls)
- [docs.cloud.google.com/storage/docs/access-control/signing-urls-with-helpers](https://docs.cloud.google.com/storage/docs/access-control/signing-urls-with-helpers)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q29

> PixelForge Media is launching a collaborative video-editing portal. The application uses a microservices architecture with several containers communicating through a service mesh. The infrastructure team must keep the number of underlying virtual machine instances constant rather than allowing the platform to add or remove compute capacity automatically. What should PixelForge Media do?  

- **A.** Create a Compute Engine instance template based on Container-Optimized OS, use a startup script to install Istio, deploy the containers, and run the template in a managed instance group configured with a fixed size.
- **B.** Create a Cloud Run service with configured minimum and maximum instance limits, connect it to Cloud Service Mesh, and deploy all application containers to that service.
- **C.** Create a Google Kubernetes Engine Autopilot cluster, enable Cloud Service Mesh, deploy the containers, and configure Vertical Pod Autoscaling and Horizontal Pod Autoscaling to maintain the required cluster capacity.
- **D.** Create a Google Kubernetes Engine Standard cluster with a node pool containing a fixed number of nodes, enable Cloud Service Mesh, and deploy the containerized application.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because although a fixed-size managed instance group can maintain a specific number of Compute Engine VM instances, manually installing Istio on Container-Optimized OS instances is not the appropriate architecture for this workload. Istio is primarily designed to manage service-to-service communication between workloads running on Kubernetes, where it can integrate with Kubernetes services, Pods, namespaces, traffic policies, and sidecar injection. Container-Optimized OS is a restricted operating system designed specifically for running containers and does not provide the conventional package-management environment expected by many installation scripts. The company would also have to build and maintain its own container scheduling, service discovery, health management, mesh configuration, rolling deployments, and workload recovery mechanisms. A managed instance group controls VM replicas but does not provide the Kubernetes orchestration capabilities needed to operate a multi-container microservices application efficiently.

**B is incorrect** because Cloud Run is a serverless platform that manages and scales its own compute instances according to incoming requests, configured minimum instances, maximum instances, concurrency, and available capacity. Minimum and maximum settings establish scaling boundaries rather than guaranteeing that a precise, fixed number of compute instances will always run. Cloud Run supports multi-container instances, but the containers deployed together belong to one Cloud Run service instance and generally form a tightly coupled group containing an ingress container and supporting sidecars. A microservices application whose independently managed containers communicate through a service mesh is more naturally deployed as multiple Kubernetes workloads. Cloud Service Mesh for Cloud Run can provide traffic management between Cloud Run services, but it does not give the company direct control over a fixed pool of underlying compute instances.

**C is incorrect** because GKE Autopilot automatically manages the cluster’s nodes and underlying compute infrastructure. Users specify workload requirements, such as Pod resource requests, while GKE provisions, scales, configures, and manages the required nodes. Horizontal Pod Autoscaling changes the number of Pod replicas based on workload metrics, while Vertical Pod Autoscaling adjusts the resources allocated to Pods. Neither mechanism provides direct control over a fixed number of underlying compute instances in an Autopilot cluster. Depending on the workloads and their resource requirements, Autopilot can add or remove compute capacity automatically. Autopilot is appropriate when the company wants Google Cloud to manage infrastructure capacity, but it does not meet a requirement to keep the number of compute nodes fixed.

**D is correct** because GKE Standard gives the company direct control over cluster node pools and their sizes. The infrastructure team can create a node pool with a specified number of nodes and leave cluster autoscaling disabled, thereby maintaining a fixed number of underlying Compute Engine instances during normal operation. GKE provides the container orchestration capabilities required by the application, including service discovery, workload scheduling, health checks, rolling deployments, configuration management, and Pod lifecycle management. Cloud Service Mesh integrates with GKE to provide service-to-service traffic management, observability, security policies, and mutual TLS capabilities for the application’s containerized services. This combination satisfies both requirements: Kubernetes and Cloud Service Mesh support the multi-container service architecture, while a fixed-size GKE Standard node pool provides control over the number of compute instances.

**Reference links**

- [docs.cloud.google.com/kubernetes-engine/docs/how-to/node-pools](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/node-pools)
- [docs.cloud.google.com/service-mesh/docs/onboarding/provision-control-plane](https://docs.cloud.google.com/service-mesh/docs/onboarding/provision-control-plane)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview)

**Related notes:** [GKE (Autopilot and Standard)](../03-compute-containers/products/gke.md) · [Cloud Service Mesh](../03-compute-containers/products/cloud-service-mesh.md)

</details>

[Back to index](#index)

---

### Q30

> AsterPeak Logistics discovers that 11 external contractor accounts have IAM access to resources in its Google Cloud organization. These accounts use email domains that are not associated with the company’s Google Workspace account. AsterPeak wants to remove the existing external principals and ensure that administrators cannot grant future access to identities outside the approved organization. The company also wants to avoid creating and maintaining a recurring access-scanning process. What should AsterPeak Logistics do?  

- **A.** Configure Cloud Scheduler to periodically scan every project and remove principals whose email addresses do not use the company’s domain.
- **B.** Configure Cloud Scheduler to periodically inspect individual Google Cloud resources and remove principals whose email addresses do not use the company’s domain.
- **C.** Enforce the Restrict allowed policy members in IAM allow policies organization policy constraint and rely on it to automatically revoke all existing external principals.
- **D.** Enforce the Restrict allowed policy members in IAM allow policies organization policy constraint, and separately remove the external principals from existing IAM allow policies.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because a scheduled project-scanning process is a custom reactive solution rather than a preventive control. It would require developing, securing, testing, and maintaining code that retrieves IAM allow policies, evaluates principal identities, and modifies role bindings. Scanning only projects could also miss IAM access granted at other points in the resource hierarchy, such as the organization or folder level, as well as access controlled directly on certain resources. The scheduled process would leave a period between scans during which an unauthorized external principal could retain access. Google Cloud Organization Policy provides a centralized and inherited preventive control that is better suited to stopping future role grants to unauthorized identities.

**B is incorrect** because periodically scanning individual resources would create significant operational complexity and would still be reactive. The company would need to account for the different IAM policy interfaces, permissions, resource types, inherited role bindings, error conditions, and newly introduced resources across the organization. The scanner would also need highly privileged permissions to inspect and modify IAM policies, which would create an additional sensitive administrative workload. Cloud Scheduler only initiates jobs at configured times; it does not natively evaluate whether IAM principals belong to an approved Google Workspace domain or remove them automatically. A domain-restricted sharing organization policy is the appropriate centralized mechanism for preventing future unauthorized role grants.

**C is incorrect** because domain-restricted sharing constraints are not retroactive. Enforcing the iam.managed.allowedPolicyMembers managed constraint, or the legacy iam.allowedPolicyMemberDomains constraint, prevents future IAM allow policy changes from granting roles to principals outside the configured organization, domains, principal sets, or explicit exceptions. However, principals that already received roles before the constraint was enforced retain those roles. The organization policy does not automatically search existing IAM allow policies and revoke noncompliant role bindings. Consequently, this option would prevent new mismatched principals from being added but would fail to remove the external users who already have access.

**D is correct** because it combines preventive enforcement with remediation of existing access. AsterPeak should enforce domain-restricted sharing at the organization level by using the current iam.managed.allowedPolicyMembers managed organization policy constraint and allowing the company’s organization principal set or other explicitly approved principals. Descendant folders and projects inherit the organization policy unless an authorized exception or override is configured. This prevents future IAM allow policy changes from granting roles to identities outside the approved organization. Because organization policy constraints do not apply retroactively, the company must also perform a one-time removal of existing external principals from the IAM allow policies where their roles were granted. After this cleanup, the organization policy prevents the same type of unauthorized grant from being created again, eliminating the need to operate a recurring Cloud Scheduler scanning and deletion process. The company should evaluate legitimate service agents, workload identities, and approved external accounts before removal and configure explicit exceptions where operationally required.

**Reference links**

- [docs.cloud.google.com/organization-policy/domain-restricted-sharing](https://docs.cloud.google.com/organization-policy/domain-restricted-sharing)
- [docs.cloud.google.com/organization-policy/restrict-domains](https://docs.cloud.google.com/organization-policy/restrict-domains)
- [docs.cloud.google.com/iam/docs/granting-changing-revoking-access](https://docs.cloud.google.com/iam/docs/granting-changing-revoking-access)

**Related notes:** [Organization Policy Service](../02-identity-security/products/organization-policy-service.md)

</details>

[Back to index](#index)

---

### Q31

> HarborCart operates an online grocery delivery platform and manages its Google Cloud resources with Terraform. Its Terraform configuration is maintained in a Git repository and updated by several platform engineers. HarborCart needs a shared Terraform state that prevents simultaneous updates from corrupting infrastructure and keeps state data containing sensitive values from being persistently stored on engineers’ workstations. What should HarborCart do?  

- **A.** Use the Terraform local backend and require engineers to apply changes through a shared user account on an administration VM.
- **B.** Configure the Terraform gcs backend to store the state in a secured Cloud Storage bucket.
- **C.** Use the Terraform local backend and commit the terraform.tfstate file to the Git repository.
- **D.** Use the Terraform local backend and distribute the latest state file to each engineer after every deployment.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because the local backend stores Terraform state on the machine where Terraform is executed. Moving execution to an administration VM does not provide a purpose-built remote state solution or reliable state locking, and using a shared account reduces accountability because actions cannot be clearly attributed to individual engineers. Team members would also depend on the availability and integrity of one VM. A dedicated Cloud Storage backend provides centralized state access, locking, IAM-based authorization, encryption, and auditable access without requiring shared credentials.

**B is correct** because the Terraform gcs backend stores the Terraform state centrally in a Cloud Storage bucket instead of persistently maintaining the authoritative state file on each engineer’s workstation. All authorized team members work with the same current state, and the gcs backend supports state locking, which prevents multiple Terraform operations from modifying the state simultaneously and potentially corrupting it. The bucket can be protected through IAM, uniform bucket-level access, encryption, versioning, retention controls, and audit logging. Because Terraform state can contain resource identifiers, credentials, generated passwords, and other sensitive values, access to the bucket should be limited to the deployment system and specifically authorized administrators. Backend credentials and other secrets should be supplied through Application Default Credentials or environment-based authentication rather than being hardcoded in Terraform files or backend command arguments.

**C is incorrect** because Terraform state can contain sensitive information in plaintext, even when Terraform variables or outputs are marked as sensitive. Committing terraform.tfstate to Git exposes that information to repository users and preserves it in commit history, where deleting the current file does not remove earlier versions. Git also does not provide Terraform-aware state locking. Two engineers could retrieve the same state, make separate infrastructure changes, and create conflicting commits or overwrite each other’s updates. The Git repository should contain the declarative Terraform configuration, while the operational state should be stored in a secured remote backend.

**D is incorrect** because manually distributing a local state file is slow, error-prone, and unable to guarantee that every engineer has the latest version. An engineer could run Terraform with an outdated state file and unintentionally recreate, modify, or delete resources. Manual sharing also provides no automatic locking, creates multiple uncontrolled copies of potentially sensitive state data, and makes access revocation and auditing difficult. A Cloud Storage backend centrally manages the authoritative state and coordinates concurrent operations automatically.

**Reference links**

- [docs.cloud.google.com/docs/terraform/best-practices/security](https://docs.cloud.google.com/docs/terraform/best-practices/security)
- [docs.cloud.google.com/docs/terraform/resource-management/store-state](https://docs.cloud.google.com/docs/terraform/resource-management/store-state)
- [developer.hashicorp.com/terraform/language/backend/gcs](https://developer.hashicorp.com/terraform/language/backend/gcs)

**Related notes:** [Terraform](../08-iac-platform-ai/products/terraform.md)

</details>

[Back to index](#index)

---

### Q32

> Skyline Analytics needs to provision identical networking, Compute Engine, and Cloud Storage resources across its development, staging, and production projects. The platform team wants to manage these resources as Infrastructure as Code while avoiding duplicated configuration. What should the team do?  

- **A.** Create reusable Terraform modules for the environment and deploy them with Infrastructure Manager.
- **B.** Use curl commands to send separate REST requests to the appropriate Google Cloud API for every resource.
- **C.** Provision and manage each resource manually through the Google Cloud console.
- **D.** Create a bash script containing a sequence of gcloud CLI commands for all required resources.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because Infrastructure Manager is Google Cloud’s managed Infrastructure as Code service for deploying and managing resources defined in Terraform configurations. Terraform modules allow related resources to be packaged into reusable components with configurable input variables and outputs. The platform team can define common networking, compute, storage, and IAM patterns once and invoke the same modules for development, staging, and production with different parameter values. This minimizes repetitive code, improves consistency, supports version control and code review, and makes environments reproducible. Terraform also uses a declarative approach in which the configuration describes the intended state of the infrastructure, while Infrastructure Manager handles deployment execution and state management.

**B is incorrect** because individual REST API requests are an imperative and low-level method of provisioning resources. The team would need to construct, authenticate, order, and maintain a separate request for each resource and operation. It would also need to develop custom logic for dependencies, retries, updates, deletions, error handling, and determining whether resources already exist. Although REST APIs can create Google Cloud resources, they do not inherently provide reusable Infrastructure as Code modules or declarative state management. This approach would result in substantial repetitive code and ongoing maintenance.

**C is incorrect** because manually provisioning resources through the Google Cloud console does not implement Infrastructure as Code. Console-based changes are difficult to reproduce consistently across multiple projects and environments, and they can lead to configuration drift when administrators make different changes in each environment. Manual provisioning also provides limited opportunities for automated testing, peer review, version control, and repeatable deployment. The Google Cloud console is useful for exploration and individual administrative tasks, but it is not the recommended solution for standardizing a large, repeatable infrastructure configuration.

**D is incorrect** because a bash script containing gcloud CLI commands can automate resource creation, but it remains primarily an imperative sequence of commands rather than a declarative Infrastructure as Code configuration. The team would need to implement its own resource-existence checks, dependency ordering, update behavior, rollback handling, error recovery, and idempotency. As the environment grows, the script could become lengthy, fragile, and repetitive. Reusable Terraform modules deployed through Infrastructure Manager provide stronger abstraction, dependency management, state tracking, repeatability, and maintainability.

**Reference links**

- [docs.cloud.google.com/infrastructure-manager/docs/overview](https://docs.cloud.google.com/infrastructure-manager/docs/overview)
- [docs.cloud.google.com/docs/terraform/blueprints/terraform-blueprints](https://docs.cloud.google.com/docs/terraform/blueprints/terraform-blueprints)
- [docs.cloud.google.com/docs/terraform/terraform-overview](https://docs.cloud.google.com/docs/terraform/terraform-overview)

**Related notes:** [Infrastructure Manager](../08-iac-platform-ai/products/infrastructure-manager.md) · [Terraform](../08-iac-platform-ai/products/terraform.md)

</details>

[Back to index](#index)

---

### Q33

> TicketNest, an event-booking platform, runs its web service on Cloud Run and connects to a Cloud SQL database. During an evening ticket-release surge, Cloud SQL logs report Cloud SQL Admin API quota errors. The project is already using the highest available API quota, so the team must reduce the quota consumed by the Cloud Run service through a configuration change. What should the team do?  

- **A.** Increase the minimum number of Cloud Run instances.
- **B.** Split incoming traffic between multiple Cloud Run revisions.
- **C.** Set a maximum number of Cloud Run instances.
- **D.** Define a minimum concurrent requests environment variable for the application.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the minimum instances setting specifies how many Cloud Run instances must remain running even when traffic is low. Increasing this setting keeps more instances active and can increase the number of instances establishing Cloud SQL connections. When Cloud Run uses its built-in Cloud SQL integration, the underlying Cloud SQL Auth Proxy uses the Cloud SQL Admin API. Keeping additional instances running would therefore not cap API consumption and could make the quota problem worse. Minimum instances are mainly used to reduce startup latency and maintain warm capacity, not to protect a downstream service from excessive API usage.

**B is incorrect** because traffic splitting controls how requests are distributed among Cloud Run revisions, usually for gradual rollouts, canary deployments, or A/B testing. It does not impose a limit on the total number of Cloud Run instances. Multiple revisions receiving traffic can scale independently, and the combined instance count can still generate enough Cloud SQL Admin API requests to exceed the project quota. Traffic splitting changes which revision processes a request but does not directly restrict overall scaling or Cloud SQL API consumption.

**C is correct** because setting a maximum number of Cloud Run instances places a cap on how far the service can scale during the traffic spike. Cloud Run’s built-in Cloud SQL connection mechanism uses the Cloud SQL Auth Proxy, which calls the Cloud SQL Admin API. The approximate API quota consumption depends on both the number of Cloud SQL instances configured for the service and the number of active Cloud Run instances. Limiting the maximum Cloud Run instance count therefore limits the number of proxy instances that can make Cloud SQL Admin API calls and helps keep usage within the available quota. The maximum should be selected carefully because requests might be delayed or rejected when traffic requires more instances than the configured limit, but this is the appropriate configuration change when the Cloud SQL API quota cannot be increased.

**D is incorrect** because Cloud Run does not use a minimum concurrent requests environment variable as an autoscaling control. Cloud Run provides a maximum concurrent requests per instance setting, commonly called concurrency, which determines how many simultaneous requests an individual instance can process. Environment variables are application configuration values and do not directly control Cloud Run autoscaling unless the application itself is specifically programmed to interpret them. Although properly increasing Cloud Run concurrency may allow each instance to process more requests and can sometimes reduce the required instance count, the option describes a nonexistent minimum-concurrency environment variable and does not directly cap the number of instances or the Cloud SQL Admin API quota consumed.

**Reference links**

- [docs.cloud.google.com/sql/docs/mysql/connect-run](https://docs.cloud.google.com/sql/docs/mysql/connect-run)
- [docs.cloud.google.com/run/docs/configuring/max-instances](https://docs.cloud.google.com/run/docs/configuring/max-instances)
- [docs.cloud.google.com/run/docs/about-concurrency](https://docs.cloud.google.com/run/docs/about-concurrency)

**Related notes:** [Cloud Run (service, job, and functions)](../03-compute-containers/products/cloud-run.md)

</details>

[Back to index](#index)

---

### Q34

> BlueHarbor Analytics operates five isolated VPC networks in a single Google Cloud project. Its security team needs to enforce an identical collection of Layer 3 and Layer 4 traffic-control rules across all five networks. The team wants to maintain the rules in one place so that a policy change is automatically effective for every associated network. Which solution should the cloud architect implement?  

- **A.** Create one global network firewall policy and associate it with all five VPC networks
- **B.** Assign the same network tag to resources across every project in the organization
- **C.** Provision a separate Cloud Router for each traffic-control rule
- **D.** Attach a Cloud Armor security policy directly to every VM network interface

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a global network firewall policy is designed to provide a centrally managed set of firewall rules that can be associated with multiple VPC networks in the same project. The policy can contain reusable ingress and egress rules that evaluate Layer 3 and Layer 4 attributes, including source and destination IP ranges, protocols, and ports. When administrators modify a rule in the policy, the change applies to every VPC network associated with that policy, eliminating the need to create and synchronize separate VPC firewall rules in each network. A VPC network can be associated with only one global network firewall policy, but the same global network firewall policy can be associated with multiple VPC networks as long as the policy and networks belong to the same project. This directly satisfies the requirement for centralized rule administration and reuse across the five networks.

**B is incorrect** because a network tag identifies VM instances or network interfaces that should be targeted by particular firewall rules; it is not a reusable firewall policy. Assigning the same text value as a network tag to resources does not create, distribute, or synchronize firewall rules. Traditional VPC firewall rules that use network tags remain scoped to the VPC network in which those rules are created. Therefore, separate rules would still have to be created and maintained in every VPC network. In addition, network tags are assigned to applicable resources rather than copied to projects as an organization-wide security construct. For centrally controlled policies across an organization, folders, or projects, hierarchical firewall policies could be considered, but they are not the construct described in this same-project, multiple-network requirement.

**C is incorrect** because Cloud Router provides dynamic route exchange by using Border Gateway Protocol. It is commonly used with Cloud VPN, Cloud Interconnect, Network Connectivity Center, and router appliances to learn and advertise network routes. Cloud Router does not define allow or deny rules, inspect traffic against Layer 3 or Layer 4 firewall criteria, or act as a container for firewall rules. Creating a separate Cloud Router for each rule would neither enforce the required security controls nor provide centralized firewall-policy management.

**D is incorrect** because Cloud Armor security policies are primarily used to protect externally accessible applications and services through supported load-balancing and edge configurations. Depending on the policy type, Cloud Armor can evaluate Layer 3 through Layer 7 attributes and provide capabilities such as distributed denial-of-service protection, web application firewall rules, IP-based access controls, and rate limiting. However, a Cloud Armor security policy is not attached directly to VM network interfaces as a reusable firewall policy for multiple VPC networks. Cloud Armor network edge security policies can protect supported external passthrough Network Load Balancers, protocol forwarding configurations, and certain VMs with public IP addresses, but they do not replace a global network firewall policy for general ingress and egress control across several VPC networks.

**Reference links**

- [docs.cloud.google.com/firewall/docs/network-firewall-policies](https://docs.cloud.google.com/firewall/docs/network-firewall-policies)
- [docs.cloud.google.com/vpc/docs/add-remove-network-tags](https://docs.cloud.google.com/vpc/docs/add-remove-network-tags)
- [docs.cloud.google.com/armor/docs/security-policy-overview](https://docs.cloud.google.com/armor/docs/security-policy-overview)

**Related notes:** [Firewall, Hierarchical Policies, and Secure Tags (Cloud NGFW)](../06-networking/products/firewall-hierarchical-policies-and-secure-tags.md)

</details>

[Back to index](#index)

---

### Q35

> CloudVista Media operates its customer-facing platform in a dedicated Google Cloud production project, while engineering teams use separate projects for development and quality assurance. The site reliability engineering team needs permissions across several production services. You must ensure that future Google Cloud service updates do not automatically expand the team’s permissions, while following the principle of least privilege. What should you do?  

- **A.** Grant the Editor role to every site reliability engineering team member at the organization level.
- **B.** Grant the Editor role to every site reliability engineering team member on the production project.
- **C.** Create a custom role containing only the required permissions, and grant the custom role to the site reliability engineering team on the production project.
- **D.** Create a custom role containing only the required permissions, and grant the custom role to the site reliability engineering team at the organization level.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because the Editor basic role contains a broad set of permissions across numerous Google Cloud services and is not recommended for production environments when more limited roles can meet the requirement. Granting it at the organization level would make the role effective throughout the resource hierarchy, including the production, development, and testing projects. This would give the site reliability engineering team substantially more access than required. Basic roles can also change as Google Cloud services evolve, so this approach does not provide tight control over the team’s future permissions.

**B is incorrect** because granting the Editor role on the production project limits its scope more appropriately than an organization-level grant, but the role is still excessively broad. The Editor role includes permissions for creating, modifying, and deleting many types of resources, including permissions unrelated to the team’s actual responsibilities. Because Google maintains basic roles and can update their permissions as products and features evolve, this option does not satisfy the requirement to prevent future Google Cloud changes from broadening the team’s permissions.

**C is correct** because a custom role allows the company to select only the specific IAM permissions that the site reliability engineering team requires. New permissions introduced by Google Cloud are not automatically added to an existing custom role, so the company retains control over any future permission changes. Granting the custom role on the production project makes the permissions effective for supported resources within that project while preventing the team from receiving the same access to unrelated development and testing projects. This combination follows the principle of least privilege and directly addresses both the required permission stability and the required production-only scope. The company should periodically review the custom role because permissions can be deprecated or replaced as services evolve.

**D is incorrect** because creating a custom role would prevent newly introduced permissions from being automatically added, but granting that role at the organization level would make its permissions effective across descendant resources. The site reliability engineering team would consequently receive those permissions in the production project as well as the development and testing projects. Because the team requires this access only for production services, the organization-level grant is broader than necessary and violates the principle of least privilege.

**Reference links**

- [docs.cloud.google.com/iam/docs/choose-role-type](https://docs.cloud.google.com/iam/docs/choose-role-type)
- [docs.cloud.google.com/iam/docs/permissions-change-log](https://docs.cloud.google.com/iam/docs/permissions-change-log)
- [docs.cloud.google.com/iam/docs/resource-hierarchy-access-control](https://docs.cloud.google.com/iam/docs/resource-hierarchy-access-control)

**Related notes:** [IAM (roles, bindings, and service accounts)](../02-identity-security/products/iam.md)

</details>

[Back to index](#index)

---

### Q36

> VaultBridge stores confidential legal documents in a private Cloud Storage bucket. Compliance auditors require the company to maintain a record whenever an authorized principal reads an object from the bucket. Which action should VaultBridge take?  

- **A.** Enable the Identity-Aware Proxy API for the project.
- **B.** Inspect the bucket by using Sensitive Data Protection.
- **C.** Grant object-read access only to one service account.
- **D.** Enable Data Access audit logs for the Cloud Storage API.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** D

**Explanation**

**A is incorrect** because Identity-Aware Proxy controls access to applications and administrative services by verifying user identity and IAM authorization. It can protect resources such as web applications and TCP connections, but it does not enable audit logging for Cloud Storage object-read operations. Enabling the Identity-Aware Proxy API would therefore not produce the required record of each request that reads an object from the bucket.

**B is incorrect** because Sensitive Data Protection discovers, classifies, and helps protect sensitive information. It can inspect Cloud Storage objects for data types such as personal information, credentials, and financial identifiers, but it does not provide a continuous audit record of every request that reads an object. Scanning the bucket can help determine what sensitive data is stored, but it does not satisfy the legal access-logging requirement.

**C is incorrect** because limiting access to a single service account reduces the number of identities that can read the objects, but it does not automatically create the required audit trail. Multiple applications or people could also use the same service account, making individual accountability more difficult. Least-privilege IAM permissions should still be applied, but restricting access alone does not record when objects are read.

**D is correct** because Cloud Audit Logs Data Access logs record user-driven API operations that read user-provided data. For Cloud Storage, DATA_READ audit logs capture operations that read object data. These logs are disabled by default for Cloud Storage and must be explicitly enabled for the Cloud Storage service. To support the compliance requirement, VaultBridge should enable the DATA_READ log type, avoid configuring exempted principals, prevent public or anonymous bucket access, and retain or route the logs according to its legal retention policy. Publicly accessible resources do not generate Data Access audit logs, so the sensitive bucket should remain private and require authenticated access.

**Reference links**

- [docs.cloud.google.com/storage/docs/audit-logging](https://docs.cloud.google.com/storage/docs/audit-logging)
- [docs.cloud.google.com/logging/docs/audit/configure-data-access](https://docs.cloud.google.com/logging/docs/audit/configure-data-access)
- [docs.cloud.google.com/logging/docs/audit](https://docs.cloud.google.com/logging/docs/audit)

**Related notes:** [Cloud Audit Logs](../02-identity-security/products/cloud-audit-logs.md)

</details>

[Back to index](#index)

---

### Q37

> Northstar Retail is running its order-processing application on a Compute Engine VM named orders-prod-vm. The operations team wants to prevent an administrator from accidentally deleting the VM from the Google Cloud console. What should the team do?  

- **A.** Disable the Delete boot disk when instance is deleted setting.
- **B.** Enable deletion protection on orders-prod-vm.
- **C.** Disable automatic restart on orders-prod-vm.
- **D.** Provision orders-prod-vm as a Spot VM.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because disabling the Delete boot disk when instance is deleted setting protects only the attached boot disk after the VM is deleted. It does not prevent the VM instance itself from being deleted. If an administrator accidentally deletes orders-prod-vm, the VM configuration and instance resource are still removed, although the preserved boot disk could potentially be used to create another VM. This setting is useful for preserving data, but it does not satisfy the requirement to block accidental VM deletion.

**B is correct** because Compute Engine deletion protection prevents the VM from being deleted until the deletion protection setting is explicitly disabled. When deletion protection is enabled on orders-prod-vm, an administrator who accidentally selects the delete action cannot immediately remove the instance. The administrator must first deliberately disable deletion protection and then perform the deletion, which adds an effective safeguard against accidental clicks or unintended automation. Deletion protection does not prevent the VM from being stopped, restarted, reset, or modified, and it does not protect the VM if the entire Google Cloud project is deleted.

**C is incorrect** because automatic restart controls whether Compute Engine attempts to restart a VM after certain infrastructure failures or host-related termination events. Disabling automatic restart can reduce the VM’s availability after such an event, but it does not restrict administrators from deleting the VM through the console, Google Cloud CLI, API, or other management tools. This setting addresses availability behavior rather than accidental deletion.

**D is incorrect** because Spot VMs are designed for fault-tolerant and interruptible workloads and can be stopped or deleted by Compute Engine when capacity is needed. They are offered at reduced prices but do not provide guaranteed availability. Configuring a production application VM as a Spot VM would increase the likelihood of interruption and would not prevent an administrator from manually deleting it. Therefore, this option works against the application’s production availability requirements and does not provide deletion protection.

**Reference links**

- [docs.cloud.google.com/compute/docs/instances/preventing-accidental-vm-deletion](https://docs.cloud.google.com/compute/docs/instances/preventing-accidental-vm-deletion)
- [docs.cloud.google.com/compute/docs/disks/modify-persistent-disk](https://docs.cloud.google.com/compute/docs/disks/modify-persistent-disk)
- [docs.cloud.google.com/compute/docs/instances/spot](https://docs.cloud.google.com/compute/docs/instances/spot)

**Related notes:** [Compute Engine](../03-compute-containers/products/compute-engine.md)

</details>

[Back to index](#index)

---

### Q38

> GlobeCart operates an international online marketplace and plans to modernize three existing data platforms as mentioned below. GlobeCart wants Google Cloud services that can scale globally while minimizing infrastructure provisioning, capacity planning, maintenance, and operational administration. Which migration plan should GlobeCart choose?  
> -A MySQL cluster that stores customer orders and payment transactions  
> -An Apache Kafka platform that distributes real-time inventory and shipping events  
> -A Cloud SQL for PostgreSQL database used for large analytical queries and business reports  

- **A.** Migrate MySQL to Cloud SQL, Apache Kafka to Pub/Sub, and Cloud SQL for PostgreSQL to BigQuery.
- **B.** Migrate MySQL to Spanner, Apache Kafka to Pub/Sub, and Cloud SQL for PostgreSQL to BigQuery.
- **C.** Migrate MySQL to Spanner, Apache Kafka to Memorystore, and Cloud SQL for PostgreSQL to Cloud SQL.
- **D.** Migrate MySQL to Cloud SQL, Apache Kafka to Memorystore, and Cloud SQL for PostgreSQL to Cloud SQL.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because migrating Apache Kafka to Pub/Sub and moving the analytical workload to BigQuery are appropriate choices, but Cloud SQL does not fully satisfy the global scalability requirement for the primary transactional database. Cloud SQL is a managed relational database service that supports MySQL, PostgreSQL, and SQL Server, and it significantly reduces database administration compared with self-managed databases. However, an individual Cloud SQL instance is deployed in a particular region and does not provide the same transparent, horizontally scalable, globally distributed architecture as Spanner. Read replicas can distribute read workloads, including across regions, but the primary write workload remains associated with the primary instance. Therefore, Cloud SQL is suitable for many regional relational applications, but Spanner is the stronger choice when global transactional scalability is a central requirement.

**B is correct** because each proposed service aligns with the corresponding workload and the requirements for global scalability and minimal operational management. Spanner is a fully managed, horizontally scalable database that provides relational capabilities, strong transactional consistency, synchronous replication, and regional, dual-region, and multi-region configurations. It is therefore appropriate for replacing a MySQL cluster that supports a globally expanding transactional application. Pub/Sub is a fully managed, scalable asynchronous messaging service that decouples message producers from consumers, making it an appropriate Google Cloud-native replacement for many Apache Kafka event-distribution and streaming scenarios without requiring the company to provision and operate Kafka brokers. BigQuery is a fully managed, serverless analytical data platform designed for large-scale reporting and analytical queries. Unlike an operational PostgreSQL database, BigQuery automatically manages the underlying analytical infrastructure and can process very large datasets without requiring database server administration. Together, Spanner, Pub/Sub, and BigQuery provide the most suitable Google-recommended architecture among the available choices.

**C is incorrect** because Spanner is an appropriate globally scalable transactional database, but Memorystore is not a direct replacement for Apache Kafka, and Cloud SQL is not the best destination for a large analytical and reporting workload. Memorystore is a managed in-memory data store based on technologies such as Redis, Valkey, and Memcached. It is primarily intended for caching, session storage, leaderboards, temporary data, and other low-latency in-memory use cases. It does not provide the durable publish-and-subscribe event-streaming model, independent subscriptions, message retention behavior, and scalable asynchronous integration capabilities expected from Kafka or Pub/Sub. Retaining the analytical workload in Cloud SQL would also continue to place reporting queries on a relational operational database that requires instance sizing and capacity management. BigQuery is better suited to serverless, large-scale analytics.

**D is incorrect** because none of the selected services fully addresses the intended modernization requirements. Cloud SQL reduces management compared with an on-premises MySQL cluster, but it does not offer the same globally distributed horizontal scalability as Spanner. Memorystore is an in-memory caching and data-serving platform rather than an event-streaming service, so it is not an appropriate replacement for Apache Kafka. Keeping analytical and reporting workloads in Cloud SQL also fails to take advantage of BigQuery’s serverless analytical architecture, independent compute capabilities, and ability to process large datasets efficiently. This option would therefore provide less global scalability and require more capacity and infrastructure management than the combination of Spanner, Pub/Sub, and BigQuery.

**Reference links**

- [docs.cloud.google.com/spanner/docs](https://docs.cloud.google.com/spanner/docs)
- [docs.cloud.google.com/pubsub/docs/overview](https://docs.cloud.google.com/pubsub/docs/overview)
- [docs.cloud.google.com/bigquery/docs/introduction](https://docs.cloud.google.com/bigquery/docs/introduction)

</details>

[Back to index](#index)

---

### Q39

> PulseCart, an online retail platform, stores application logs in Cloud Logging. Its analytics team wants to run SQL queries against these logs and combine the results with business data in BigQuery. The team wants to use Google’s recommended architecture without maintaining a separate log-export pipeline. What should the team do?  

- **A.** Use Gemini for Google Cloud to generate SQL queries for the application logs.
- **B.** Upgrade the log bucket to use Observability Analytics and create a linked BigQuery dataset.
- **C.** Define a schema for the Cloud Logging bucket and query the bucket directly with SQL.
- **D.** Route the logs to a Cloud Storage bucket and create an external view in BigQuery.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Gemini for Google Cloud can assist users with tasks such as explaining code, generating SQL, and suggesting query improvements, but it does not make Cloud Logging data directly available for SQL analysis. Before SQL queries can analyze the logs, the underlying log bucket must support Observability Analytics or the logs must be moved to another supported analytics destination. Gemini can help write a query after the data is accessible, but it does not replace the required integration between Cloud Logging and BigQuery.

**B is correct** because Observability Analytics is Google Cloud’s recommended capability for running SQL queries directly against log data stored in Cloud Logging. The team should upgrade the relevant log bucket to use Observability Analytics and then create a linked BigQuery dataset for that bucket. The linked dataset allows BigQuery to read the logs while Cloud Logging continues to store and manage the underlying data. It avoids creating a separate copy of the logs through an export pipeline and lets analysts use BigQuery services, BigQuery Studio, and Looker Studio to analyze the logs or combine them with other business datasets. Log views in the upgraded bucket are represented as views in the linked dataset, and BigQuery permissions control access when users query them through BigQuery.

**C is incorrect** because a Cloud Logging log bucket is not a Cloud Storage bucket for which users manually define a file schema. Cloud Logging manages the organization and storage format of log entries. Users cannot make a log bucket SQL-queryable merely by creating a schema for it. To perform SQL analysis while keeping the logs in Cloud Logging, the bucket must be upgraded to use Observability Analytics. A linked BigQuery dataset can then expose the relevant log views through a BigQuery-compatible interface.

**D is incorrect** because exporting logs to Cloud Storage introduces an additional storage and data-processing workflow that is unnecessary for this requirement. Cloud Storage exports are commonly used for archival or downstream batch processing, and the exported data might require transformation, partition handling, schema management, or external-table configuration before it can be efficiently queried. In addition, BigQuery normally queries Cloud Storage data through external tables rather than an external view alone. Google’s recommended approach for SQL analysis of logs already stored in Cloud Logging is to use Observability Analytics and, when BigQuery access is required, create a linked BigQuery dataset without exporting or duplicating the logs.

**Reference links**

- [docs.cloud.google.com/logging/docs/analyze/query-and-view](https://docs.cloud.google.com/logging/docs/analyze/query-and-view)
- [docs.cloud.google.com/logging/docs/analyze/query-linked-dataset](https://docs.cloud.google.com/logging/docs/analyze/query-linked-dataset)
- [docs.cloud.google.com/logging/docs/buckets](https://docs.cloud.google.com/logging/docs/buckets)

**Related notes:** [Observability Analytics](../07-operations-cost/products/observability-analytics.md)

</details>

[Back to index](#index)

---

### Q40

> Northwind Health hosts a patient portal on a Compute Engine VM. A project administrator creates a VPC firewall rule that allows TCP port 8443 from a trusted medical-services provider. Connections are still blocked, and the effective firewall view identifies a matching deny rule in a hierarchical firewall policy associated with the organization. The organization-level rule is evaluated before the project’s VPC firewall rule. What should the administrator determine?  

- **A.** The project-level allow rule overrides the organization policy because it is configured closer to the VM.
- **B.** The organization-level policy denies the connection; the central security team must change that rule or delegate evaluation with an approved action such as goto_next where appropriate.
- **C.** Assigning a larger numeric priority value to the VPC firewall rule makes it override the organization-level rule.
- **D.** Restarting the Compute Engine VM causes the project-level allow rule to be evaluated first.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because hierarchical firewall policies associated with an organization or folder are evaluated according to the Google Cloud firewall policy and rule evaluation order, not according to which rule appears physically closer to the VM. An organization-level hierarchical firewall policy is inherited by the projects and VPC networks beneath that organization. When a matching hierarchical firewall policy rule has a terminal deny action, evaluation stops and the connection is denied. Google Cloud does not continue to a project-level VPC firewall allow rule after such a matching deny. Resource proximity therefore does not give the project rule precedence over the inherited organization policy.

**B is correct** because the effective firewall view confirms that the organization-level hierarchical firewall policy contains the matching rule that denies the connection. A deny action is terminal: after the rule matches, Google Cloud denies the new connection and does not evaluate lower stages such as the project’s VPC firewall rules. The project administrator cannot override that decision merely by adding another local allow rule. The administrator must work with the central security team that manages the ancestor policy. That team could modify the deny rule, narrow its matching criteria, add an appropriate higher-precedence allow rule within the hierarchical policy, or use goto_next when delegation to lower-level firewall policies or VPC firewall rules is intended. The goto_next action is not an allow action by itself; it tells Google Cloud to stop evaluating the current policy and continue to the next applicable stage in the firewall evaluation order.

**C is incorrect** because a rule’s numeric priority determines evaluation order among rules within the relevant policy or rule set; it does not let a project-level VPC firewall rule jump ahead of a matching terminal rule in an organization-level hierarchical firewall policy. In Google Cloud firewall rules, smaller numeric values represent higher priorities, with priority 0 being the highest. Therefore, increasing the VPC rule’s numeric value would ordinarily give it lower priority within its own rule set, not greater priority. More importantly, changing the project rule’s priority cannot override the separate evaluation stage of the organization-level hierarchical policy. The ancestor deny must be changed or must delegate evaluation before the VPC firewall allow rule can affect the connection.

**D is incorrect** because firewall policy precedence is determined by policy associations, rule matching, actions, and the documented evaluation order. It is not determined by the VM’s boot state or restart history. VPC firewall enforcement is implemented by Google Cloud’s networking infrastructure and applies independently of the VM’s guest operating system. Restarting the VM does not change an inherited hierarchical firewall policy, convert a deny action into goto_next, or move a project-level VPC firewall rule ahead of an organization-level rule. The connection will continue to be denied until the applicable firewall configuration is changed.

**Reference links**

- [docs.cloud.google.com/firewall/docs/firewall-policies-rule-eval-order](https://docs.cloud.google.com/firewall/docs/firewall-policies-rule-eval-order)
- [docs.cloud.google.com/firewall/docs/firewall-policies](https://docs.cloud.google.com/firewall/docs/firewall-policies)
- [docs.cloud.google.com/firewall/docs/firewall-policies-rule-details](https://docs.cloud.google.com/firewall/docs/firewall-policies-rule-details)

**Related notes:** [Firewall, Hierarchical Policies, and Secure Tags (Cloud NGFW)](../06-networking/products/firewall-hierarchical-policies-and-secure-tags.md)

</details>

[Back to index](#index)

---

### Q41

> BrightCart operates order-processing applications on Compute Engine in a Google Cloud VPC network. The VPC is connected through a Cloud VPN tunnel to BrightCart’s on-premises data center, where an inventory database is hosted. Several applications must connect to this database, but the database’s private IP address might change during maintenance. BrightCart wants to update the connection information in one place instead of modifying every application. What should BrightCart do?  

- **A.** Enable Cloud NAT for every subnet containing the application VM instances.
- **B.** Create a private zone in Cloud DNS, add a DNS record for the database, and configure the applications to use the DNS name.
- **C.** Store the database IP address as custom metadata on every VM instance and have each application query the metadata server.
- **D.** Have the applications query Compute Engine internal DNS to automatically discover the on-premises database address.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Cloud NAT performs network address translation for traffic originating from supported Google Cloud resources. It can provide source NAT for outbound internet access or private address translation in specific private networking scenarios, but it does not provide a stable logical name for a changing destination IP address. The applications would still need to know either the database’s current IP address or a hostname that resolves to that address. Enabling Cloud NAT on the application subnets would therefore not eliminate the need to update application configurations when the database IP changes. The existing Cloud VPN tunnel and associated routes already provide the network path between the VPC and the on-premises network.

**B is correct** because a Cloud DNS private zone provides centrally managed DNS records that are visible only to authorized VPC networks. BrightCart can create a record such as inventory-db.corp.internal and map it to the database server’s current private IP address. Every application can then use that DNS name instead of embedding the IP address in its configuration. When the on-premises database receives a different IP address, an administrator only needs to update the record in Cloud DNS. After the record’s time to live and any DNS caches expire, applications resolve the same name to the new address without requiring configuration changes on every application instance. Cloud DNS supplies the required name-to-address abstraction, while Cloud VPN continues to provide connectivity to the resolved on-premises address.

**C is incorrect** because custom metadata can store arbitrary key-value configuration data, and an application running on a Compute Engine VM can retrieve that data from the metadata server. However, the option requires the database address to be configured separately on every VM instance. When the database IP changes, administrators would need to update metadata across all affected instances, which recreates the distributed configuration problem described in the question. It also couples the application to the Compute Engine metadata API and is less suitable for standard endpoint discovery than DNS. Cloud DNS provides a single record that all applications can resolve using normal DNS mechanisms.

**D is incorrect** because Compute Engine internal DNS automatically creates and manages DNS records for Google Cloud resources such as Compute Engine VM instances. It does not automatically discover an arbitrary database server located in an on-premises network or create a DNS record for that server. The applications cannot obtain the on-premises database’s address merely by querying Compute Engine internal DNS. An explicit Cloud DNS private-zone record, a forwarding-zone configuration, or another hybrid DNS arrangement must exist before the on-premises hostname can be resolved. In this scenario, creating a private Cloud DNS record is the simplest appropriate solution.

**Reference links**

- [docs.cloud.google.com/dns/docs/zones/zones-overview](https://docs.cloud.google.com/dns/docs/zones/zones-overview)
- [docs.cloud.google.com/compute/docs/internal-dns](https://docs.cloud.google.com/compute/docs/internal-dns)
- [docs.cloud.google.com/nat/docs/overview](https://docs.cloud.google.com/nat/docs/overview)

**Related notes:** [Cloud Router, Cloud VPN, and Cloud Interconnect](../06-networking/products/cloud-router-cloud-vpn-and-cloud-interconnect.md)

</details>

[Back to index](#index)

---

### Q42

Choose 2.

> BrightPath Health runs patient-processing and analytics VMs in multiple Google Cloud projects. The workloads are frequently replaced, causing their internal IP addresses to change. The security team must ensure that analytics services can connect to patient-data servers only when both workloads have approved identities. The access model must be centrally controlled and should not depend on maintaining IP address lists. Which two actions should the team take? (Choose two.)  

- **A.** Define secure tags for the analytics and patient-data workload identities, and strictly control the IAM permissions used to create tag bindings.
- **B.** Configure firewall policies to identify workloads exclusively by their Compute Engine instance names.
- **C.** Create Cloud NGFW firewall policy rules that use the analytics secure tag as the source and the patient-data secure tag as the target.
- **D.** Permit all addresses in the 10.0.0.0/8 range to connect to the patient-data service port.
- **E.** Assign external IP addresses to the patient-data VMs and keep their addresses undisclosed.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A, C

**Explanation**

**A is correct** because secure tags provide centrally managed, identity-based labels that can be bound to Compute Engine VM network interfaces and referenced by Cloud NGFW firewall policy rules. Unlike IP addresses, secure tag identities remain meaningful when workloads are recreated, moved, or assigned different addresses. The team can create separate tag values representing approved analytics clients and protected patient-data servers. IAM permissions for creating and modifying tag bindings must be tightly restricted because a user who can bind the approved analytics tag to an unauthorized VM could cause that VM to match an allow rule. Central control of tag creation and binding therefore makes the workload identity trustworthy and supports durable segmentation across projects.

**B is incorrect** because Compute Engine VM names are not supported as source or target identity selectors in Cloud NGFW firewall rules. Instance names are administrative identifiers rather than centrally governed security identities, and names can be reused or changed when workloads are recreated. Depending on VM names would therefore neither provide a valid firewall match condition nor establish reliable authorization. Secure tags are specifically designed to represent workload identity in firewall policies and are protected through IAM-controlled tag-binding operations.

**C is correct** because Cloud NGFW firewall policy rules can reference secure tags as both source and target selectors. The security team can create an ingress allow rule that permits the required application protocol and database port only when traffic originates from a VM carrying the approved analytics tag and is directed to a VM carrying the patient-data tag. The policy can be centrally managed through an appropriate hierarchical or network firewall policy, depending on the organization’s design. Because the rule evaluates workload identity rather than manually maintained address ranges, it continues to work when instances are recreated and their IP addresses change. Other traffic can remain denied through higher-priority rules, lower-priority rules, or the applicable implied deny behavior.

**D is incorrect** because allowing the entire 10.0.0.0/8 private address range would grant access based only on network location and would include a very large number of potentially unrelated or unauthorized workloads. RFC1918 addresses indicate that an address is private, but they do not prove that the source carries an approved application identity. Any compromised or misconfigured VM using an address within the allowed range could potentially reach the protected service. This broad rule would increase the attack surface and would not meet the requirement for identity-based, centrally governed access.

**E is incorrect** because assigning an external IP address exposes the patient-data workload to additional internet-facing risk and does not create a meaningful security control. An IP address cannot be considered secret because it can be discovered through scanning, logs, DNS data, configuration leaks, or other observation. Security through obscurity does not authenticate the calling workload or restrict access to approved application identities. The database should remain protected by explicit Cloud NGFW firewall policy rules that use trusted secure tags rather than by attempting to conceal a publicly reachable address.

**Reference links**

- [docs.cloud.google.com/firewall/docs/tags-firewalls-overview](https://docs.cloud.google.com/firewall/docs/tags-firewalls-overview)
- [docs.cloud.google.com/firewall/docs/use-tags-for-firewalls](https://docs.cloud.google.com/firewall/docs/use-tags-for-firewalls)
- [docs.cloud.google.com/firewall/docs/firewall-policies-rule-details](https://docs.cloud.google.com/firewall/docs/firewall-policies-rule-details)

**Related notes:** [Firewall, Hierarchical Policies, and Secure Tags (Cloud NGFW)](../06-networking/products/firewall-hierarchical-policies-and-secure-tags.md)

</details>

[Back to index](#index)

---

### Q43

> SkyRoute Media stores uploaded video files in a Cloud Storage bucket located in its application project. The bucket uses a customer-managed encryption key from Cloud KMS that is maintained in a separate security project. Although the application service account has permission to create objects in the bucket, uploads fail because access to the encryption key is denied. Which additional identity should receive the required Cloud KMS permissions?  

- **A.** All human users who have access to the application project
- **B.** The Cloud Storage service agent belonging to the project that contains the bucket
- **C.** The allUsers principal with the Cloud KMS Admin role
- **D.** The Compute Engine default service account in the security project with the Owner role

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because permissions granted to human users in the application project do not enable Cloud Storage to perform the cryptographic operation required for customer-managed encryption keys. The application service account or a human requester needs the appropriate Cloud Storage permission, such as storage.objects.create, to upload an object, but Cloud Storage performs the server-side encryption operation through its own Google-managed service agent. Granting every human user access to the Cloud KMS key would not fix the missing permission for that service agent and would violate the principle of least privilege by unnecessarily allowing many identities to access a sensitive encryption resource.

**B is correct** because each project that uses Cloud Storage has a Google-managed Cloud Storage service agent that performs encryption and decryption operations for objects protected by customer-managed encryption keys. The relevant identity is the Cloud Storage service agent associated with the project that owns the bucket, even when the Cloud KMS key is located in a different centralized security project. This service agent commonly has an identity based on the bucket project’s project number, such as service-PROJECT_NUMBER@gs-project-accounts.iam.gserviceaccount.com. The security team should grant this service agent the required cryptographic permissions on the Cloud KMS key, typically through the Cloud KMS CryptoKey Encrypter/Decrypter role, roles/cloudkms.cryptoKeyEncrypterDecrypter, at the key or an appropriate parent resource. The application service account’s permission to create objects controls access to Cloud Storage, while the Cloud Storage service agent’s permission controls whether Cloud Storage can use the key to encrypt the uploaded data. Both permission paths must succeed.

**C is incorrect** because allUsers represents unauthenticated public access. Granting this principal access to a Cloud KMS key would expose the key resource far more broadly than required and would create a serious security risk. In addition, the Cloud KMS Admin role is intended to administer key resources and does not provide the cryptographic encrypt and decrypt operations required to process Cloud Storage objects. The correct approach is to grant a narrowly scoped cryptographic role to the specific Cloud Storage service agent, not to make the key publicly accessible.

**D is incorrect** because the Compute Engine default service account in the security project does not perform Cloud Storage’s server-side CMEK encryption operations for a bucket in another project. The fact that the key is stored in the security project does not make that project’s Compute Engine service account the acting identity. Granting the Owner role would also be excessively broad because it provides extensive project-level permissions unrelated to the required encryption operation. The permission should instead be granted directly to the bucket project’s Cloud Storage service agent, using the least-privileged Cloud KMS role needed to encrypt and decrypt the bucket’s objects.

**Reference links**

- [docs.cloud.google.com/storage/docs/encryption/customer-managed-keys](https://docs.cloud.google.com/storage/docs/encryption/customer-managed-keys)
- [docs.cloud.google.com/storage/docs/encryption/using-customer-managed-keys](https://docs.cloud.google.com/storage/docs/encryption/using-customer-managed-keys)
- [docs.cloud.google.com/kms/docs/reference/permissions-and-roles](https://docs.cloud.google.com/kms/docs/reference/permissions-and-roles)

**Related notes:** [Cloud KMS](../02-identity-security/products/cloud-kms.md)

</details>

[Back to index](#index)

---

### Q44

> BrightCart Commerce runs its application servers on Compute Engine virtual machines in a custom mode VPC network. The virtual machines receive their primary internal IPv4 addresses from a subnet whose primary range is 10.24.0.0/21. The subnet is nearly out of available addresses, and the company needs additional primary internal IPv4 addresses for new virtual machines. What should the company do?  

- **A.** Add 10.40.0.0/21 as a secondary IPv4 range of the existing subnet.
- **B.** Expand the subnet’s primary IPv4 range from 10.24.0.0/21 to 10.24.0.0/19.
- **C.** Change the subnet’s primary IPv4 range from 10.24.0.0/21 to 10.24.0.0/23.
- **D.** Replace the subnet’s primary IPv4 range with an IPv6 range.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because a virtual machine network interface normally receives its primary internal IPv4 address from the subnet’s primary IPv4 range. A secondary IPv4 range does not enlarge the address pool used for these primary VM interface addresses. Secondary ranges are primarily used for alias IP ranges, including addresses assigned to applications, containers, and Google Kubernetes Engine Pods. Adding 10.40.0.0/21 as a secondary range would therefore create another address range in the subnet, but it would not provide additional primary internal IPv4 addresses for the new virtual machines described in the requirement.

**B is correct** because Google Cloud allows the primary IPv4 range of an existing subnet to be expanded to a larger, contiguous CIDR block, provided the expanded range does not overlap another subnet range, a peering-related range, or another relevant network allocation. Changing the prefix from /21 to /19 increases the size of the primary address pool while retaining all existing addresses. A /21 contains 2,048 total IPv4 addresses, whereas a /19 contains 8,192 total IPv4 addresses. The expanded primary range can therefore supply many more primary internal IPv4 addresses to Compute Engine virtual machine interfaces. The expansion cannot later be reversed, so the administrator should first verify that the larger range is available and does not conflict with present or planned connected networks.

**C is incorrect** because changing from /21 to /23 would reduce the size of the subnet range rather than increase it. A /23 contains only 512 total IPv4 addresses, compared with 2,048 total addresses in a /21. In addition, Google Cloud does not allow an existing subnet’s primary IPv4 range to be shrunk. The primary range can be expanded, but it cannot be replaced with a smaller CIDR block. This option would therefore both fail to provide more addresses and represent an unsupported subnet modification.

**D is incorrect** because IPv6 does not expand the subnet’s pool of primary internal IPv4 addresses. Configuring an IPv6 or dual-stack subnet can provide IPv6 connectivity to compatible workloads, but it does not make more IPv4 addresses available to virtual machines that require primary internal IPv4 addresses. An existing IPv4 primary range also cannot simply be replaced with an IPv6 range as a method of resolving IPv4 exhaustion. Applications, operating systems, clients, and dependent services might still require IPv4 connectivity, so the appropriate solution is to expand the existing primary IPv4 range.

**Reference links**

- [docs.cloud.google.com/vpc/docs/subnets](https://docs.cloud.google.com/vpc/docs/subnets)
- [docs.cloud.google.com/vpc/docs/create-modify-vpc-networks](https://docs.cloud.google.com/vpc/docs/create-modify-vpc-networks)
- [docs.cloud.google.com/vpc/docs/alias-ip](https://docs.cloud.google.com/vpc/docs/alias-ip)

**Related notes:** [VPC, Subnets, and IPs](../06-networking/products/vpc-subnets-and-ips.md)

</details>

[Back to index](#index)

---

### Q45

> MercuryMart operates a retail analytics platform and needs to install a third-party application on one Compute Engine VM. The application stores transactional data in an internal database on an attached data disk and requires the highest possible read and write performance. If the VM becomes unhealthy, it must be recreated automatically without losing the database disk. What should MercuryMart do?  

- **A.** Create an instance template with an SSD Persistent Disk and use it to create a stateful managed instance group with a target size of one VM.
- **B.** Create an instance template with an SSD Persistent Disk and use it to create a stateless managed instance group with a target size of one VM.
- **C.** Create an instance template with a Hyperdisk Extreme data disk and use it to create a stateful managed instance group with a target size of one VM.
- **D.** Create an instance template with a Hyperdisk Extreme data disk and use it to create a stateless managed instance group with a target size of one VM.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a stateful managed instance group is appropriate for preserving the application’s unique database disk when the VM is restarted, recreated, updated, or autohealed. However, SSD Persistent Disk does not provide the highest available disk performance for an IOPS-intensive database. Hyperdisk Extreme is designed for demanding workloads that require substantially higher provisioned IOPS and throughput. Therefore, this option satisfies the recovery and state-preservation requirement but not the requirement for the highest-speed disk access.

**B is incorrect** because SSD Persistent Disk does not offer the maximum disk performance available for this database workload, and a stateless managed instance group is intended for instances that can be recreated from a common template without preserving unique instance data. When a stateless instance is replaced, the group normally creates the replacement from the instance template rather than preserving and reattaching the failed instance’s unique database disk. This approach is suitable for interchangeable application servers whose persistent data is stored in an external service, but it is unsuitable for a database stored locally on the VM.

**C is correct** because Hyperdisk Extreme is Google Cloud’s highest-performance durable block storage option for workloads requiring very high IOPS and low-latency disk access. It should be configured as an attached data disk because Hyperdisk Extreme cannot be used as a boot disk. A stateful managed instance group can preserve the attached database disk and reattach it when the VM is automatically recreated. The group can have a target size of one, and an application-based health check with an autohealing policy can detect an unhealthy VM and trigger its replacement. The selected machine series and VM configuration must support Hyperdisk Extreme and meet its applicable vCPU and attachment requirements. This design protects against VM failure while preserving the database state. Because Hyperdisk Extreme is zonal, additional replication or another high-availability architecture would be required if recovery from an entire zone failure were also required.

**D is incorrect** because Hyperdisk Extreme meets the high-performance storage requirement, but a stateless managed instance group does not preserve the unique state of an individual VM. If the database disk is treated as stateless, recreating the instance can create or attach storage based on the template rather than reliably retaining the failed VM’s existing database disk. Stateless managed instance groups are appropriate when instances are interchangeable and application data is stored outside the instances. The locally stored database makes a stateful managed instance group necessary.

**Reference links**

- [docs.cloud.google.com/compute/docs/disks/hd-types/hyperdisk-extreme](https://docs.cloud.google.com/compute/docs/disks/hd-types/hyperdisk-extreme)
- [docs.cloud.google.com/compute/docs/instance-groups/stateful-migs](https://docs.cloud.google.com/compute/docs/instance-groups/stateful-migs)
- [docs.cloud.google.com/compute/docs/instance-groups/autohealing-instances-in-migs](https://docs.cloud.google.com/compute/docs/instance-groups/autohealing-instances-in-migs)

**Related notes:** [Managed Instance Group (MIG)](../03-compute-containers/products/managed-instance-group.md) · [Hyperdisk](../03-compute-containers/products/hyperdisk.md)

</details>

[Back to index](#index)

---

### Q46

> TransitPulse, a city transport tracking company, has built a stateless application that depends on an operating-system package and must run directly on virtual machines. User traffic varies significantly throughout the day, so the number of virtual machines must increase and decrease automatically. How should the company deploy the application?  

- **A.** Deploy the application to a managed instance group and configure an autoscaling policy.
- **B.** Deploy the application to a Google Kubernetes Engine cluster and enable node pool autoscaling.
- **C.** Deploy the application as a Cloud Run function and configure the maximum number of function instances.
- **D.** Deploy the application to Cloud Run and configure instance autoscaling.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A

**Explanation**

**A is correct** because a Compute Engine managed instance group is designed to operate a collection of identical virtual machine instances created from an instance template. It is the most appropriate solution when an application must run directly on virtual machines while remaining stateless and horizontally scalable. An autoscaling policy can automatically add or remove VM instances according to signals such as average CPU utilization, load-balancing serving capacity, Cloud Monitoring metrics, schedules, or queue-based workload. Because every instance is created from the same instance template, the application can be installed and configured consistently across all VMs. The stateless design also allows incoming requests to be distributed across interchangeable instances without requiring session data to remain on a particular VM. A regional managed instance group can additionally distribute instances across multiple zones for improved availability.

**B is incorrect** because Google Kubernetes Engine is intended for deploying and orchestrating containerized applications as Kubernetes Pods rather than running an application directly on independently managed virtual machines. Node pool autoscaling changes the number of Compute Engine nodes available to a GKE cluster when Pods cannot be scheduled or when nodes are underutilized. It does not directly scale the application itself; application-level scaling would normally require Kubernetes mechanisms such as the Horizontal Pod Autoscaler. Although GKE nodes are virtual machines underneath, the application runs inside containers managed by Kubernetes. This introduces unnecessary containerization and cluster-management complexity and does not satisfy the stated requirement to run the application directly on virtual machines.

**C is incorrect** because Cloud Run functions is a serverless, event-driven compute service intended for deploying functions in response to HTTP requests or events. The platform manages the underlying infrastructure, and users do not deploy or administer the virtual machines on which function instances execute. Configuring the maximum number of instances only places an upper limit on function scaling; it does not provide direct access to VM configuration or allow the application to run as a traditional VM-based workload. This option is therefore incompatible with the requirement that the application run directly on virtual machines.

**D is incorrect** because Cloud Run is a fully managed serverless platform that runs containerized workloads on infrastructure managed by Google. Cloud Run automatically scales container instances according to incoming requests, resource utilization, and configured scaling limits, making it suitable for many stateless applications. However, users do not provision or manage the underlying virtual machines, and the workload must be packaged as a supported container image. Since the application specifically requires direct execution on virtual machines, Cloud Run does not meet the deployment requirement even though it provides automatic scaling.

**Reference links**

- [docs.cloud.google.com/compute/docs/autoscaler](https://docs.cloud.google.com/compute/docs/autoscaler)
- [docs.cloud.google.com/compute/docs/instance-groups](https://docs.cloud.google.com/compute/docs/instance-groups)
- [docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/cluster-autoscaler)

**Related notes:** [Managed Instance Group (MIG)](../03-compute-containers/products/managed-instance-group.md)

</details>

[Back to index](#index)

---

### Q47

> LedgerNest stores monthly compliance reports in Cloud Storage. Each report is uploaded once and accessed frequently during its first 45 days. After that period, reports are retrieved only in exceptional circumstances. The company must retain every report for four years while minimizing storage and access costs. Which lifecycle policy should LedgerNest configure?  

- **A.** Store the reports in Nearline storage for the first 45 days, and then move them to Archive storage for the remaining retention period.
- **B.** Store the reports in Standard storage for the first 45 days, and then move them to Archive storage for the remaining retention period.
- **C.** Store the reports in Nearline storage for the first 45 days, move them to Coldline storage for one year, and then move them to Archive storage.
- **D.** Store the reports in Standard storage for the first 45 days, move them to Coldline storage for one year, and then move them to Archive storage.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because Nearline storage is intended for data that is accessed approximately once per month or less frequently. Although its at-rest storage price is lower than Standard storage, Nearline storage has data-retrieval charges, operation charges, and a 30-day minimum storage duration. The reports are accessed frequently during their first 45 days, so the repeated retrieval charges can outweigh the savings from Nearline’s lower storage price. Moving the reports directly to Archive storage after they become inactive is appropriate, but using Nearline during the initial high-access period is not the most cost-effective choice.

**B is correct** because Standard storage is designed for frequently accessed data and has no minimum storage duration or data-retrieval fee. It is therefore the appropriate class for the reports during their first 45 days. After 45 days, the reports are expected to remain unread except in special circumstances, making Archive storage the most economical class for the rest of the four-year retention period. Archive storage has the lowest at-rest storage cost and is intended for data accessed less than once per year. Because the reports will remain in Archive storage for much longer than its 365-day minimum storage duration, the company avoids early-deletion charges under the expected lifecycle. Object Lifecycle Management can use a SetStorageClass action with an age condition of 45 days to move objects to Archive storage. A separate Delete action can remove them when their age reaches the required four-year retention threshold, subject to any retention policy or compliance requirements.

**C is incorrect** because Nearline storage is unsuitable for the initial period in which the reports are frequently accessed. Retrieval and operation charges would apply during that high-access period. The additional transition through Coldline storage is also unnecessary because the reports are expected to become almost completely inactive after 45 days. Coldline storage is intended for data accessed at most once per quarter and has a higher at-rest storage cost than Archive storage. Since the reports will be retained for several years and accessed only in exceptional cases, moving them directly to Archive storage after the active period provides lower storage costs and a simpler lifecycle configuration.

**D is incorrect** because Standard storage is the correct choice for the first 45 days, but retaining the reports in Coldline storage for an additional year is unnecessary. Once the reports are no longer regularly accessed, Archive storage is already the best match for their access pattern and long retention period. Coldline storage has a 90-day minimum storage duration and lower retrieval charges than Archive storage, but its at-rest storage cost is higher. The possibility of a rare retrieval does not justify paying Coldline storage rates for an entire year. Moving directly from Standard storage to Archive storage after 45 days minimizes ongoing storage costs and eliminates an unnecessary lifecycle transition.

**Reference links**

- [docs.cloud.google.com/storage/docs/storage-classes](https://docs.cloud.google.com/storage/docs/storage-classes)
- [docs.cloud.google.com/storage/docs/lifecycle](https://docs.cloud.google.com/storage/docs/lifecycle)
- [docs.cloud.google.com/storage/docs/lifecycle-configurations](https://docs.cloud.google.com/storage/docs/lifecycle-configurations)

**Related notes:** [Cloud Storage](../05-storage-databases-data/products/cloud-storage.md)

</details>

[Back to index](#index)

---

### Q48

> BrightForge Labs gives each of its 12 application developers a separate Google Cloud project for testing services and building prototypes. All sandbox projects are used independently. You need to receive an alert whenever any individual project’s monthly spending reaches $650. What should you do?  

- **A.** Create one $650 budget that includes all sandbox projects and configure budget alert thresholds for that budget.
- **B.** Create a separate Cloud Billing account for each sandbox project, enable Cloud Billing export to BigQuery, and use Looker Studio to display spending by billing account.
- **C.** Create a $650 budget for each sandbox project and configure budget alert thresholds for every budget.
- **D.** Link all sandbox projects to one Cloud Billing account, enable Cloud Billing export to BigQuery, and use Looker Studio to display spending by project.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** C

**Explanation**

**A is incorrect** because a budget that includes all sandbox projects monitors their combined costs. The alert would be triggered when the total spending across the included projects reaches the configured threshold, rather than when one particular project reaches $650. For example, several projects could each spend less than $650 but collectively exceed the budget, causing an alert that does not identify an individual developer as exceeding the limit. Conversely, an individual project’s spending would not be evaluated against a separate $650 threshold. A distinct project-filtered budget is required for each independently monitored sandbox.

**B is incorrect** because creating a separate Cloud Billing account for every sandbox project introduces unnecessary administrative complexity. Cloud Billing accounts are normally used to manage billing relationships and payment arrangements and are not required merely to monitor projects separately. Cloud Billing export to BigQuery provides detailed cost data, and Looker Studio can visualize that data, but a dashboard does not by itself satisfy the requirement for an automatic threshold alert. Additional queries, scheduling, and notification automation would have to be developed and maintained. Native Cloud Billing budgets provide a simpler solution.

**C is correct** because each Cloud Billing budget can be scoped to a specific Google Cloud project. Creating a $650 monthly budget for each sandbox project allows every developer’s spending to be evaluated independently. A 100-percent actual-cost threshold can notify the appropriate recipients when that project reaches the monthly budget amount, and lower thresholds such as 50 percent or 90 percent can provide earlier warnings. The team lead can configure the supported email recipients or notification channels for the budgets. Budgets monitor spending and generate alerts; they do not automatically cap usage or prevent additional charges after the threshold is reached.

**D is incorrect** because using a single Cloud Billing account for all projects is a reasonable billing-account design, and exported billing data can be grouped by project in BigQuery and displayed in Looker Studio. However, this option only describes reporting and visualization. It does not configure automatic alerts when an individual project exceeds $650. Implementing threshold notifications from exported data would require additional scheduled queries or custom automation. Project-specific Cloud Billing budgets provide the required notifications directly and with less operational effort.

**Reference links**

- [docs.cloud.google.com/billing/docs/how-to/budgets](https://docs.cloud.google.com/billing/docs/how-to/budgets)
- [docs.cloud.google.com/billing/docs/how-to/budgets-notification-recipients](https://docs.cloud.google.com/billing/docs/how-to/budgets-notification-recipients)
- [docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-setup](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery-setup)

**Related notes:** [Cloud Billing](../07-operations-cost/products/cloud-billing.md)

</details>

[Back to index](#index)

---

### Q49

> Meridian BioLabs operates several Google Cloud projects that store regulated research data in CMEK-supported services. Compliance requirements state that all newly created supported resources must use customer-managed encryption keys and that the keys must come only from the dedicated project secure-key-hub-72. Development teams continuously provision resources through the Google Cloud console and automated pipelines, so voluntary guidance cannot reliably enforce the requirement. What should the organization implement?  

- **A.** Ask developers to manually choose an approved Cloud KMS key whenever they create a resource.
- **B.** Enforce Organization Policy constraints that require CMEK for the applicable supported services and restrict permitted Cloud KMS keys to the central security project.
- **C.** Grant the security team the Project Owner role in every workload project and perform a compliance assessment once per year.
- **D.** Encrypt exported Cloud Billing reports with a central key and treat all resources in the associated projects as CMEK-protected.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** B

**Explanation**

**A is incorrect** because instructions and documentation provide guidance but do not technically prevent developers, service accounts, deployment pipelines, or infrastructure automation from creating resources without CMEK. A user could overlook the encryption setting, choose Google-managed encryption, or select a Cloud KMS key from an unapproved project. This approach becomes especially unreliable when teams create resources frequently and through several provisioning methods. Google Cloud IAM can control who creates resources, but ordinary resource-creation permissions do not by themselves enforce the selection of CMEK or the location of the selected key. A regulated organization needs a preventive control that evaluates each applicable resource-creation request rather than depending on user memory.

**B is correct** because Organization Policy provides centrally managed, inheritable guardrails that can prevent noncompliant resources from being created. To require CMEK for applicable services, the organization should configure the constraints/gcp.restrictNonCmekServices list constraint. The organization places the relevant supported service names, such as storage.googleapis.com, compute.googleapis.com, or bigquery.googleapis.com, in the denied list. For those supported services, creation requests that do not specify a customer-managed encryption key are rejected. The constraint also prevents CMEK protection from being removed from covered resources where that operation is supported. To satisfy the separate requirement that approved keys reside in the central security project, the organization should also configure constraints/gcp.restrictCmekCryptoKeyProjects and allow only the dedicated key project, such as projects/secure-key-hub-72. This prevents teams from satisfying the CMEK requirement with keys from unauthorized workload projects. Both constraints are needed for complete enforcement: restrictNonCmekServices requires CMEK, while restrictCmekCryptoKeyProjects controls which projects may supply the Cloud KMS keys. These policies can be applied at the organization, folder, or project level and inherited through the resource hierarchy. They primarily govern newly created resources in supported services, so the company should separately assess and remediate existing resources that were created before enforcement. A centralized key project also supports separation of duties because the security team can administer keys without receiving broad access to the application resources protected by those keys.

**C is incorrect** because the Project Owner role is excessively privileged and does not create an automatic CMEK enforcement mechanism. Project Owner grants broad authority over project resources and IAM configuration, far beyond what the security team needs to manage encryption governance. Assigning this role in every workload project weakens separation of duties and increases the potential impact of credential compromise or administrator error. An annual review is also a detective control: it identifies violations only after resources have already been created and possibly used to store regulated data. The requirement calls for continuous preventive enforcement because project teams create resources frequently. Organization Policy can reject a noncompliant creation request immediately, whereas an annual audit could leave a resource using an unapproved encryption configuration for many months.

**D is incorrect** because encryption settings do not propagate from Cloud Billing exports to unrelated Google Cloud resources. A billing export stored in BigQuery or Cloud Storage can have its own encryption configuration, but that configuration protects only the applicable billing data resource. It does not cause Compute Engine disks, Cloud Storage buckets, BigQuery datasets, Cloud SQL instances, Pub/Sub topics, or other resources in the project to inherit the same Cloud KMS key. CMEK integration and configuration are resource-specific or service-specific. Encrypting billing reports may be useful for protecting billing information, but it does not enforce CMEK for newly provisioned application resources and does not restrict teams to keys from the central security project.

**Reference links**

- [docs.cloud.google.com/kms/docs/cmek-org-policy](https://docs.cloud.google.com/kms/docs/cmek-org-policy)
- [docs.cloud.google.com/kms/docs/separation-of-duties](https://docs.cloud.google.com/kms/docs/separation-of-duties)
- [docs.cloud.google.com/organization-policy/reference/org-policy-constraints](https://docs.cloud.google.com/organization-policy/reference/org-policy-constraints)

**Related notes:** [Cloud KMS](../02-identity-security/products/cloud-kms.md)

</details>

[Back to index](#index)

---

### Q50

Choose 2.

> ParcelPilot, a package-delivery platform, runs its production workloads across several Google Cloud services. Its site reliability engineering team needs a single console view for open Cloud Monitoring incidents, Google Cloud service disruptions, resource performance and health metrics, and other issues affecting its applications. The team must also receive automatic notifications whenever a new Google Cloud service-health event is relevant to the production project. Which two actions should the team take? (Choose two.)  

- **A.** Use Cloud Hub’s Health &amp; troubleshooting page to review centralized application and resource health information.
- **B.** Create a Personalized Service Health alerting policy and associate it with a Cloud Monitoring notification channel in the production project.
- **C.** Configure only Cloud Billing budgets because every Google Cloud service disruption produces a detectable billing increase.
- **D.** Enable Object Versioning for every Cloud Storage bucket used by the production applications.
- **E.** Publish a dashboard containing operational logs and grant the allUsers principal permission to view it.

<details>
<summary><strong>Show answer</strong></summary>

**Correct answer:** A, B

**Explanation**

**A is correct** because Cloud Hub provides centralized data and insights about Google Cloud applications and resources. Its Health &amp; troubleshooting page brings together open alerts generated by Cloud Monitoring alerting policies, active Google Cloud incidents involving service outages or degradations, and health and performance metrics such as utilization, latency, and errors. The team can examine this information at the project level or, when using App Hub applications, in the context of a particular application and its associated services and workloads. This makes Cloud Hub suitable for obtaining the consolidated operational context described in the requirement. It reduces the need to navigate independently through multiple service-specific dashboards while investigating whether an issue originates in the application, its resources, or an underlying Google Cloud service.

**B is correct** because Personalized Service Health identifies Google Cloud service-health events that are relevant to a specific project or organization. The team can create an alerting policy for conditions such as the publication of a new incident, an update to an existing incident, or an incident affecting selected Google Cloud products or locations. The alerting policy can send notifications through a configured Cloud Monitoring notification channel, including email, SMS, Slack, PagerDuty, Pub/Sub, webhooks, or the Google Cloud mobile application. Creating the policy in the production project ensures that notifications are based on disruptive events relevant to that project instead of relying solely on the general public service-health dashboard. The Service Health API must be enabled, appropriate IAM permissions must be available, and a notification channel must be configured for the alerts to reach the operations team.

**C is incorrect** because Cloud Billing budgets monitor spending and forecasted costs rather than the operational health of Google Cloud services. A service disruption does not necessarily create a cost increase, and a budget alert cannot reliably identify incidents, degraded services, affected products, impacted locations, or incident updates. Billing budgets are useful for financial governance, but they do not replace Cloud Hub, Cloud Monitoring, or Personalized Service Health for operational incident detection and notification.

**D is incorrect** because Cloud Storage Object Versioning preserves older versions of objects when objects are replaced or deleted. It can support recovery from accidental modification or deletion of application data stored in Cloud Storage, but it does not provide centralized visibility into Monitoring incidents, Google Cloud service disruptions, resource health metrics, or application-wide operational problems. It also cannot notify the team that a Google Cloud service-health event is affecting the production project.

**E is incorrect** because granting the allUsers principal access would make the dashboard or its underlying information publicly accessible to unauthenticated users. Operational logs can contain sensitive details such as resource names, internal architecture information, error messages, request metadata, and application activity. Public access is unnecessary for centralized troubleshooting and violates least-privilege security practices. Authorized operations personnel should receive appropriate IAM roles, while Cloud Hub and Personalized Service Health should provide the required visibility and notifications without exposing logs publicly.

**Reference links**

- [docs.cloud.google.com/hub/docs/health](https://docs.cloud.google.com/hub/docs/health)
- [docs.cloud.google.com/service-health/docs/overview](https://docs.cloud.google.com/service-health/docs/overview)
- [docs.cloud.google.com/service-health/docs/configure-alerts-dashboard](https://docs.cloud.google.com/service-health/docs/configure-alerts-dashboard)

**Related notes:** [Cloud Hub](../07-operations-cost/products/cloud-hub.md) · [Personalized Service Health](../07-operations-cost/products/personalized-service-health.md)

</details>

[Back to index](#index)

---
