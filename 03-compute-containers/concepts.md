# Compute and containers: concepts from basic to advanced

> Official exam guide sections covered: 2.1, 3.1, 3.2, 3.3, 4.1, 4.2, 4.3 (see the [exam guide map](../00-start-here/exam-guide-map.md)).

## Basic

### Choosing a compute service

Pick by how much you want to manage and what the workload looks like.

| Service | You provide | Best for |
|---|---|---|
| Compute Engine | VMs (OS and up) | Lift-and-shift, custom OS, licensed software, GPUs, full control |
| GKE | Containers, Kubernetes manifests | Many microservices, portability, Kubernetes ecosystem |
| Cloud Run (service) | A container image | Stateless HTTP containers, scale to zero |
| Cloud Run (job) | A container image | Batch tasks that run to completion |
| Cloud Run functions | Source code | Small single-purpose, event-driven handlers |
| App Engine | Source code (standard) or container (flexible) | Web apps in the PaaS model, services and versions |

Rule of thumb: the most managed option that fits is usually the right exam answer. A ready Docker image with no cluster needs points to Cloud Run. Small code reacting to a bucket upload points to a Cloud Run function. A nightly containerized batch points to a Cloud Run job plus Cloud Scheduler.

Note: Cloud Functions is now **Cloud Run functions**.

### Compute Engine essentials

- **Machine families**: general-purpose (E2, N2, N4, ...), compute-optimized (C2, ...), memory-optimized (M-series, for example M1 for very large memory), accelerator-optimized (GPU instances), and storage-optimized.
- **Custom machine types** let you pick vCPU and memory when predefined shapes do not match (available on several general-purpose families, not all).
- **Spot VMs** give a large discount but can be stopped by Google at any time. Use them for fault-tolerant, checkpointed batch work. They are wrong for a long job that cannot be interrupted.
- GPUs: NVIDIA GPUs for CUDA code. Check zone support and GPU quota before building templates. VMs with GPUs cannot live-migrate.

```bash
gcloud compute instances create web-1 --zone=us-central1-a \
  --machine-type=e2-medium --image-family=debian-12 --image-project=debian-cloud
gcloud compute instances create batch-1 --zone=us-central1-a \
  --custom-vm-type=n2 --custom-cpu=6 --custom-memory=24GB \
  --provisioning-model=SPOT --instance-termination-action=STOP
```

## Intermediate

### Disks, snapshots, and images

- **Persistent Disk** (standard, balanced, SSD) and **Hyperdisk** (provisioned IOPS and throughput; Extreme for the highest IOPS) are network disks. **Local SSD** is fast but lost with the VM.
- A **regional** persistent disk replicates synchronously across two zones, which protects against a zone failure.
- **Snapshots** are incremental backups of a disk. Automate with a **snapshot schedule** that has a retention period.
- **Images** are boot templates created from a disk, snapshot, or another image. An **image family** points to the newest non-deprecated image. Sharing an image across projects needs `roles/compute.imageUser`.

```bash
gcloud compute resource-policies create snapshot-schedule daily-14d \
  --region=us-central1 --max-retention-days=14 --daily-schedule --start-time=02:00
gcloud compute disks add-resource-policies data-disk \
  --resource-policies=daily-14d --zone=us-central1-a
gcloud compute images create web-v1 --source-disk=web-1 --source-disk-zone=us-central1-a
gcloud compute snapshots list --filter="creationTimestamp<'2025-01-01'"
```

### Instance templates and managed instance groups (MIGs)

- An **instance template** is an immutable definition of a VM (machine type, image, disks, network, service account, metadata). To change anything, create a new template.
- A **MIG** creates identical VMs from a template. It can be **zonal** or **regional** (spread across zones in a region).
- **Autoscaling** adds or removes VMs based on CPU utilization, load balancer capacity, Cloud Monitoring metrics, or a schedule.
- **Autohealing** recreates VMs that fail an application **health check**; set an initial delay so slow-booting VMs are not killed.
- Updates use a **rolling update** to a new template. A **stateful MIG** preserves disks or IPs.

```bash
gcloud compute instance-templates create web-v1 --machine-type=e2-medium \
  --image-family=debian-12 --image-project=debian-cloud --tags=http-server
gcloud compute health-checks create http web-hc --port=80
gcloud compute instance-groups managed create web-mig --zone=us-central1-a \
  --template=web-v1 --size=2 --health-check=web-hc --initial-delay=120
gcloud compute instance-groups managed set-autoscaling web-mig --zone=us-central1-a \
  --min-num-replicas=2 --max-num-replicas=10 --target-cpu-utilization=0.6
gcloud compute instance-groups managed rolling-action start-update web-mig \
  --zone=us-central1-a --version=template=web-v2
gcloud compute instance-groups managed recreate-instances web-mig \
  --zone=us-central1-a --instances=web-mig-abcd
```

### OS Login and VM Manager

- **OS Login**: SSH access through IAM roles (`compute.osLogin`, `compute.osAdminLogin`) instead of metadata SSH keys. Enable with metadata `enable-oslogin=TRUE` or enforce with an organization policy.
- **VM Manager** (OS Config): patch management, OS inventory, and vulnerability reports. It needs the OS Config API, the agent on the VM (`enable-osconfig=TRUE` metadata), and a path to the API.

## Advanced

### GKE

- **Autopilot**: Google manages nodes; you are billed for Pod resource requests. Always regional. Choose it for minimum operations.
- **Standard**: you manage node pools, machine types, and sizes. Choose it when you need node-level control or a fixed number of nodes (a fixed-size pool with autoscaling off).
- **Zonal** cluster: one zone, cheaper. **Regional** cluster: control plane and nodes across zones for high availability.
- **Private cluster**: nodes have only internal IPs; the control plane endpoint can be restricted with authorized networks. Nodes use Private Google Access for Google APIs and Cloud NAT for general internet access.
- **Release channels** (Rapid, Regular, Stable) control upgrades; Stable suits critical production.

```bash
gcloud container clusters create-auto app-auto --region=us-central1
gcloud container clusters create app-std --region=us-central1 --num-nodes=1
gcloud container clusters get-credentials app-std --region=us-central1
kubectl get nodes
kubectl create deployment web --image=us-docker.pkg.dev/cloudrun/container/hello
kubectl expose deployment web --type=LoadBalancer --port=80
kubectl scale deployment web --replicas=3
kubectl rollout status deployment/web
kubectl rollout undo deployment/web
kubectl get pods,svc -o wide
```

In a regional Standard cluster, `--num-nodes` is **per zone**.

### Node pools and autoscaling

- A **node pool** is a group of nodes with one configuration. A workload needing a different machine type goes in a **new node pool** in the same cluster. Spot node pools suit batch jobs.
- **HPA** changes the number of Pod replicas (based on CPU, memory, or custom metrics, as a percentage of requests). Pods need resource requests.
- **VPA** adjusts CPU and memory requests of Pods; it is the choice for a single-replica workload.
- **Cluster autoscaler** adds or removes nodes within the pool's min and max when Pods are unschedulable.

```bash
gcloud container node-pools create highmem --cluster=app-std --region=us-central1 \
  --machine-type=n2-highmem-4 --enable-autoscaling --min-nodes=0 --max-nodes=5
kubectl autoscale deployment web --cpu-percent=60 --min=2 --max=10
```

### Artifact Registry access from GKE

Nodes pull images as the **node service account**. Give that account `roles/artifactregistry.reader` on the repository (or project). No keys or image pull secrets are needed. Image path format: `LOCATION-docker.pkg.dev/PROJECT/REPO/IMAGE:TAG`.

### Cloud Run

- **Service**: serves requests; scales to zero. **Job**: runs to completion (`gcloud run jobs create/execute`). **Function**: source-based, from a trigger.
- Each deploy creates an immutable **revision**. **Traffic splitting** sends percentages to revisions, used for canary rollouts and rollback.
- **Min instances** keep warm instances to reduce cold starts. **Max instances** cap scale to protect backends such as a database. **Concurrency** is requests per instance (default 80); lower concurrency means more instances.
- **Ingress**: `all`, `internal`, or `internal-and-cloud-load-balancing`.
- **Invoker**: callers need `roles/run.invoker`. `--allow-unauthenticated` grants it to everyone.

```bash
gcloud run deploy web --image=us-docker.pkg.dev/cloudrun/container/hello \
  --region=us-central1 --min-instances=1 --max-instances=20 --concurrency=80 \
  --ingress=all --no-allow-unauthenticated
gcloud run deploy web --image=IMAGE:v2 --region=us-central1 --no-traffic --tag=canary
gcloud run services update-traffic web --region=us-central1 \
  --to-revisions=web-00002-abc=10,web-00001-xyz=90
gcloud run services update-traffic web --region=us-central1 --to-latest
```

After traffic is pinned to specific revisions, new deploys receive 0% until you run `--to-latest`.

### App Engine

An application (one per project, region fixed at creation) contains **services**, each with **versions**. Traffic is split between **versions of the same service**, not between services.

```bash
gcloud app deploy --version=v2 --no-promote
gcloud app services set-traffic default --splits=v1=0.9,v2=0.1 --split-by=random
```

## Exam tips

- Ready container image, serverless: Cloud Run service. Nightly container batch: Cloud Run job plus Scheduler. Upload-triggered snippet: Cloud Run function.
- Minimal ops and HA on Kubernetes: Autopilot. Fixed node count: Standard with autoscaling off.
- Different machine type for one workload: new node pool.
- HPA changes replicas, VPA changes Pod size, cluster autoscaler changes nodes. Single replica: VPA.
- Cold starts: min instances. Protect the database: max instances.
- "Send 8% to the new version": Cloud Run revisions or App Engine versions.
- GKE cannot pull images: node service account needs Artifact Registry Reader.
- Spot VMs for interruption-tolerant work only; a long non-interruptible job uses a regular VM.
- A MIG that will not recreate VMs: check the template and conflicting disk names.

## What appeared on the practice exams

Condensed from the 300 practice questions. Question IDs link to the full question and explanation.

### Compute Engine

- **Spot VMs:** interruption-tolerant workloads, with checkpointing. This is the cheapest option.
- **Regular VM:** a long 34-hour job, with no interruption tolerance, and occasional workloads (turned on and off).
- **MIG:** autoscaling by CPU, auto-healing and distribution across zones. Use a **stateful MIG** to keep the disk.
- **Disk:**
  - Snapshot schedule with retention for backup.
  - **Regional Persistent Disk** to survive a zone failure.
  - **Hyperdisk Extreme** for very high IOPS (SAP HANA).
- **Machines:**
  - M1 for high memory.
  - NVIDIA GPU for CUDA.
  - TPU for JAX and LLM training.
- **Protection:** *deletion protection* on the VM. Check the zones that support the GPU and the quotas before creating the template.
- **SSH:**
  - With a Google account and centralized: **OS Login** (group and IAM role), required by org policy.
  - Without an external IP: **IAP TCP forwarding**, with a firewall allowing `35.235.240.0/20`.
  - Without a Google account: SSH key in the metadata.
- **Cloud Workstations:** configuration with an approved image, persistent home and **idle timeout**.

### GKE

- **Autopilot** (regional, Google manages the nodes) vs. **Standard** (you control the node pools).
- **Stable release channel** for critical production.
- **Node pools:** Spot for batch, regular for the API. Cluster autoscaler with min/max.
- Commands:
  - `kubectl rollout undo` reverts a bad deploy.
  - **StatefulSet** with a persistent disk for databases.
  - **Config Connector** manages Google resources as Kubernetes objects. Deleting the object removes the real resource.
- **Image:** push it to Artifact Registry and create a **Deployment** that references it.

### Cloud Run, App Engine, and events

- **Cloud Run service:** HTTP, scales to zero, traffic split by revision, min-instances to reduce cold start and max-instances to limit load on the database.
- **Cloud Run jobs:** batch.
- **Events:** Pub/Sub and Eventarc.
- **Cloud Tasks / Scheduler:** scheduled or queued execution.
- **Private connection:** Direct VPC egress with ILB and private DNS.

## Official documentation
- [Custom machine types](https://docs.cloud.google.com/compute/docs/instances/creating-instance-with-custom-machine-type)
- [Spot VMs](https://docs.cloud.google.com/compute/docs/instances/spot)
- [Instance groups](https://docs.cloud.google.com/compute/docs/instance-groups)
- [Autohealing in MIGs](https://docs.cloud.google.com/compute/docs/instance-groups/autohealing-instances-in-migs)
- [Choose a GKE cluster mode](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/choose-cluster-mode)
- [Horizontal Pod autoscaling](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/horizontalpodautoscaler)
- [Integrating Artifact Registry with GKE](https://docs.cloud.google.com/artifact-registry/docs/integrate-gke)
- [What is Cloud Run](https://docs.cloud.google.com/run/docs/overview/what-is-cloud-run)
- [Rollouts, rollbacks, and traffic migration](https://docs.cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration)
- [App Engine traffic splitting](https://docs.cloud.google.com/appengine/docs/standard/splitting-traffic)

[Back to topic](README.md)
