# Proxmox Homelab

A hands-on homelab environment built to develop practical experience in
virtualization, Linux system administration, infrastructure monitoring,
networking, automation, and security.

## 🖥️ Lab Overview

My homelab is built around a Lenovo ThinkCentre running Proxmox VE as the
hypervisor.

Current environment:

- Proxmox VE 9
- Ubuntu Server 24.04 LTS VM
- Uptime Kuma LXC container
- Windows 11 VM
- ProxMenux Monitor
- QEMU Guest Agent
- Discord monitoring notifications

## 🔍 Monitoring

I deployed Uptime Kuma to monitor the availability of my infrastructure.

Currently monitored:

- Proxmox Host
- Proxmox VE web interface
- Ubuntu Server
- ProxMenux Monitor

Discord notifications are configured to report when monitored services
go down and when they recover.

## ⚙️ Automated Startup & Recovery

The environment is configured to automatically recover after a Proxmox
host reboot.

Startup sequence:

1. Ubuntu Server VM starts automatically.
2. Proxmox waits before starting the next service.
3. Uptime Kuma starts automatically.
4. Monitoring resumes without manual intervention.

I tested this configuration by rebooting the Proxmox host and verifying
that the Ubuntu Server VM and Uptime Kuma container recovered
successfully.

## 🛠️ Troubleshooting Experience

During the build I encountered and resolved issues involving:

- QEMU Guest Agent installation and configuration
- Proxmox Guest Agent integration
- VM IP address visibility
- Service monitoring
- Discord alert testing
- Startup ordering and delays

## 🚧 Future Projects

This homelab will continue to expand with projects involving:

- Windows Server
- Active Directory Domain Services
- DNS
- Group Policy
- Linux administration
- Docker
- Network segmentation
- Backup and disaster recovery
- Security monitoring

## 🎯 Purpose

The purpose of this lab is to build practical IT infrastructure skills
through implementation, troubleshooting, testing, and documentation.
