# Cloud Load Balancing

> **Level:** Intermediate · **Topic:** [Networking](../README.md) · **Cited in:** 4 practice-exam questions

## What it is

- **Application Load Balancer:** layer 7, HTTP(S), global or regional, with URL map, managed certificate, and backend buckets.
- **Network Load Balancer (passthrough):** TCP/UDP, regional, preserves the source IP.

## Trigger

"users on several continents, lowest latency": **global** external ALB ([E1Q33](../../99-practice-exams/exam-1.md#q33)). "Static and dynamic content on the same domain": URL map with backend bucket ([E4Q21](../../99-practice-exams/exam-4.md#q21)). "TCP on port 5222, source IP" or "game UDP": passthrough ([E4Q23](../../99-practice-exams/exam-4.md#q23), [E6Q36](../../99-practice-exams/exam-6.md#q36)).

## Related practice questions

| Question | Question stem |
|---|---|
| [E1Q33](../../99-practice-exams/exam-1.md#q33) | GlobeCart runs an online shopping website on Compute Engine. Its customer base is growing across North America... |
| [E4Q21](../../99-practice-exams/exam-4.md#q21) | Northstar Books operates a public ecommerce website on Compute Engine virtual machines in a managed instance g... |
| [E4Q23](../../99-practice-exams/exam-4.md#q23) | ConnectSphere operates a real-time messaging gateway on a Compute Engine managed instance group. The gateway r... |
| [E6Q36](../../99-practice-exams/exam-6.md#q36) | PixelRaid Studios operates a real-time multiplayer battle game on Google Cloud. Players connect from mobile de... |

## Official documentation

- [Load balancing / Choosing load balancer](https://docs.cloud.google.com/load-balancing/docs/choosing-load-balancer)
- [Load balancing / Passthrough network load balancer](https://docs.cloud.google.com/load-balancing/docs/passthrough-network-load-balancer)
- [Load balancing / Https](https://cloud.google.com/load-balancing/docs/https)
- [Load balancing / Udp with network load balancing](https://docs.cloud.google.com/load-balancing/docs/network/udp-with-network-load-balancing)
- [Load balancing / Proxy network load balancer](https://docs.cloud.google.com/load-balancing/docs/proxy-network-load-balancer)
- [Load balancing / Setup global ext https buckets](https://cloud.google.com/load-balancing/docs/https/setup-global-ext-https-buckets)

[Back to topic](../README.md) · [Glossary A-Z](../../glossary.md)
