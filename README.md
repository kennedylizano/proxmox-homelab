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

The homelab includes two recovery mechanisms designed to reduce manual intervention and improve service availability.

### Host Reboot Recovery

Proxmox is configured to automatically restore the environment after a host reboot.

Startup sequence:

1. Ubuntu Server VM starts automatically.
2. Proxmox waits before starting the next service.
3. Uptime Kuma starts automatically.
4. Monitoring resumes without manual intervention.

This configuration was tested by rebooting the Proxmox host and verifying that the Ubuntu Server VM and Uptime Kuma container recovered successfully.

### Automated VM Recovery

A custom Bash recovery script and systemd timer monitor the power state of Ubuntu Server VM 100.

The recovery check runs every 60 seconds. If VM 100 is detected as stopped, Proxmox automatically issues a start command without requiring manual intervention.

The recovery workflow was successfully tested by intentionally shutting down VM 100. The system detected the stopped VM and automatically started it again.

During the test, Uptime Kuma briefly entered a Pending state because the automated recovery completed before the outage detection threshold was reached.

Full configuration, testing procedure, logs, and screenshots are documented in:

➡️ [Project 01 — Infrastructure Monitoring & Automated Recovery](docs/01-monitoring-and-recovery.md)

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
