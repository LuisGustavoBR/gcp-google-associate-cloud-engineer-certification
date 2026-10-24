# Config Connector

> **Level:** Advanced · **Topic:** [IaC, platform and AI tooling](../README.md) · **Cited in:** 2 practice-exam questions

## What it is

Manages Google Cloud resources (buckets, Pub/Sub topics, Cloud SQL) as **Kubernetes objects** (custom resources in YAML), through the same GitOps flow.

## Watch out

Deleting the object in the cluster removes the real resource in Google Cloud.

## Where it appeared

[E2Q37](../../99-practice-exams/exam-2.md#q37), [E3Q22](../../99-practice-exams/exam-3.md#q22).

## Related practice questions

| Question | Question stem |
|---|---|
| [E2Q37](../../99-practice-exams/exam-2.md#q37) | Northstar Media deploys its streaming services to Google Kubernetes Engine (GKE) by applying Kubernetes YAML m... |
| [E3Q22](../../99-practice-exams/exam-3.md#q22) | StreamForge operates a live-event notification platform that provisions Google Cloud resources through Config ... |

## Official documentation

- [Config connector / Managing deleting resources](https://docs.cloud.google.com/config-connector/docs/how-to/managing-deleting-resources)
- [Config connector / Annotations](https://docs.cloud.google.com/config-connector/docs/reference/annotations)
- [Config connector / Pubsubtopic](https://docs.cloud.google.com/config-connector/docs/reference/resource-docs/pubsub/pubsubtopic)
- [Config connector / Resources](https://cloud.google.com/config-connector/docs/concepts/resources)
- [Config connector / Overview](https://cloud.google.com/config-connector/docs/overview)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
