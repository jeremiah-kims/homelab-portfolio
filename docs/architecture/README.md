# Architecture Overview

## Purpose

This homelab is designed as a structured infrastructure, cybersecurity, and learning environment.

Primary goals:
- Build operational discipline
- Develop blue team and infrastructure security skills
- Support threat intelligence, OSINT, and malware-analysis learning
- Create a public technical portfolio
- Document architecture decisions as the environment evolves

---

## Current Physical Infrastructure

The environment currently runs on a single consumer PC acting as the primary virtualization host.

| Component | Details |
|---|---|
| CPU | Intel i7-10700K |
| Memory | 48 GB RAM |
| Primary Storage | 1 TB SSD |
| Bulk Storage | 2x 2 TB HDD in RAID1 |
| Network | 2 NICs |
| Hardware Type | Consumer PC |

---

## Current Network Edge

Current network path:

```txt
ONT
↓
OPNsense VM
↓
Access Point
↓
Client Devices / Homelab Services
```

OPNsense is fully in-path and currently handles:
- Routing
- Firewalling
- DHCP
- DNS

---

## Core Platforms

| Platform | Type | Purpose |
|---|---|---|
| Proxmox | Bare-metal hypervisor | Primary virtualization platform |
| OPNsense | VM | Router, firewall, DHCP, DNS |
| TrueNAS | VM | SMB, NFS, media storage, backup storage |
| PBS | VM | Proxmox backup management |
| Cloudflare Tunnel | Service | Remote access to selected services |
| Actual Budget | Web application | Personal finance application |
| Minecraft Server | VM | Public-facing game server |

---

## Storage Architecture

TrueNAS runs as a VM and provides storage services.

Current TrueNAS roles:
- SMB shares
- NFS shares
- Media storage
- Backup storage target

Current storage layout:
- 2x 2 TB HDDs in RAID1
- Used as shared storage and backup destination

---

## Backup Architecture

PBS runs as a VM and stores Proxmox backups to TrueNAS.

Current backup behavior:
- Proxmox backups run daily
- Scheduled backup time: 9:00 PM
- Backup destination: TrueNAS storage

Known limitation:
- PBS and TrueNAS currently share the same physical host/failure domain as the primary workloads.

Risk:
- A major host failure may impact compute, storage, and backups together.

Future improvements:
- Dedicated PBS system
- Separate backup target
- Offsite replication
- Disaster recovery runbooks

---

## Remote Access

Remote access is currently provided through Cloudflare Tunnel.

Current externally accessible service:
- Actual Budget

Minecraft is public-facing.

No traditional NGINX Proxy Manager deployment is currently active.

---

## Authentication

Current authentication model:
- Local accounts only
- No centralized identity provider
- No SSO currently implemented

Future considerations:
- Authentik
- SSO
- MFA
- Role-based access control
- Admin-only management access

---

## Monitoring and Automation

Current state:
- No centralized monitoring
- No centralized logging
- No automation framework
- No infrastructure-as-code
- Documentation is manual

Future improvements:
- Uptime monitoring
- Grafana/Prometheus
- Centralized logging
- Ansible automation
- AI-assisted documentation workflow

---

## Network Segmentation

Current state:
- OPNsense is deployed and fully in-path
- VLAN plan exists
- Full VLAN segmentation is not yet implemented

Planned VLAN structure:

| VLAN | Purpose | Subnet |
|---|---|---|
| 10 | Management | 10.10.10.0/24 |
| 20 | Servers | 10.10.20.0/24 |
| 30 | Storage | 10.10.30.0/24 |
| 40 | Kubernetes | 10.10.40.0/24 |
| 50 | IoT | 10.10.50.0/24 |
| 60 | Guest | 10.10.60.0/24 |
| 70 | Experimental | 10.10.70.0/24 |

---

## Security Model

The environment is being designed around trust boundaries, controlled exposure, and blast-radius reduction.

Current concerns:
- Minecraft is public-facing and not yet isolated
- Management services require strong access control
- Backups share the same physical failure domain
- No centralized logging or monitoring yet

Security priorities:
- Isolate public-facing services
- Restrict management access
- Separate experimental workloads
- Add monitoring and logging
- Improve backup resilience
- Build malware-analysis and OSINT lab capabilities safely

---

## Current Pain Point

The largest current operational pain point is documentation.

Planned solution:
- Standardized markdown documentation
- GitHub-based documentation tracking
- Changelog updates
- AI-assisted documentation generation
- Manual review before merge

---

## Future Direction

Planned improvements:
- Implement VLAN segmentation
- Isolate Minecraft/public services
- Add monitoring and alerting
- Add centralized logging
- Add dedicated backup hardware
- Build runbooks
- Begin automation with Ansible or scripts
- Create AI-assisted documentation workflow
- Expand into blue team, threat intelligence, malware-analysis, and OSINT labs

---

## Architecture Philosophy

This homelab prioritizes:
- Operational discipline
- Security-conscious design
- Documentation-first habits
- Incremental improvement
- Learning in public
- Realistic infrastructure tradeoffs
