# pfSense WAN Failover

> Manual: Networking  
> Last updated: 2026-04-01T22:34:30.055Z
## Overview

Configure dual-WAN failover using pfSense gateway groups.

## WAN Interfaces

- **WAN1**: Comcast (primary) — `em0`
- **WAN2**: T-Mobile 5G (backup) — `em1` via USB adapter

## Steps

1. In pfSense, go to **System > Routing > Gateways**.
2. Add both WAN gateways.
3. Under **Gateway Groups**, create group `WAN_FAILOVER`:
   - WAN1: Tier 1
   - WAN2: Tier 2
4. Update firewall rules to use `WAN_FAILOVER` as the gateway.
5. Test by unplugging WAN1 — traffic should switch within 30s.

## Monitoring

Enable DPINGER for latency-based failover. Set trigger threshold to 200ms.