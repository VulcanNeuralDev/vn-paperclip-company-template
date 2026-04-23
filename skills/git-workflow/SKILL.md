---
name: Git Workflow
slug: git-workflow
description: Conventional commits, branch naming, and PR etiquette for the engineering team
---

# Git Workflow

This skill defines how all engineering agents interact with Git and GitHub.

## Branch Naming
- `feature/<ticket-id>-short-description`
- `bugfix/<ticket-id>-short-description`
- `hotfix/<ticket-id>-short-description`
- `docs/<ticket-id>-short-description`

## Commit Conventions (Conventional Commits)
```
<type>(<scope>): <subject>

<body>

<footer>
```

Types:
- `feat` — new feature
- `fix` — bug fix
- `docs` — documentation only
- `style` — formatting, no logic change
- `refactor` — code change that neither fixes nor adds
- `test` — adding or correcting tests
- `chore` — build process, dependencies, etc.

## Pull Request Process
1. Branch from `main`
2. Write code and tests
3. Open PR with descriptive title and context
4. Link related Paperclip ticket in PR description
5. Request review from relevant agent (or board for architectural changes)
6. Merge only after approval and CI pass
7. Delete branch after merge

## Prohibited
- Force push to `main`
- Committing `.env` files or secrets
- Merge commits without squash (keep history linear)
- Direct commits to `main` (all changes via PR)
