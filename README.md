# EpicBook Dual-Pipeline DevOps Project

This repository serves as the central project workspace for the EpicBook AWS deployment and dual-pipeline CI/CD implementation.

## Repository Structure

| Directory | Description |
|---|---|
| `infra-epicbook/` | AWS infrastructure provisioning using Terraform |
| `theepicbook/` | EpicBook application source code and application CI/CD pipeline |
| `triage/` | AI-assisted pipeline failure diagnosis, Claude Code skill, and incident reports |

## Git Submodules

This project integrates two independently maintained GitHub repositories:

### 1. Infrastructure Repository
- **Repository:** [Felimek28/infra-epicbook](https://github.com/Felimek28/infra-epicbook)
- **Purpose:** AWS infrastructure provisioning and management using Terraform.
- **Pipeline:** Azure DevOps Infrastructure Pipeline.

### 2. Application Repository
- **Repository:** [Felimek28/theepicbook-cicd](https://github.com/Felimek28/theepicbook-cicd)
- **Purpose:** EpicBook application source code, testing, and deployment configuration.
- **Pipeline:** Azure DevOps Application Pipeline.

## Architecture and CI/CD

The project uses two independent Azure DevOps pipelines:

1. **Infrastructure Pipeline:** Provisions AWS resources using Terraform.
2. **Application Pipeline:** Builds, tests, and deploys the EpicBook application.

Ansible manages application server configuration and deployment.

## AI-Assisted Pipeline Triage

The `triage/` directory contains:
- Pipeline health and failure diagnosis script.
- Claude Code triage instructions and skill.
- Pipeline incident reports documenting failure diagnosis and recovery.

## Cloning the Project

Clone the parent repository together with both submodules:

```bash
git clone --recurse-submodules https://github.com/Felimek28/epicbook-dual-pipeline.git
```

Initialize submodules after cloning without the recursive option:

```bash
git submodule update --init --recursive
```

## Security

- Never commit personal access tokens, passwords, or private keys.
- Terraform state and sensitive variable files must remain outside Git.
- Keep database credentials and deployment secrets in secure pipeline variables or secret stores.
