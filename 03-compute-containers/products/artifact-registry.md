# Artifact Registry

> **Level:** Basic · **Topic:** [Compute and containers](../README.md) · **Cited in:** 5 practice-exam questions

## What it is

Repository for container images and packages.

## Trigger

"push the image and create the Deployment" ([E2Q7](../../99-practice-exams/exam-2.md#q7), [E6Q33](../../99-practice-exams/exam-6.md#q33)) or "deploy directly to Cloud Run" ([E2Q29](../../99-practice-exams/exam-2.md#q29), [E6Q7](../../99-practice-exams/exam-6.md#q7)).

## Watch out

For GKE to pull private images, the **nodes' service account** needs `Artifact Registry Reader` ([E5Q34](../../99-practice-exams/exam-5.md#q34)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E2Q7](../../99-practice-exams/exam-2.md#q7) | PulseCart, an online retail company, has packaged its inventory API into a Docker image. The development team ... |
| [E2Q29](../../99-practice-exams/exam-2.md#q29) | StreamNest has completed a new release of its video-transcoding API and stored the production container image ... |
| [E5Q34](../../99-practice-exams/exam-5.md#q34) | NovaCart stores private container images in Artifact Registry for its online ordering platform. The cloud team... |
| [E6Q7](../../99-practice-exams/exam-6.md#q7) | FitMeal Labs has packaged its meal-planning web service as Docker container images. The company expects traffi... |
| [E6Q33](../../99-practice-exams/exam-6.md#q33) | ParcelPilot, a package-tracking website, has containerized its stateless API as a Docker image. The engineerin... |

## Official documentation

- [Artifact registry / Integrate GKE](https://docs.cloud.google.com/artifact-registry/docs/integrate-gke)
- [Artifact registry / Store docker container images](https://docs.cloud.google.com/artifact-registry/docs/docker/store-docker-container-images)
- [Artifact registry / Access control](https://docs.cloud.google.com/artifact-registry/docs/access-control)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
