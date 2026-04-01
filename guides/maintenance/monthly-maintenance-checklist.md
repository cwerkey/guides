# Monthly Maintenance Checklist

> Manual: Maintenance  
> Last updated: 2026-04-01T22:34:30.055Z
## Schedule

Run on the first Saturday of each month.

## Tasks

### Physical
- [ ] Blow dust out of rack with compressed air
- [ ] Check all cable connections
- [ ] Verify UPS battery test passed

### Software
- [ ] Apply Proxmox updates: `apt update && apt dist-upgrade`
- [ ] Update pfSense packages
- [ ] Rotate logs older than 90 days
- [ ] Review Proxmox backup job results

### Security
- [ ] Review auth logs for anomalies
- [ ] Check for CVEs affecting running software
- [ ] Rotate service account passwords if flagged

## Post-Maintenance

Document any changes made in the WerkStack activity log.