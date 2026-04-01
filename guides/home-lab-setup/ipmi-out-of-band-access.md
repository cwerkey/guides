# IPMI / Out-of-Band Access

> Manual: Home Lab Setup  
> Last updated: 2026-04-01T22:34:30.055Z
## Overview

Configure IPMI on all bare-metal servers so they can be managed when the OS is down.

## Prerequisites

- Dedicated IPMI VLAN (VLAN 10)
- Static IP reservations in pfSense DHCP

## Configuration Steps

1. Boot into BIOS and navigate to IPMI settings.
2. Set IP mode to Static.
3. Assign IP from the `10.0.10.0/24` management range.
4. Set a strong password — default `ADMIN/ADMIN` must be changed.
5. Disable unused IPMI features (KVMIP if not needed).

## Accessing the Console

```
ssh admin@10.0.10.21
```

Or use the web UI at `https://10.0.10.21`.