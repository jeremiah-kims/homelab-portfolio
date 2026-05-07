# Network Plan

## Overview

Current environment operates on a flat `192.168.0.0/24` network.

As the homelab evolves, services and devices will transition into segmented VLANs using `/24` subnet allocations under the `10.10.0.0/16` private address space.

Primary goals of segmentation:
- Improve security boundaries
- Reduce broadcast scope
- Isolate untrusted devices
- Support future infrastructure growth
- Simulate enterprise networking practices

---

# Planned VLAN Structure

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

# VLAN Definitions

## VLAN 10 — Management
Trusted administrative network.

Planned systems:
- Proxmox management
- PBS management
- OPNSense
- Hypervisor access
- Future firewall/switch management

---

## VLAN 20 — Servers
Primary infrastructure and application workloads.

Examples:
- Reverse proxies
- Grafana
- Authentication services
- Game servers
- Automation services

---

## VLAN 30 — Storage
Storage-related services and future NAS infrastructure.

Examples:
- TrueNAS
- NFS
- SMB
- Backup storage

---

## VLAN 40 — Kubernetes
Reserved for future Kubernetes workloads and experimentation.

---

## VLAN 50 — IoT
Untrusted or low-trust smart devices.

Goals:
- Internet access only
- Restricted internal access

---

## VLAN 60 — Guest
Guest-only network with no internal resource access.

---

## VLAN 70 — Experimental
High-risk testing and isolated experimentation environment.

Examples:
- TOR routing
- Malware analysis
- Security testing
- Experimental AI services
- Untrusted containers

---

# Notes

- VLAN implementation is planned but not yet deployed.
- Current infrastructure remains physically flat pending managed switching and firewall segmentation.
- Initial segmentation may be simulated virtually within Proxmox prior to full physical VLAN deployment.
