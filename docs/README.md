# Documentation Index

## Overview

This directory contains operational, architectural, and procedural documentation for the homelab environment.

The goal of this documentation structure is to:
- maintain operational clarity
- document infrastructure decisions
- reduce configuration drift
- support disaster recovery
- track architectural evolution
- create repeatable operational processes
- support public learning and portfolio development

Documentation is treated as part of the infrastructure itself.

---

# Documentation Philosophy

Core principles:
- Document changes immediately
- Prefer clarity over complexity
- Record known limitations
- Track architectural decisions
- Build repeatable operational procedures
- Treat the homelab like a production environment

---

# Directory Structure

| Directory | Purpose |
|---|---|
| `/architecture` | Infrastructure design, architecture overviews, limitations |
| `/network` | VLAN plans, IP schemes, network diagrams |
| `/runbooks` | Recovery procedures and operational workflows |
| `/inventory` | Service tracking and infrastructure inventory |
| `/notes` | Lessons learned and operational notes |
| `/standards` | Naming conventions and operational standards |
| `/content` | Content planning, branding, and publishing notes |

---

# Core Documents

| Document | Purpose |
|---|---|
| `architecture/overview.md` | High-level architecture overview |
| `architecture/known-limitations.md` | Current risks and technical debt |
| `network/network-plan.md` | Planned network segmentation and subnetting |
| `standards/naming-conventions.md` | Resource naming standards |
| `CHANGELOG.md` | Infrastructure and documentation changes |
| `README.md` | Repository overview |

---

# Operational Workflow

General workflow for infrastructure changes:

```txt
Plan
↓
Implement
↓
Validate
↓
Document
↓
Commit
```

Documentation should be updated during implementation rather than after major changes accumulate.

---

# Current Environment State

Current environment characteristics:
- Single Proxmox host
- OPNsense virtualized firewall
- TrueNAS VM storage
- PBS backups
- Flat network transitioning toward VLAN segmentation
- Cloudflare Tunnel remote access
- Documentation-first operational workflow

---

# Current Priorities

Active focus areas:
- Documentation discipline
- Network segmentation planning
- Monitoring and observability
- Backup resilience
- Infrastructure organization
- Security-focused architecture

---

# Future Goals

Planned future initiatives:
- VLAN implementation
- Centralized monitoring
- Centralized logging
- Infrastructure automation
- AI-assisted documentation
- Threat-intelligence tooling
- Malware-analysis environment
- Blue-team workflow development

---

# Documentation Standards

Guidelines:
- Markdown preferred
- Use descriptive filenames
- Avoid undocumented infrastructure changes
- Record architectural tradeoffs
- Keep diagrams updated as infrastructure evolves

---

# Notes

This environment is intentionally iterative.

The goal is not immediate perfection, but continuous operational improvement and realistic infrastructure growth.
