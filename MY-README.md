# OpsHub Support Ticket Repository

This repository is a GitHub-based support ticketing system for the **Technology and Transformation (TnT)** team. It provides structured issue templates, automated label management, and Kanban board triage workflows to streamline support requests.

---

## Table of Contents

- [Overview](#overview)
- [Issue Templates](#issue-templates)
- [Labels](#labels)
- [GitHub Actions Workflows](#github-actions-workflows)
- [Repository Structure](#repository-structure)
- [Code Owners](#code-owners)
- [References](#references)

---

## Overview

This repo enables teams to submit and track support requests using GitHub Issues. Issues are automatically triaged onto the **TnT Support Kanban** board based on their label. It follows the [TnT Single Backlog Workflow](https://wiki.aa.com/bin/view/Technology%20and%20Transformation%20(TnT)%20Technology%20Operating%20Model/TnT%20Single%20Backlog%20Workflow/) and the [TnT Operating Model](https://wiki.aa.com/bin/view/Main/Technology%20and%20Transformation/).

---

## Issue Templates

Three issue templates are available when opening a new issue:

| Template | Label | Purpose |
|---|---|---|
| **Bug** | `bug` | Report a bug for a product in the organization |
| **Service Request** | `service-request` | Request a service for a product in the organization |
| **Quick Question** | `question` | Ask a general question |

Each template is located under `.github/ISSUE_TEMPLATE/`.

---

## Labels

Labels are managed as code via `.github/ISSUE_TEMPLATE/labels.yml` using the [ghaction-github-labeler](https://github.com/crazy-max/ghaction-github-labeler) action. Labels include product labels, squad labels, and work item types such as:

- `bug`, `service-request`, `feature-request`, `question`
- `DM`, `DBaaS`
- `Squad1`, `Squad2`
- `Epic`, `User Story`
- `Points: 3`, etc.

---

## GitHub Actions Workflows

| Workflow | Trigger | Description |
|---|---|---|
| `create-labels.yml` | Push to `main`/`master` (labels.yml changes) or manual dispatch | Creates/updates labels from `labels.yml` |
| `triage-project-issues.yml` | Issue labeled | Adds labeled issues to the **TnT Support Kanban** board under *To do* |
| `remove-project-issues.yml` | Issue unlabeled | Removes issues from the **TnT Support Kanban** board |
| `sync-template.yml` | Push to `main` | Syncs workflow files and templates to downstream repositories |

---

## Repository Structure

```
OpsHub-Support-ticket1/
├── README.md                        # Brief repo description
├── MY-README.md                     # This file
├── aa.yaml                          # Squad/tool configuration (Geek Gurus - 1302960)
└── .github/
    ├── ABOUTME.md                   # Notes on templates and actions used
    ├── CODEOWNERS                   # Code ownership assignments
    ├── ISSUE_TEMPLATE/
    │   ├── bug-template.md          # Bug report template
    │   ├── question-template.md     # Quick question template
    │   ├── servicerequest-template.md # Service request template
    │   └── labels.yml               # Label definitions (managed as code)
    └── workflows/
        ├── create-labels.yml        # Label management workflow
        ├── triage-project-issues.yml # Issue triage workflow
        ├── remove-project-issues.yml # Issue removal workflow
        └── sync-template.yml        # Template sync workflow
```

---

## Code Owners

Issue templates and workflow files are owned by:

- [@shaunaa126](https://github.com/shaunaa126)
- [@echojiang](https://github.com/echojiang)

---

## References

- [TnT Single Backlog Workflow](https://wiki.aa.com/bin/view/Technology%20and%20Transformation%20(TnT)%20Technology%20Operating%20Model/TnT%20Single%20Backlog%20Workflow/)
- [TnT Operating Model](https://wiki.aa.com/bin/view/Main/Technology%20and%20Transformation/)
- [ghaction-github-labeler](https://github.com/crazy-max/ghaction-github-labeler)
- [github-project-automation-plus](https://github.com/alex-page/github-project-automation-plus)
- [action-github-workflow-sync](https://github.com/varunsridharan/action-github-workflow-sync)
