# Storage, databases and data: concepts from basic to advanced

> Official exam guide sections covered: 2.2, 3.4, 4.4 (see the [exam guide map](../00-start-here/exam-guide-map.md)).

## Basic

Google Cloud splits data services into three groups. Pick the group first, then the product.

- **Object storage:** Cloud Storage. Unstructured objects (files, images, backups, logs) in buckets.
- **Block and file storage:** Persistent Disk and Hyperdisk (block, attached to VMs), Filestore (managed NFS file shares).
- **Databases and analytics:** Cloud SQL, AlloyDB, Spanner, Bigtable, Firestore, Memorystore, BigQuery.

### Cloud Storage buckets

A bucket is a container for objects. Bucket names are globally unique. The **location is chosen at creation and cannot be changed**.

| Location type | What it means | Typical use |
|---|---|---|
| Region | One region | Lowest cost and latency next to compute |
| Dual-region | Two specific regions | Higher availability, you choose the pair |
| Multi-region | A large geography (for example US or EU) | Broad geo-redundancy, content serving |

### Storage classes and minimum durations

All classes have the same durability and millisecond access. They differ in at-rest price, retrieval fees and a **minimum storage duration**. Deleting or rewriting earlier still bills the remaining days.

| Class | Minimum duration | Use for |
|---|---|---|
| Standard | None | Hot data, frequently accessed |
| Nearline | 30 days | Read about once a month |
| Coldline | 90 days | Read about once a quarter |
| Archive | 365 days | Long-term archive, compliance |

Autoclass can move objects between classes automatically based on access.

### Disks and file shares

- **Persistent Disk:** network block storage. Zonal by default. **Regional Persistent Disk** replicates synchronously between two zones of a region, so a VM can be restarted in the other zone after a zone failure.
- **Hyperdisk:** newer block storage where you provision IOPS and throughput separately from size. Hyperdisk Extreme targets the highest IOPS (for example SAP HANA).
- **Local SSD:** very fast but ephemeral; data does not survive VM deletion.
- **Filestore:** managed NFS for legacy apps that need a POSIX file share. SMB workloads point to NetApp Volumes. Massive parallel HPC/AI throughput points to Managed Lustre.

## Intermediate

### Cloud Storage management

- **Lifecycle rules:** conditions (`age`, `createdBefore`, `numNewerVersions`, `isLive`, `matchesStorageClass`) plus an action (`SetStorageClass` or `Delete`). Rules are evaluated by Google asynchronously, not instantly.
- **Object Versioning:** keeps noncurrent versions when an object is overwritten or deleted. Combine it with a lifecycle rule to expire old versions, or storage grows without limit.
- **Retention policy and bucket lock:** objects cannot be deleted or replaced until they reach the retention age. Locking the policy is permanent. Object holds are a per-object alternative.
- **Soft delete:** keeps deleted objects for a configurable period (7 days by default).
- **Uniform bucket-level access:** turns off ACLs so only IAM controls access. This is required to use IAM Conditions (for example restrict by object name prefix).
- **Signed URLs:** time-limited access to one object for someone without a Google identity. The signer must itself have access. V4 signed URLs last at most 7 days.
- **Access roles:** use `Storage Object Viewer` or `Storage Object Creator` on the bucket for least privilege.

```bash
gcloud storage buckets create gs://my-bucket --location=us-central1 \
    --default-storage-class=STANDARD --uniform-bucket-level-access
gcloud storage buckets update gs://my-bucket --versioning
gcloud storage buckets update gs://my-bucket --lifecycle-file=lifecycle.json
gcloud storage cp ./data/* gs://my-bucket/data/ --recursive
gcloud storage rsync ./local-dir gs://my-bucket/dir --recursive
gcloud storage sign-url gs://my-bucket/report.pdf --duration=2h \
    --impersonate-service-account=signer@PROJECT.iam.gserviceaccount.com
```

```json
{"rule": [
  {"action": {"type": "SetStorageClass", "storageClass": "NEARLINE"},
   "condition": {"age": 30}},
  {"action": {"type": "Delete"}, "condition": {"age": 365}}
]}
```

`gcloud storage` replaces the older `gsutil` for new work.

### Choosing a database

| Need | Product |
|---|---|
| Regional relational (MySQL, PostgreSQL, SQL Server), lift and shift, no app rewrite | Cloud SQL |
| PostgreSQL-compatible, higher transactional performance and fast analytics on live data | AlloyDB |
| Global relational, strong consistency, horizontal scale | Spanner |
| Huge-scale low-latency wide-column NoSQL: time series, telemetry, IoT | Bigtable |
| Serverless document database with mobile/web sync | Firestore |
| In-memory cache, sessions (Redis, Valkey, Memcached) | Memorystore |
| Serverless analytics data warehouse queried with SQL | BigQuery |

Bigtable row keys matter: lead with a high-cardinality id (for example `deviceId#timestamp`), not a bare timestamp, to avoid hotspots. Database Center gives one view of health and recommendations across the database fleet.

### Cloud SQL operations

- **High availability:** a regional instance has a primary and a standby in two zones of one region, with synchronous replication and automatic failover. HA protects against zone failure.
- **Read replicas:** asynchronous copies that scale reads. They can be cross-region. They are **not** a backup and not the HA mechanism.
- **Backups vs export:** automated and on-demand backups live with the instance and support point-in-time recovery (needs binary logging or WAL). An **export** (SQL dump or CSV to Cloud Storage) is a portable, independent copy, for example scheduled into an Archive bucket for multi-year retention.
- **Connecting:** the **Cloud SQL Auth Proxy** gives encrypted, IAM-authorized connections without managing certificates or allowlisting IPs. IAM database authentication can replace passwords.

```bash
gcloud sql instances create prod-db --database-version=POSTGRES_16 \
    --region=us-central1 --tier=db-custom-2-8192 --availability-type=REGIONAL
gcloud sql instances create prod-db-replica --master-instance-name=prod-db
gcloud sql backups create --instance=prod-db
gcloud sql export sql prod-db gs://my-bucket/dump.sql --database=app
cloud-sql-proxy PROJECT:us-central1:prod-db --port=5432
```

### BigQuery basics

- **Hierarchy:** project, dataset (has a fixed location), table or view. Tables can be partitioned and clustered to reduce scanned bytes.
- **Jobs:** load, query, copy and extract run as jobs. Check them with `bq ls -j` and `bq show -j JOB_ID`, or in BigQuery Studio job history.
- **Roles:** `BigQuery Data Viewer` (read table data), `Data Editor`, `Data Owner`, `Job User` (run jobs in a project), `User`, `Admin`. Running a query needs a job role in the billing project plus data access on the dataset.
- **External tables:** query files in Cloud Storage in place, with no copy.
- **INFORMATION_SCHEMA:** metadata views, region-qualified, for example `` `region-us`.INFORMATION_SCHEMA.JOBS ``. Use it with Cloud Audit Logs to troubleshoot `quotaExceeded` errors.
- **Cost control:** on-demand queries bill by bytes processed. `--dry_run` shows the estimate. Tables or partitions untouched for 90 days move to cheaper long-term storage automatically.

```bash
bq mk --dataset --location=US my_dataset
bq load --source_format=CSV --autodetect my_dataset.sales gs://my-bucket/sales.csv
bq query --use_legacy_sql=false --dry_run 'SELECT COUNT(*) FROM my_dataset.sales'
bq query --use_legacy_sql=false \
  'SELECT job_id, state FROM `region-us`.INFORMATION_SCHEMA.JOBS ORDER BY creation_time DESC LIMIT 10'
```

## Advanced

### Dataflow

Dataflow is the managed Apache Beam runner for batch and streaming pipelines, for example Pub/Sub to Dataflow to BigQuery or Cloud Storage. Google provides ready-made templates. Review jobs with `gcloud dataflow jobs list` or the console. For streaming jobs, **drain** finishes in-flight data before stopping; **cancel** stops immediately and may lose it. A data freshness alert detects a stuck pipeline.

### Loading and transferring data

| Scenario | Tool |
|---|---|
| Small or ad hoc upload, scripted sync | `gcloud storage cp` / `rsync` (add cron for recurring) |
| Amazon S3, Azure Blob, HTTP lists, or on-premises file systems (with agents), scheduled, low impact on the network | Storage Transfer Service |
| Tens of terabytes to petabytes, slow or no network, offline | Transfer Appliance |
| Scheduled loads into BigQuery from SaaS apps, Cloud Storage, S3, Redshift | BigQuery Data Transfer Service |
| Move a MySQL, PostgreSQL or SQL Server database to Cloud SQL or AlloyDB with minimal downtime | Database Migration Service |

`bq load` appends unless you pass `--replace`. Cloud SQL imports need the instance's service account to read the bucket.

### Estimating storage costs

- Cloud Storage cost is the sum of data at rest (per GB-month by class and location), operations, retrieval fees for colder classes, early-deletion charges and network egress.
- BigQuery cost is storage (active vs long-term) plus query processing.
- Use the Pricing Calculator for plans. Use billing export to BigQuery for what you actually spend.

## Exam tips

- Cold data with fixed ages: **lifecycle rule** (`age` + `SetStorageClass`/`Delete`). Old versions: versioning plus lifecycle.
- Temporary access for a partner with no identity: **signed URL**. Read-only on one bucket: `Storage Object Viewer` on that bucket.
- Global strong-consistency SQL: **Spanner**. Telemetry and time series: **Bigtable**. Regional relational with no rewrite: **Cloud SQL**. Bigger PostgreSQL performance: **AlloyDB**.
- Survive a zone failure on a disk: **regional Persistent Disk**. Survive a zone failure on Cloud SQL: **HA**. Read scaling: **read replica**.
- Independent copy kept for years: **scheduled export** to Archive, not automated backups.
- Encrypted, IAM-based Cloud SQL connection: **Auth Proxy** plus IAM database authentication.
- Data already in Cloud Storage and queried by SQL without copying: **BigQuery external table**.
- Cloud Storage object read auditing needs **Data Access audit logs**, which are off by default.
- Prefer the most managed option: Storage Transfer Service over hand-written scripts, Redshift via BigQuery Data Transfer Service, huge offline volume via Transfer Appliance.
- Enable the service API (for example Spanner) before creating the first resource.

## What appeared on the practice exams

Condensed from the 300 practice questions. Question IDs link to the full question and explanation.

### Storage

- **Classes:** Standard > Nearline (30 days) > Coldline (90) > Archive (365).
- **Lifecycle** (age + SetStorageClass/Delete) automates class changes and retention.
- **Object Versioning** keeps old versions.
- **Signed URLs** give temporary access to those without an identity.
- **Uniform bucket-level access** + IAM conditions to filter by object prefix.
- **Transfer:**
  - Transfer Appliance for very large volumes, offline.
  - Storage Transfer Service (S3, on-premises with agents).
  - BigQuery Data Transfer Service (Redshift).
  - For simple continuous synchronization: `gcloud storage rsync` + cron.

## Official documentation
- [Cloud Storage classes](https://cloud.google.com/storage/docs/storage-classes)
- [Cloud Storage locations](https://cloud.google.com/storage/docs/locations)
- [Object lifecycle management](https://docs.cloud.google.com/storage/docs/lifecycle)
- [Object Versioning](https://docs.cloud.google.com/storage/docs/object-versioning)
- [Signed URLs](https://docs.cloud.google.com/storage/docs/access-control/signed-urls)
- [Choose a Google Cloud database](https://docs.cloud.google.com/docs/databases)
- [Cloud SQL high availability](https://docs.cloud.google.com/sql/docs/postgres/high-availability)
- [Cloud SQL Auth Proxy](https://docs.cloud.google.com/sql/docs/postgres/sql-proxy)
- [BigQuery introduction](https://docs.cloud.google.com/bigquery/docs/introduction)
- [Storage Transfer Service overview](https://docs.cloud.google.com/storage-transfer/docs/overview)

[Back to topic](README.md)
