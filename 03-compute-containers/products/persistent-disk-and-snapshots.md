# Persistent Disk and snapshots

> **Level:** Basic · **Topic:** [Compute and containers](../README.md) · **Cited in:** 3 practice-exam questions

## What it is

Network disk. The **regional** type replicates across two zones, and a **snapshot schedule** with retention is the native backup.

## Trigger

"survive a zone outage without restoring from backup" ([E5Q35](../../99-practice-exams/exam-5.md#q35)). "Daily backup with N-day retention" ([E1Q15](../../99-practice-exams/exam-1.md#q15), [E1Q40](../../99-practice-exams/exam-1.md#q40)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q15](../../99-practice-exams/exam-1.md#q15) | Northstar Clinic runs an appointment-processing application on a Compute Engine VM. Employees use the applicat... |
| [E1Q40](../../99-practice-exams/exam-1.md#q40) | MediRoute, a medical appointment mobile app, stores its scheduling database on a Persistent Disk attached to a... |
| [E5Q35](../../99-practice-exams/exam-5.md#q35) | HealthBridge Systems is moving a patient-records application from its private data center to Compute Engine. T... |

## Official documentation

- [Compute / About snapshot schedules](https://docs.cloud.google.com/compute/docs/disks/about-snapshot-schedules)
- [Compute / About](https://docs.cloud.google.com/compute/docs/disks/async-pd/about)
- [Compute / High availability regional persistent disk](https://docs.cloud.google.com/compute/docs/disks/high-availability-regional-persistent-disk)
- [Compute / Repd failover](https://docs.cloud.google.com/compute/docs/disks/repd-failover)
- [Compute / Scheduled snapshots](https://docs.cloud.google.com/compute/docs/disks/scheduled-snapshots)
- [Compute / Snapshot best practices](https://docs.cloud.google.com/compute/docs/disks/snapshot-best-practices)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
