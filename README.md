# Paperclip Company Template

A reusable template for defining autonomous AI companies in [Paperclip](https://paperclip.ing/).

## Quick Start

```bash
# 1. Copy this template to a new repo
git clone https://github.com/VulcanNeuralDev/vn-paperclip-company-template.git company-mycompany
cd company-mycompany

# 2. Find and replace all template values
#    - acme-ai → your-company-slug
#    - Acme AI Inc. → Your Company Name
#    - ACM → your issue prefix

# 3. Customize agents, projects, and skills (see below)

# 4. Import into Paperclip
paperclipai company import . --newCompanyName "My Company"
```

## What This Contains

| Directory | Purpose |
|---|---|
| `COMPANY.md` | Company definition, goals, secrets manifest, governance settings |
| `agents/` | Agent definitions — one per role (dev, ops, architect, etc.) |
| `teams/` | Team groupings with managers and members |
| `projects/` | Projects with tasks, owners, and schedules |
| `skills/` | Reusable skill packages that agents can inherit |
| `assets/` | Logos, images, brand assets |
| `references/` | External docs, style guides, API references |

## Agent Types Included

### hermes-dev
A Hermes-based software development agent. Runs locally via the `hermes_local` adapter. Handles feature implementation, bug fixes, and code review.

### hermes-ops
A Hermes-based infrastructure/DevOps agent. Manages deployments, monitors services, and maintains infrastructure as code.

### claude-architect
A Claude Code-based system architecture agent. Designs systems, reviews technical decisions, and maintains the architecture decision record.

## Customizing Agents

Each agent is defined in `agents/<slug>/AGENTS.md`:

```yaml
---
name: My Agent
title: Senior Developer
reportsTo: ceo
skills:
  - git-workflow
  - deployment
---

# Instructions
Write the agent's personality, working style, and constraints here.
```

Key fields:
- `reportsTo` — slug of the agent this one reports to (or `null` for CEO)
- `skills` — list of skill shortnames from `skills/<shortname>/`
- Body text — injected as system prompt instructions at runtime

## Customizing Projects

Each project is defined in `projects/<slug>/PROJECT.md`:

```yaml
---
name: Website Redesign
owner: hermes-dev
goal: Modernize the company website for launch
---

# Project Overview
Describe what this project delivers and its success criteria.
```

## Customizing Skills

Each skill is defined in `skills/<slug>/SKILL.md`:

```yaml
---
name: Git Workflow
slug: git-workflow
description: Conventional commits, branch naming, and PR etiquette
---

# Git Workflow
Detailed instructions that any agent using this skill will receive.
```

## Importing into Paperclip

### From local path
```bash
paperclipai company import ./company-mycompany --newCompanyName "My Company"
```

### From GitHub
```bash
paperclipai company import VulcanNeuralDev/company-mycompany --newCompanyName "My Company"
```

### Preview before import
```bash
paperclipai company import ./company-mycompany --dryRun
```

## Exporting from Paperclip

If you build a company in Paperclip and want to version-control it:

```bash
paperclipai company export <companyId> --out ./company-export
```

This generates a markdown package just like this template.

## License

MIT — same as Paperclip itself.
