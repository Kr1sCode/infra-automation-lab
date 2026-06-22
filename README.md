# Infrastructure Automation Lab

A curated set of Ansible playbooks for routine infrastructure operations in a mixed lab environment based on Proxmox, Linux and Windows Server.

This repository is a public portfolio project that presents selected automation examples used for patching, snapshot management and health checks.  
Sensitive values, inventory details and runtime credentials are intentionally excluded from the repository.

## Scope

Included playbooks cover:

- Debian / Ubuntu patching with reboot logic
- RedHat / Fedora patching with reboot detection
- Windows Server update automation
- Proxmox VM and LXC snapshot creation
- Snapshot cleanup based on age
- Infrastructure health checks for Proxmox hosts

## Why this repository exists

The goal of this repository is to present a practical approach to operational automation in infrastructure environments.

It focuses on:
- repeatable administration tasks,
- reducing manual effort,
- safer maintenance workflows,
- separation of automation logic from secrets and runtime configuration.

## Semaphore workflow

These playbooks are intended to be executed through Semaphore UI.

In the operational setup:
- the GitHub repository stores playbooks only,
- inventories are managed separately,
- credentials and secrets are not stored in the repository,
- runtime variables are handled outside the public source tree.

This keeps the repository safe for public presentation while still showing the automation logic.

## Example execution

```bash
ansible-playbook -i inventory/example.ini playbooks/debian.yml
```
