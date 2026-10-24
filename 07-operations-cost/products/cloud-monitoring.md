# Cloud Monitoring

> **Level:** Basic · **Topic:** [Operations and cost](../README.md) · **Cited in:** 4 practice-exam questions

## What it is

Metrics, dashboards, and **alerts**.

## Triggers and facts

- Alert on the MIG's average CPU for 7 minutes: metric-based policy filtered by the MIG ([E2Q34](../../99-practice-exams/exam-2.md#q34)).
- Latency above the threshold for 7 minutes: metric-based policy with a retest window ([E5Q5](../../99-practice-exams/exam-5.md#q5)).
- Several projects in a single view: **metrics scope** with one scoping project ([E4Q44](../../99-practice-exams/exam-4.md#q44)).
- Stuck Dataflow job: *data freshness* alert ([E5Q14](../../99-practice-exams/exam-5.md#q14)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E2Q34](../../99-practice-exams/exam-2.md#q34) | BrightCart runs an order-processing API on a regional Compute Engine managed instance group. The reliability t... |
| [E4Q44](../../99-practice-exams/exam-4.md#q44) | SkyRoute Logistics operates applications across Google Cloud projects Fleet-Core, Dispatch-Services, and Analy... |
| [E5Q5](../../99-practice-exams/exam-5.md#q5) | ShopPulse hosts its customer-order portal on Compute Engine virtual machines. The operations team must be noti... |
| [E5Q14](../../99-practice-exams/exam-5.md#q14) | StreamCart operates a real-time order-processing platform that uses several Dataflow streaming jobs. A recent ... |

## Official documentation

- [Monitoring / Alerts](https://docs.cloud.google.com/monitoring/alerts)
- [Monitoring / Using alerting ui](https://docs.cloud.google.com/monitoring/alerts/using-alerting-ui)
- [Monitoring / Metrics opsagent](https://docs.cloud.google.com/monitoring/api/metrics_opsagent)
- [Monitoring / Settings](https://docs.cloud.google.com/monitoring/settings)
- [Monitoring / Multiple projects](https://docs.cloud.google.com/monitoring/settings/multiple-projects)
- [Monitoring / Notification options](https://docs.cloud.google.com/monitoring/support/notification-options)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
