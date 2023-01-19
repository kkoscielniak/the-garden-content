---
title: Internet Control Message Protocol
---

`/* [...] */`

IMCP supports many types of queries.

In [[cybersecurity/knowledge/tools/ping]] we're relying on `ping` (`IMCP echo/type 8`) and `ping reply` (`IMCP echo reply/type 0`). If we want to ping a system on the same subnet, an [[networks/ARP]] query should precede the `ICMP Echo`.
