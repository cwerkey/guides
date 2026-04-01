# VLAN Plan

> Manual: Networking  
> Last updated: 2026-04-01T22:34:30.055Z
## VLAN Assignments

| VLAN | Name | Subnet | Purpose |
|------|------|--------|---------|
| 1 | Default | 10.0.1.0/24 | Untagged legacy |
| 10 | MGMT | 10.0.10.0/24 | IPMI, switches, APs |
| 20 | Servers | 10.0.20.0/24 | Proxmox hosts |
| 30 | VMs | 10.0.30.0/24 | Guest VMs |
| 40 | IoT | 10.0.40.0/24 | IoT devices (isolated) |
| 50 | Trusted | 10.0.50.0/24 | Laptops, desktops |

## Firewall Rules

- IoT → no access to Servers or Trusted
- MGMT → only accessible from Trusted
- Servers → can reach internet via NAT