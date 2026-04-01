# Proxmox Backup Strategy

> Manual: Maintenance  
> Last updated: 2026-04-01T22:34:30.055Z
## Backup Targets

| Target | Type | Retention |
|--------|------|-----------|
| TrueNAS NFS share | Proxmox Backup Server | 7 daily, 4 weekly |
| Offsite Backblaze B2 | rclone sync | 30 days |

## Proxmox Backup Job

Configured in **Datacenter > Backup**:
- Schedule: `0 2 * * *` (daily at 2AM)
- Mode: Snapshot
- Compression: zstd
- Nodes: all

## Restoring a VM

1. Go to the target node in Proxmox UI.
2. Select **Restore** from the backup storage.
3. Choose the snapshot date.
4. Restore to new VMID if testing, or overwrite existing.

## Offsite Sync

```bash
rclone sync /mnt/pbs-backups b2:homelab-backups --progress
```