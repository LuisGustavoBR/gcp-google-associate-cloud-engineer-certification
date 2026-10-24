# Terraform

> **Level:** Basic · **Topic:** [IaC, platform and AI tooling](../README.md) · **Cited in:** 6 practice-exam questions

## What it is

Multicloud IaC.

## Triggers and facts

- Reusable mandatory standards: **modules** ([E1Q22](../../99-practice-exams/exam-1.md#q22), [E4Q28](../../99-practice-exams/exam-4.md#q28)).
- State: `gcs` backend with a protected bucket ([E3Q31](../../99-practice-exams/exam-3.md#q31)).
- Per-application operations: one root directory per application ([E2Q17](../../99-practice-exams/exam-2.md#q17)).
- Several cloud providers: Terraform with the providers ([E2Q31](../../99-practice-exams/exam-2.md#q31)).
- Same infrastructure across several environments: modules plus Infrastructure Manager ([E3Q32](../../99-practice-exams/exam-3.md#q32)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q22](../../99-practice-exams/exam-1.md#q22) | BrightCart, an online retail company, requires every Google Cloud resource to follow approved settings for net... |
| [E2Q17](../../99-practice-exams/exam-2.md#q17) | TrailCart runs a customer marketplace, a delivery portal, and an analytics application on Google Cloud. Each a... |
| [E2Q31](../../99-practice-exams/exam-2.md#q31) | OrbitFleet is migrating its containerized logistics applications to Kubernetes clusters running on Google Clou... |
| [E3Q31](../../99-practice-exams/exam-3.md#q31) | HarborCart operates an online grocery delivery platform and manages its Google Cloud resources with Terraform.... |
| [E3Q32](../../99-practice-exams/exam-3.md#q32) | Skyline Analytics needs to provision identical networking, Compute Engine, and Cloud Storage resources across ... |
| [E4Q28](../../99-practice-exams/exam-4.md#q28) | AeroPulse, a flight analytics company, has several application teams that create Google Cloud environments for... |

## Official documentation

- [Terraform / Terraform blueprints](https://docs.cloud.google.com/docs/terraform/blueprints/terraform-blueprints)
- [Terraform / Terraform overview](https://docs.cloud.google.com/docs/terraform/terraform-overview)
- [Terraform / Reusable modules](https://docs.cloud.google.com/docs/terraform/best-practices/reusable-modules)
- [Terraform / Intro](https://developer.hashicorp.com/terraform/intro)
- [Terraform / Gcs](https://developer.hashicorp.com/terraform/language/backend/gcs)
- [Terraform / Files](https://developer.hashicorp.com/terraform/language/files)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
