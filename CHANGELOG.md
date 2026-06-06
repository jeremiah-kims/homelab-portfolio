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

 ## 2026-06-04

### Network

* Defined VLAN 20 (Servers) firewall rules

  * Allow management access from VLAN 10
  * Allow SMB/NFS access to storage services
  * Allow PBS backup traffic
  * Block access to Management VLAN
  * Block unauthorized storage access
  * Block access to other internal VLANs
  * Allow internet access

* Defined VLAN 30 (Storage) firewall rules

  * Allow management access from VLAN 10
  * Allow SMB/NFS traffic from Servers VLAN
  * Allow PBS backup traffic
  * Block all outbound traffic initiated by storage systems
  * Block internet access from storage systems

* Defined VLAN 50 (IoT) firewall rules

  * Block access to RFC1918 internal networks
  * Allow DNS, NTP, HTTP, and HTTPS outbound traffic

* Defined VLAN 60 (Guest) firewall rules

  * Block access to RFC1918 internal networks
  * Allow internet access

* Defined VLAN 70 (Experimental) firewall rules

  * Block all internal network access
  * Block internet access
  * Prevent inbound access from other VLANs

### Troubleshooting

* Investigated PBS connectivity issues after VLAN deployment
* Identified storage connectivity issues between PBS and TrueNAS
* Deferred troubleshooting until VLAN deployment is complete

### Professional Development

* Began CySA+ certification study
* Continued security-focused networking and segmentation research

  ## 2026-06-06

### Network
* Attempted to migrate from 192.x.x.x addreses to 10.x.x.x addresses and apply VLAN tagging.
* Unable to apply, lacking managed switch capabilities and current AP does not support tagging.
