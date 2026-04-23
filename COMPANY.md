---
schema: agentcompanies/v1
kind: company
slug: acme-ai
name: Acme AI Inc.
description: An autonomous AI company that builds and operates software products.
version: 0.1.0
license: MIT
authors:
  - name: VulcanNeural
    email: founder@vulcanneural.net
tags:
  - software
  - saas
  - ai-native
goals:
  - Build the #1 AI-powered note-taking app to $1M MRR
  - Maintain 99.9% uptime across all services
  - Ship at least one major feature per month
requirements:
  secrets:
    - name: OPENROUTER_API_KEY
      description: LLM API key for agent inference
      required: true
    - name: GITHUB_TOKEN
      description: GitHub PAT for repo access and PR automation
      required: true
    - name: TELEGRAM_BOT_TOKEN
      description: Bot token for gateway messaging
      required: false
---

# Acme AI Inc.

Welcome to the company definition for Acme AI. This markdown package defines the org structure, agents, projects, and skills that Paperclip uses to run this autonomous company.

## How to Use This Template

1. **Fork this repo** and rename it to your company (e.g. `company-yoyo`)
2. **Update `COMPANY.md`** frontmatter with your company name, slug, and goals
3. **Customize agents** in `agents/*/AGENTS.md` with your own instructions and roles
4. **Define projects** in `projects/*/PROJECT.md`
5. **Add skills** in `skills/*/SKILL.md` for reusable agent capabilities
6. **Import into Paperclip** via `paperclipai company import <path-or-url>`

## Directory Layout

```
company-package/
├── COMPANY.md              # Company definition and secrets manifest
├── .paperclip.yaml         # Vendor extensions (optional)
├── agents/
│   ├── hermes-dev/         # Hermes agent — software development
│   ├── hermes-ops/         # Hermes agent — infrastructure & DevOps
│   └── claude-architect/   # Claude Code agent — system architecture
├── teams/
│   ├── eng/                # Engineering team
│   └── product/            # Product team
├── projects/
│   ├── website/            # Company website project
│   └── infrastructure/     # Infrastructure & DevOps project
├── skills/
│   ├── git-workflow/       # Git branching, PR, commit conventions
│   └── deployment/         # Deploy to production safely
├── assets/                 # Logos, images, brand assets
└── references/             # External documentation, style guides
```

## Governance

- **Board approval required for new agents:** Yes
- **Monthly budget:** $500 USD
- **Issue prefix:** ACM
