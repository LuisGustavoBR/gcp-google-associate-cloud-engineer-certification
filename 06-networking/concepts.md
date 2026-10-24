# Networking: concepts from basic to advanced

> Official exam guide sections covered: 2.3, 3.5, 4.5 (see the [exam guide map](../00-start-here/exam-guide-map.md)).

## Basic

### VPC networks and subnets

A **VPC network** is a private, software-defined network. In Google Cloud a VPC is **global**, and its **subnets are regional**. VMs in different regions of one VPC talk over internal IPs with no VPN needed.

| Mode | Behavior |
|---|---|
| Auto mode | One subnet per region is created automatically from a fixed block (10.128.0.0/9). Convenient for learning. Cannot be peered with another auto mode network. |
| Custom mode | You create each subnet and choose its range. This is the production choice. |

An auto mode network can be converted to custom mode (one way only). The `default` network is auto mode and comes with permissive prefilled firewall rules.

```bash
gcloud compute networks create prod-vpc --subnet-mode=custom
gcloud compute networks subnets create web-subnet --network=prod-vpc \
    --region=us-central1 --range=10.10.0.0/24
```

**Adding a subnet** to an existing custom VPC is the command above with a new, non-overlapping range. **Expanding a subnet** increases its primary range in place, without downtime. A range can only grow, never shrink.

```bash
gcloud compute networks subnets expand-ip-range web-subnet \
    --region=us-central1 --prefix-length=22
```

Each primary range reserves four addresses (network, gateway, and two at the end). Secondary ranges provide alias IPs, for example GKE Pod and Service ranges.

### IP addresses

- **Internal IPs:** from the subnet range. Ephemeral by default; reserve a static internal IP to keep it.
- **External IPs:** ephemeral or static. Static external addresses are **regional** (VMs, regional load balancers) or **global** (global external load balancers).
- An ephemeral address in use can be promoted to static without interruption. A reserved but unused static external IP is billed.

```bash
gcloud compute addresses create web-ip --region=us-central1
gcloud compute addresses create lb-ip --global
gcloud compute addresses create db-ip --region=us-central1 \
    --subnet=web-subnet --addresses=10.10.0.50
```

### Firewall rules

VPC firewall rules are **stateful** (return traffic of an allowed connection is allowed) and are enforced at the VM, not at the subnet edge.

- Each rule has a direction (ingress or egress), an action (allow or deny), a priority (0 to 65535, **lower number wins**, default 1000), a protocol/port, and a target.
- **Implied rules** at lowest priority: deny all ingress, allow all egress. They cannot be deleted or logged.
- At equal priority, deny wins over allow.
- **Targets and sources:** all instances, **network tags**, or **service accounts**. Service accounts are more secure than tags because tags can be edited by anyone who can edit the VM.

```bash
gcloud compute firewall-rules create allow-https --network=prod-vpc \
    --direction=INGRESS --action=ALLOW --rules=tcp:443 \
    --source-ranges=0.0.0.0/0 --target-tags=web --priority=1000
gcloud compute firewall-rules create allow-from-app --network=prod-vpc \
    --allow=tcp:5432 --source-service-accounts=app@PROJECT.iam.gserviceaccount.com \
    --target-service-accounts=db@PROJECT.iam.gserviceaccount.com
```

## Intermediate

### Firewall policies and logging

- **Cloud NGFW firewall policies** can be attached to the organization, to a folder (**hierarchical policies**), or to a VPC network (network policies). Hierarchical policies are evaluated first. A rule can allow, deny, or `goto_next` to pass the decision down.
- **Secure tags** (resource-manager tags with IAM control) can be used as source and target in firewall policies, not in classic VPC firewall rules. Like service accounts, they suit VMs whose IPs change often.
- Central rule for the whole company (for example block SSH from the internet): hierarchical policy at the organization.
- **Firewall Rules Logging** is enabled per rule (`--enable-logging`) and shows which rule allowed or denied a connection. To log denied traffic that hits the implied rule, create an explicit deny-all rule with logging.
- **VPC Flow Logs** are enabled per subnet, sampled, and record connection metadata and byte counts, not packet content.

### Routes, Cloud Router and Cloud NAT

- **Routes** decide where packets go: system subnet routes, a default route (0.0.0.0/0 to the internet gateway), static custom routes, and dynamic routes learned by BGP. The most specific destination wins, then the lowest priority number.
- **Cloud Router** is a regional BGP speaker that exchanges routes with on-premises networks over VPN or Interconnect. It is also required for Cloud NAT.
- **Cloud NAT** gives outbound internet access to VMs and GKE nodes that have no external IP. It is egress only and cannot accept unsolicited inbound connections. You can use manual static NAT IPs when a partner allowlists addresses.

```bash
gcloud compute routers create nat-router --network=prod-vpc --region=us-central1
gcloud compute routers nats create nat-config --router=nat-router \
    --region=us-central1 --auto-allocate-nat-external-ips --nat-all-subnet-ip-ranges
```

### Reaching Google APIs and services privately

| Need | Use |
|---|---|
| VM with no external IP calls Google APIs (Cloud Storage, BigQuery) | **Private Google Access** on the subnet |
| Same VM downloads patches from the general internet | **Cloud NAT** |
| Reach Google APIs, or a published service such as Cloud Run, through an internal IP from the VPC and on-premises | **Private Service Connect** endpoint |

```bash
gcloud compute networks subnets update web-subnet --region=us-central1 \
    --enable-private-ip-google-access
```

Private Google Access is a per-subnet setting and still follows egress firewall rules.

### Connecting VPCs and projects

| Option | Key points |
|---|---|
| VPC Network Peering | Connects two VPCs privately. Non-transitive, no overlapping subnet ranges, configured on both sides. Simple and low cost. |
| Shared VPC | A host project owns the network, service projects use its subnets. Requires an organization. Grant `Compute Network User` on the host project or on specific subnets. |

```bash
gcloud compute shared-vpc enable HOST_PROJECT
gcloud compute shared-vpc associated-projects add SERVICE_PROJECT --host-project=HOST_PROJECT
gcloud compute networks peerings create a-to-b --network=vpc-a \
    --peer-network=vpc-b --peer-project=PROJECT_B
```

## Advanced

### Hybrid connectivity

- **HA VPN:** IPsec tunnels over the internet with dynamic routing through Cloud Router. It has a 99.99% SLA when configured with tunnels on both interfaces. Classic VPN is legacy.
- **Cloud Interconnect:** private physical connectivity. Dedicated Interconnect connects directly at a colocation facility. Partner Interconnect goes through a service provider and suits smaller bandwidth. Cross-Cloud Interconnect links to another cloud.
- Use a custom mode VPC for HA VPN. Active/active routing uses the capacity of both tunnels; active/passive keeps capacity when one path fails.

### Cloud DNS

- **Public zones** answer on the internet. **Private zones** answer only for the VPC networks you authorize and do not fall back to public DNS for that namespace.
- Other features: forwarding zones (send queries to on-premises DNS), inbound server policies (let on-premises resolve Google Cloud names), and DNS peering.
- **Apex rule:** a CNAME cannot be created at the zone apex (the bare domain, which already has SOA and NS records). Use A/AAAA at the apex and CNAME for subdomains such as `www`.

```bash
gcloud dns managed-zones create corp-zone --dns-name="example.com." \
    --description="Public zone" --visibility=public
gcloud dns record-sets create www.example.com. --zone=corp-zone \
    --type=A --ttl=300 --rrdatas=203.0.113.10
```

### Load balancer families

| Family | Layer and scope | Pick when |
|---|---|---|
| Application Load Balancer | L7 HTTP(S). External global or regional, internal regional | Web apps, URL maps, managed certificates, backend buckets, Cloud CDN and Cloud Armor. Global users, lowest latency. |
| Proxy Network Load Balancer | L4 TCP (and SSL) with a proxy | Non-HTTP TCP traffic that needs a global or proxy-based setup |
| Passthrough Network Load Balancer | L4 TCP/UDP, regional, external or internal | Preserve the client source IP, UDP, any port, no proxy |

Regional proxy-based load balancers need a proxy-only subnet. Only passthrough load balancers show the original client IP as the packet source.

### Network Service Tiers and VPC Flow Logs

- **Premium Tier** (default) carries traffic on Google's global backbone as far as possible. **Standard Tier** uses the public internet for more of the path, costs less, and is regional. A typical split is Standard for dev and Premium for production.
- Set it per resource with `--network-tier=STANDARD`, or change the project default.
- Flow Logs help with traffic analysis and cost investigation (for example inter-region traffic).

## Exam tips

- IP running out: **expand the primary range** of the subnet (grow only, no downtime). New workload in new space: add a subnet.
- Frequently replaced VMs (IP changes): firewall rules by **service account** or **secure tag**, not IP or tags.
- Rule for the entire organization: **hierarchical firewall policy** at the organization.
- Why is traffic blocked or allowed by rule X: **Firewall Rules Logging**. Bytes and metadata between regions: **VPC Flow Logs**.
- No external IP: Google APIs use **Private Google Access**; general internet uses **Cloud NAT**; internal-IP access to Cloud Run uses **Private Service Connect**.
- Two VPCs, simple and cheap: **VPC Peering** (no overlapping ranges, not transitive). Many projects in one organization sharing a network: **Shared VPC**.
- Dynamic route exchange with on-premises: **Cloud Router (BGP)**.
- CNAME at the apex is not allowed. A public name for a load balancer: an **A record** to its IP.
- HTTP(S) global: **Application Load Balancer**. TCP/UDP with client IP preserved: **Passthrough Network Load Balancer**.
- Cheaper network for non-critical workloads: **Standard Tier**.

## Official documentation
- [VPC networks](https://docs.cloud.google.com/vpc/docs/vpc)
- [Subnets](https://docs.cloud.google.com/vpc/docs/subnets)
- [VPC firewall rules](https://docs.cloud.google.com/firewall/docs/firewalls)
- [Firewall policies overview](https://docs.cloud.google.com/firewall/docs/firewall-policies-overview)
- [VPC Network Peering](https://docs.cloud.google.com/vpc/docs/vpc-peering)
- [Shared VPC](https://docs.cloud.google.com/vpc/docs/shared-vpc)
- [Cloud NAT overview](https://docs.cloud.google.com/nat/docs/overview)
- [Private Google Access](https://docs.cloud.google.com/vpc/docs/private-google-access)
- [Choose a load balancer](https://docs.cloud.google.com/load-balancing/docs/choosing-load-balancer)
- [Network Service Tiers](https://docs.cloud.google.com/network-tiers/docs/overview)

[Back to topic](README.md)
