# Service Inventory

## Purpose

Track workloads, exposure levels, and operational importance.

| Service | Type | Exposure | Backup | Criticality | Notes |
|---|---|---|---|---|---|
| OPNsense | VM | Internal | Config export planned | Critical | Router, firewall, DHCP, DNS |
| PBS | VM | Internal | Partial | High | Stores Proxmox backups |
| TrueNAS | VM | Internal | Config/data focused | High | SMB, NFS, media, backups |
| Actual Budget | VM/App | Cloudflare Tunnel | Yes | Medium | Public web app |
| Minecraft Server | VM | Public IP | Yes | Medium | Public-facing, not isolated |

## Infrastructure

| Component | Details |
|---|---|
| Hypervisor | Proxmox |
| CPU | Intel i7-10700K |
| Memory | 48 GB RAM |
| Primary Storage | 1 TB SSD |
| Bulk Storage | 2x 2 TB HDD RAID1 |
| Network | 2 NICs |

## Current Concerns

- limited segmentation
- single host dependency
- no monitoring
- recovery testing incomplete
