# Week 8 — CI/CD + Deployment Discipline

**Dates:** 9–15 Oct 2026  
**Priority:** P0  
**Time:** 8–10 hours

## Learn
- CI vs CD
- test/build/deploy stages
- image tagging
- secrets
- environment promotion
- rollback
- health gates
- GitHub Actions

## Sources
- GitHub Actions: https://docs.github.com/en/actions
- Docker CI/CD guide: https://docs.docker.com/build/ci/github-actions/

## Build
Pipeline: push → tests → build image → scan/basic validation → deploy to a test environment → health check.

## KPI
A bad build cannot reach deployment; a failed health check triggers a rollback/stop condition.

## AI-engineering focus
High: deployment safety and rollback strategy are your decisions.