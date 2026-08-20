# Week 11 — CI/CD + Production Hygiene

**Dates:** 10–16 Nov 2026  
**Priority:** **CORE**  
**Target:** 6–8 hours

## Objective
Make changes repeatable, testable and deployable before Kubernetes.

## Learn
- GitHub Actions basics
- lint/typecheck
- unit/API tests
- build artifacts/images
- Docker image tagging
- secrets management
- deployment environments
- rollback concept

## Sources
- GitHub Actions docs: https://docs.github.com/en/actions
- GitHub Actions quickstart: https://docs.github.com/en/actions/get-started/quickstart
- FastAPI testing: https://fastapi.tiangolo.com/tutorial/testing/

If you want a Hindi video, search for a current GitHub Actions beginner tutorial and watch only workflow YAML, triggers, jobs, secrets and Docker build/push. Verify syntax against the official docs because Actions examples change.

## Build
Pipeline:
`push → test → typecheck/lint → build → Docker image`

Use a matrix only if you actually need multiple runtimes.

## Failure lab
Make the pipeline fail deliberately:
- failing test
- type error
- Docker build failure
- missing secret

Document how the failure is surfaced and fixed.

## AI-engineering focus — HIGH
The hard part is deciding:
- what must block deployment
- environment separation
- image/version strategy
- rollback point
- secret boundaries
- migration ordering

## KPI / exit test
A bad test/build blocks the pipeline; a successful commit creates a traceable image/artifact.
