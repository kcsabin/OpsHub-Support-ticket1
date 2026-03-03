# OpsHub-Support-ticket1

A GitHub-based support ticketing repository for the **Technology and Transformation (TnT)** organization, used to manage and triage support issues across product teams and squads.

## Overview

This repository serves as a central support hub that leverages GitHub Issues, Issue Templates, Labels, and GitHub Actions to streamline the intake, categorization, and routing of support requests to the appropriate product Kanban boards.

## Issue Templates

Issues can be submitted using one of the following templates located in `.github/ISSUE_TEMPLATE/`:

| Template | Label | Purpose |
|---|---|---|
| **Bug** | `bug` | Report a bug found in a product within the organization |
| **Service Request** | `service-request` | Request a service for a product in the organization |
| **Quick Question** | `question` | Submit a quick question |

## Labels

Labels are managed as code via `.github/ISSUE_TEMPLATE/labels.yml` using the [ghaction-github-labeler](https://github.com/crazy-max/ghaction-github-labeler) action.

Labels include:

- **Product labels** – `DM`, `DBaaS`, `CaaS`, `GaaS`, `OB`, `DTE`, `DX`, `KaaS`, `SRE`, `BO`, `DC`, and more
- **Squad labels** – `Rogue One`, `Phenoms`, `GeekGurus`, `Tech Hawks`, `Crazy 8`, `District 9`, `Ctl-Alt-Complete`, `Oceans11`, `KubeGeek`, and more
- **Work item labels** – `epic`, `bug`, `service-request`, `feature-request`, `question`, `blocked`
- **Story point labels** – `Points: 0` through `Points: 5`
- **Work type labels** – `Work Type: 1` through `Work Type: 7`
- **Feature type labels** – `Feature Type: 1` through `Feature Type: 8`

## GitHub Actions Workflows

| Workflow | File | Trigger | Description |
|---|---|---|---|
| **Create TnT Labels** | `create-labels.yml` | Push to `main`/`master` on `labels.yml`, or manual dispatch | Syncs labels defined in `labels.yml` to the repository |
| **Triage Issues to Product Kanban Boards** | `triage-project-issues.yml` | Issue labeled | Automatically adds labeled issues (`bug`, `service-request`, `feature-request`, `question`) to the **TnT Support Kanban** project board under the **To do** column |
| **Remove Project Issues** | `remove-project-issues.yml` | Issue events | Removes issues from the project board as needed |
| **Sync Template** | `sync-template.yml` | Template sync events | Keeps this repository in sync with the template repository |

## Squad Configuration

This repository is associated with the **GeekGurus** squad (ID: `1302960`) as defined in `aa.yaml`.

## Code Owners

Changes to issue templates and label/issue workflows are owned by [@shaunaa126](https://github.com/shaunaa126) and [@echojiang](https://github.com/echojiang).

## Additional Resources

- [TnT Single Backlog Workflow](https://wiki.aa.com/bin/view/Technology%20and%20Transformation%20(TnT)%20Technology%20Operating%20Model/TnT%20Single%20Backlog%20Workflow/)
- [TnT Operating Model](https://wiki.aa.com/bin/view/Main/Technology%20and%20Transformation/)
