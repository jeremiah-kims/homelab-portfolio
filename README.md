# homelab-portfolio

## Overview
This homelab is focused on developing practical skills in:
- networking
- virtualization
- security
- self-hosting
- infrastructure management

The environment is built primarily around Proxmox, OPNSense, and TrueNAS, with an emphasis on secure remote access, monitoring, automation, and operational best practices.

## Objectives: Utilize security and networking concepts in a tangible lab environment.

# Current Stack

## Infrastructure:
Proxmox Installation and Configuration
Proxmox Backup Server - Saves backups to HD array in TrueNAS.
OPNSense Installation and Configuration
TrueNAS Installation and Configuration
CloudFlare Tunnel - Enables HTTPS encryption and secure remote access with MFA to applications. 

## Applications:
Actual Budget Server - self hosted budgeting platform
Minecraft Server - providing secure, remote access

## Security:
Configured fail2ban
Configured SSH keys

## Networking:
Configured OPNSense Routing - manually configured DHCP, DNS, Static IPs

# Planned Implementations:
- Nginx configuration
- Static IPs for each host
- SSH Keys + Password disabling on all LXCs
- UFW + Fail2ban on all LXCs
- NPM Config
- Cloudflare DDNS
- Gitea configuration
- AdGuard Home
- Vaultwarden
- Jellyfin
- Uptime Kuma
- AD-DS
- SSO Config
- Ollama with VFIO for selfhosted AI
- VLAN Segmentation
- OPNSense Networking Rules: Firewall
- Wazuh SIEM Config
- Unattended updates configured
- Grafana / Prometheus config.

# Skills Developed

## Infrastructure & Virtualization
- Proxmox VE administration
- VM and LXC provisioning
- Backup and recovery workflows
- Storage management with TrueNAS

## Linux Administration
- Linux server configuration
- SSH hardening and key authentication
- System troubleshooting
- Package and service management

## Networking
- OPNSense firewall/router configuration
- DHCP and DNS management
- Static IP allocation
- Reverse proxy and secure remote access concepts
- VLAN and subnet planning

## Security
- Fail2ban configuration
- MFA-enabled remote access with Cloudflare Tunnel
- SSH key authentication
- Firewall rule configuration
- Secure service exposure practices

## Self-Hosting & Platform Engineering
- Containerized/self-hosted applications
- Infrastructure documentation
- Backup strategy implementation
- Service monitoring planning
- Homelab architecture design

## Future Areas of Development
- SIEM and observability
- Identity and access management (SSO/AD-DS)
- Kubernetes and orchestration
- AI infrastructure and GPU passthrough
- Network segmentation and zero-trust concepts

# Lessons Learned

# Timeline
