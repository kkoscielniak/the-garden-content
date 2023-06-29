---
title: Internet Control Message Protocol
---

`/* [...] */`

IMCP supports many types of queries.

In [ping](/Knowledge/OffSec/tools/ping.md) we're relying on `ping` (`IMCP echo/type 8`) and `ping reply` (`IMCP echo reply/type 0`). If we want to ping a system on the same subnet, an [ARP](/Knowledge/Networking/ARP.md) query should precede the `ICMP Echo`.
