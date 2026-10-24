# Trigger cheat sheet

If the question stem says the phrase on the left, think of the product or setting on the right.

| If the question says... | Think... |
|---|---|
| contractor without a Google account, SSH | public key in the metadata |
| VM without an external IP, SSH | IAP TCP forwarding |
| external pipeline without a key | Workload Identity Federation |
| people from an external IdP | Workforce Identity Federation |
| Pod accessing a Google API | Workload Identity Federation for GKE |
| ready-made Docker image, serverless | Cloud Run service |
| nightly batch in a container | Cloud Run job and Cloud Scheduler |
| bucket upload triggers code | Cloud Run function and bucket trigger |
| without managing nodes | GKE Autopilot |
| fixed number of nodes | GKE Standard without autoscaling |
| 8% of traffic to the new version | revision (Cloud Run) or version (App Engine) |
| no external IP, reaches Google APIs | Private Google Access |
| no external IP, reaches the internet | Cloud NAT |
| ephemeral VM, firewall | service account or secure tag |
| rule for the whole organization | hierarchical firewall policy |
| global, consistent SQL | Spanner |
| telemetry and time series | Bigtable |
| multi-year copy of Cloud SQL | scheduled export to Archive |
| logs to an external SaaS | sink to Pub/Sub |
| who read objects | Data Access audit logs |
| budget that must stop a resource | budget, Pub/Sub, and Cloud Run function |
| health of the database fleet | Database Center |
| corporate SMB | NetApp Volumes |
| thousands of workers on shared files | Managed Lustre |

[Back](README.md)
