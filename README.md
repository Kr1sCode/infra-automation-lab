# Infrastructure Automation Lab

[![GitHub stars](https://img.shields.io/github/stars/Kr1sCode/infra-automation-lab?style=flat)](https://github.com/Kr1sCode/infra-automation-lab/stargazers)
[![License](https://img.shields.io/badge/license-see--LICENSE-blue)](LICENSE)
[![Last commit](https://img.shields.io/github/last-commit/Kr1sCode/infra-automation-lab)](https://github.com/Kr1sCode/infra-automation-lab/commits/main)

A curated set of Ansible playbooks for routine infrastructure operations in a mixed lab environment based on Proxmox, Linux and Windows Server.

This repository is a public portfolio project that presents selected automation examples used for patching, snapshot management and health checks.

Sensitive values, inventory details and runtime credentials are intentionally excluded from the repository.

## Scope

| Playbook | Use case |
|----------|----------|
| [debian.yml](./playbooks/debian.yml) | Debian/Ubuntu patching (`apt upgrade`) with kernel/reboot detection |
| [redhat.yml](./playbooks/redhat.yml) | RedHat/Fedora patching (`dnf`) with reboot detection |
| [win2022srv.yml](./playbooks/win2022srv.yml) | Windows Server security/critical updates via `ansible.windows.win_updates` |
| [autocreate.yml](./playbooks/autocreate.yml) | Daily Proxmox VM + LXC snapshot creation |
| [autoremove.yml](./playbooks/autoremove.yml) | Cleanup of Proxmox snapshots older than N days |
| [diskspace.yml](./playbooks/diskspace.yml) | Proxmox host health check — disk, CPU, memory |

## Dependencies

```bash
ansible-galaxy collection install -r requirements.yml
```

Collections: `ansible.windows` (Windows update playbook).

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
ansible-galaxy collection install -r requirements.yml
ansible-playbook -i inventory/example.ini playbooks/debian.yml
```

## CI

GitHub Actions runs [ansible-lint](.github/workflows/ansible-lint.yml) on every push to `main`.

## License

[MIT](./LICENSE) — Copyright (c) 2026 Krzysztof Gawkowski
