---
name: Deployment
slug: deployment
description: Safe deployment practices for staging and production
---

# Deployment

This skill defines how all agents deploy services to infrastructure.

## Environments
- **local** — developer workstation
- **staging** — pre-production validation
- **production** — live customer-facing services

## Staging Deploys
- Any agent can deploy to staging
- Must pass CI (tests, lint, typecheck)
- Must be smoke-tested before promotion
- Staging data is synthetic — never use production data

## Production Deploys
- Require board approval (or automated approval after staging validation)
- Must have rollback plan documented
- Must be deployed during low-traffic window when possible
- Must update Paperclip ticket with deploy status

## Deployment Checklist
- [ ] All tests passing
- [ ] No uncommitted changes on deploy branch
- [ ] Database migrations reviewed (if applicable)
- [ ] Rollback command tested
- [ ] Monitoring dashboards checked pre-deploy
- [ ] Post-deploy smoke test completed
- [ ] Paperclip ticket updated with deploy notes

## Rollback
1. Immediately revert to last known good deployment
2. Notify team via Paperclip ticket
3. Investigate root cause before re-deploying
4. Document incident in `references/incidents/`

## Prohibited
- Deploying without a rollback plan
- Skipping staging for production
- Deploying with failing tests
- Manual server changes not captured in code
