# Semaphore

Semaphore is used as the execution layer for this repository.

## Model

- GitHub stores playbooks and documentation
- Semaphore stores inventory, credentials and execution templates
- Sensitive variables are not kept in the public repo

## Why

This separation keeps the repository suitable for a public portfolio while still making it useful for real automation tasks.
