---
name: Infrastructure
owner: hermes-ops
goal: Maintain reliable, cost-effective infrastructure for all company services
description: |
  Servers, databases, networks, and deployment pipelines. Everything the
  company runs on, managed as code.
---

# Infrastructure Project

## Scope
- VPS provisioning and hardening (Ubuntu)
- Docker container orchestration
- PostgreSQL database management
- CI/CD pipeline (GitHub Actions)
- Monitoring and alerting
- Backup and disaster recovery

## Tech Stack
- OS: Ubuntu 24.04 LTS
- Containers: Docker + Docker Compose
- Database: PostgreSQL 16
- Reverse proxy: Caddy or Nginx
- Monitoring: Uptime Kuma + log aggregation

## Milestones
1. Baseline server hardening
2. Containerized service deployment
3. Automated backup system
4. Monitoring and alerting
5. Disaster recovery runbook

## Success Criteria
- 99.9% uptime target
- < 5 min incident response time
- Zero unplanned data loss
- All changes captured in version control
