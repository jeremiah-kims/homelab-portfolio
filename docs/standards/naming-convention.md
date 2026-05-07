# Naming Conventions

## Overview

Resources are named according to operational function and workload type.

Goals:
- Consistency
- Readability
- Automation friendliness
- Easy identification during troubleshooting
- Scalability as infrastructure grows

---

# Resource Prefixes

| Prefix | Purpose | Example |
|---|---|---|
| svc- | Application/service workloads | svc-minecraft |
| infra- | Core infrastructure services | infra-opnsense |
| mon- | Monitoring/observability | mon-grafana |
| auth- | Authentication/identity services | auth-authentik |
| dev- | Development/testing workloads | dev-sandbox |
| exp- | Experimental/high-risk systems | exp-malware-lab |

---

# Current Standards

## Service Workloads
Format:
```txt
svc-(service-name)
