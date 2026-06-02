# Changelog

## 2026-05-07

### Documentation
- Created `docs/architecture/README.md`
- Created `docs/network/README.md`
- Created `docs/standards/README.md`
- Updated `docs/README.md`

### Standards
- Standardized folder-level documentation using `README.md`

## 2026-05-08

### Documentation
- Created `docs/architecture/known-limitations`
- Created `docs/inventory/README.md`

### Configuration
- Removed PBS and TrueNAS from daily Proxmox backup

## 2026-05-30
### Configuration
- Set PBS backup retention schedules: Keep Last: 3, Keep Daily: 7, Keep Weekly: 4, Keep Monthly: 3
- Enabled PBS integrity checking on datastore
### Testing
- Stopped VM 100 (`svc-minecraft`) for restore test
- Restored Minecraft backup to test VM 999
- Verified `whitelist.json` present at `/opt/minecraft/`
- Destroyed VM 999 after successful validation

## 2026-05-31
### Configuration
- Restricted TrueNAS dataset ACLs to single production user
### Bugfix
- Fixed PBS chunk store inaccessible at boot due to NFS mount failing
  - Corrected fstab share path from `/mnt/pool/Proxmox_Backup` to `/mnt/Hoard/Proxmox_Backup`
  - Added `_netdev` and systemd network dependencies to fstab entry
  - Re-registered existing datastore in PBS config rather than reinitializing

## 2026-06-01
### Network
- Defined VLAN 10 (Management) firewall rules
  - Block intra-VLAN hairpin traffic
  - Allow TCP 443, 80 from MGMT to any (web UI)
  - Allow TCP 22 from MGMT to any (SSH)
  - Allow ICMP from MGMT to any (ping)
  - Allow all outbound from MGMT (admin catch-all)
  - Block all inbound to MGMT from any
