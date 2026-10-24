# Identity and security: concepts from basic to advanced

> Official exam guide sections covered: 1.1, 5.1, 5.2 (see the [exam guide map](../00-start-here/exam-guide-map.md)).

## Basic

### The IAM model

IAM answers "who can do what on which resource".

- **Principal**: who. A Google account, a group, a service account, a Workspace or Cloud Identity domain, or a federated identity.
- **Permission**: one allowed operation, such as `compute.instances.start`.
- **Role**: a named collection of permissions.
- **Allow policy**: attached to a resource, it holds a list of **bindings**. Each binding connects one role to one or more principals (and optionally a condition).

```bash
gcloud projects add-iam-policy-binding my-project \
  --member="group:devops@example.com" --role="roles/compute.admin"
gcloud projects get-iam-policy my-project
gcloud projects get-ancestors-iam-policy my-project   # includes inherited policies
```

**Inheritance**: policies flow down organization, folder, project, resource. The effective access is the **union** of what is granted at every level. A lower-level policy cannot remove a grant inherited from above. To block inherited access, change the grant at its source, change group membership, or use an **IAM deny policy** (evaluated before allow policies).

Grant roles to **groups** rather than individuals, at the **lowest level** that works.

### Role types

| Type | Description | Use |
|---|---|---|
| Basic | Owner, Editor, Viewer (and Browser). Very broad. | Avoid in production |
| Predefined | Managed by Google per service, fine grained | Default choice |
| Custom | You pick the permissions; maintained by you | When no predefined role fits, or you need stable permissions |

Least privilege means the narrowest predefined role on the narrowest resource. Example: read-only access to one bucket is `roles/storage.objectViewer` on that bucket, not a custom role at project level. Custom roles are defined at project or organization level, and Google may change predefined roles over time, which is the reason to use a custom role when you need a fixed permission set. `gcloud iam roles copy` can start a custom role from an existing one.

### Service accounts

A service account is an identity for software, not a person.

- **User-managed**: you create them (`NAME@PROJECT_ID.iam.gserviceaccount.com`). Best practice is one per workload.
- **Default service accounts**: created automatically by some services (Compute Engine, App Engine). The Compute Engine default has historically been given the broad Editor role, so create a dedicated account instead.
- **Service agents**: Google-managed accounts (`service-PROJECT_NUMBER@...`) that let a service act on your resources. Do not delete them or strip their roles. If something breaks after a role removal, restore the documented role.

A service account is also a **resource**: you control who can use it through its own IAM policy.

## Intermediate

### Attaching and using service accounts

- **Attach** a service account to a VM, Cloud Run service, or GKE node pool so code gets credentials from the metadata server, with no keys.
- Attaching requires `roles/iam.serviceAccountUser` on that service account.
- On a VM, changing the account needs the VM stopped (`gcloud compute instances set-service-account`). Access scopes on a VM intersect with IAM roles.

| Role | Allows |
|---|---|
| Service Account User | Attach the account to a resource, run as it |
| Service Account Token Creator | Impersonate it: mint short-lived tokens |
| Service Account Creator | Create accounts only |
| Service Account Admin | Manage the account and its IAM policy |

Granting these roles at project level covers every service account there, which enables privilege escalation. Prefer granting on the specific account.

### Keys vs short-lived credentials

Downloaded **keys** do not expire by default, can leak, and must be rotated by you. Prefer, in order: an attached service account, **impersonation**, **Workload Identity Federation**, and only then keys. Organization Policy constraints can block key creation (`iam.disableServiceAccountKeyCreation`), and newer organizations enforce this by default.

**Impersonation**: a principal with Token Creator on the service account gets short-lived tokens (one hour by default) and acts as it. Developers test least-privilege this way without a key.

```bash
gcloud iam service-accounts create deployer --display-name="CI deployer"
gcloud iam service-accounts add-iam-policy-binding \
  deployer@my-project.iam.gserviceaccount.com \
  --member="user:dev@example.com" --role="roles/iam.serviceAccountTokenCreator"
gcloud storage ls --impersonate-service-account=deployer@my-project.iam.gserviceaccount.com
gcloud config set auth/impersonate_service_account deployer@my-project.iam.gserviceaccount.com
```

### Application Default Credentials (ADC)

Client libraries look for credentials in this order: the `GOOGLE_APPLICATION_CREDENTIALS` file, credentials from `gcloud auth application-default login`, then the service account attached to the runtime (metadata server). Code that works on a laptop and then runs on a VM usually needs an attached service account.

### Cloud Identity and Directory Sync

- **Cloud Identity** (Free or Premium) manages users, groups, and MFA, and creates the organization node for a domain.
- **Google Cloud Directory Sync (GCDS)** copies users and groups from LDAP or Active Directory to Cloud Identity. It is **one-way**: the directory is the source of truth.
- Personal accounts already using a corporate email can be moved with a transfer invitation.
- For IAM, use a **security group** and enable MFA.

### Organization Policy vs IAM

- IAM controls **who** can act. Organization Policy controls **what is allowed**, even for Owners.
- Constraints are set at organization, folder, or project and inherit down. They are not retroactive: existing resources are not changed.

```bash
cat > policy.yaml <<'EOF'
name: organizations/123456789/policies/iam.disableServiceAccountKeyCreation
spec:
  rules:
  - enforce: true
EOF
gcloud org-policies set-policy policy.yaml
```

Common constraints: `gcp.resourceLocations` (allowed regions), `gcp.restrictServiceUsage`, `iam.allowedPolicyMemberDomains` (restrict members to your domains; existing external members must be removed manually), `compute.requireOsLogin`, `compute.vmExternalIpAccess`.

## Advanced

### Federation

| | Workload Identity Federation | Workforce Identity Federation |
|---|---|---|
| For | Software outside Google Cloud (GitHub Actions, AWS, Azure, on-premises) | People from an external IdP |
| Setup | Workload identity pool + provider (OIDC, SAML, AWS) | Workforce pool at the organization + provider |
| Result | Short-lived tokens, optionally by impersonating a service account | Sign-in with no Cloud Identity account per person |

Both map external **attributes** (claims) to Google attributes, and an **attribute condition** limits who may federate. IAM can grant roles to a `principalSet` built from an attribute, so changing a user's team in the IdP changes access. A pipeline typically gets `roles/iam.workloadIdentityUser` on a least-privilege service account.

**Workload Identity Federation for GKE** is a separate feature: a Pod uses its Kubernetes service account to call Google APIs with no key. Do not confuse the three.

### Keys, encryption, and secrets

- **Cloud KMS** hierarchy: key ring (has a location), key, key version. Services use **customer-managed encryption keys (CMEK)** when the key location matches the resource.
- The **service agent** of the consuming service needs `roles/cloudkms.cryptoKeyEncrypterDecrypter` on the key. Example: the Cloud Storage service agent of the bucket's project.
- Rotation creates a new primary version; **older versions still decrypt old data**. Disabling or destroying a version makes data encrypted with it unreadable. If a service suddenly fails with CMEK, re-enable the key version.
- An organization policy can require CMEK for chosen services.
- **Secret Manager** stores API keys and passwords as versioned secrets, controlled by IAM (`roles/secretmanager.secretAccessor`). Use it instead of environment files on VMs.

```bash
gcloud kms keyrings create app-ring --location=us-central1
gcloud kms keys create app-key --keyring=app-ring --location=us-central1 --purpose=encryption
gcloud secrets create db-password --data-file=pw.txt
gcloud secrets versions access latest --secret=db-password
```

### Cloud Audit Logs

- **Admin Activity** and **System Event**: always on, free.
- **Data Access**: off by default (except BigQuery); enable per service. Needed to answer "who read these objects?". Viewing them needs `roles/logging.privateLogViewer`.
- **Policy Denied**: logged when a security policy denies access.

### Remote access: IAP and OS Login

- **IAP TCP forwarding** gives SSH or RDP to VMs without external IPs: allow ingress from `35.235.240.0/20` and grant `roles/iap.tunnelResourceAccessor`, then `gcloud compute ssh VM --tunnel-through-iap`.
- **OS Login** ties Linux accounts to IAM: `roles/compute.osLogin`, or `roles/compute.osAdminLogin` for sudo. The user also needs Service Account User if the VM runs as a service account. Enforce it with `compute.requireOsLogin`.
- People without a Google identity (a contractor, for example) cannot use IAP or OS Login: add their public SSH key to metadata.

## Exam tips

- Pod needs Google APIs, no key: Workload Identity Federation for GKE. External pipeline: Workload Identity Federation plus impersonation. External employees with their own IdP: Workforce.
- "Test as a service account without a key": Token Creator and impersonation.
- Attach needs Service Account User. Impersonate needs Token Creator.
- "Block external accounts": `iam.allowedPolicyMemberDomains`, then remove existing members manually.
- Org-wide location restriction: apply at the organization. Group of projects: folder.
- Stable permissions despite Google changes: custom role.
- A deny policy overrides allows. Allow policies alone cannot revoke inherited access.
- Data Access audit logs must be enabled before the access happens.

## Official documentation
- [IAM overview](https://docs.cloud.google.com/iam/docs/overview)
- [Choose a role type](https://docs.cloud.google.com/iam/docs/choose-role-type)
- [Service accounts overview](https://docs.cloud.google.com/iam/docs/service-account-overview)
- [Service account impersonation](https://docs.cloud.google.com/iam/docs/service-account-impersonation)
- [Workload Identity Federation](https://docs.cloud.google.com/iam/docs/workload-identity-federation)
- [Workforce Identity Federation](https://docs.cloud.google.com/iam/docs/workforce-identity-federation)
- [Application Default Credentials](https://docs.cloud.google.com/docs/authentication/application-default-credentials)
- [Organization Policy overview](https://docs.cloud.google.com/organization-policy/overview)
- [Using Cloud KMS keys with Google Cloud services](https://docs.cloud.google.com/kms/docs/use-keys-google-cloud)
- [Cloud Audit Logs](https://docs.cloud.google.com/logging/docs/audit)

[Back to topic](README.md)
