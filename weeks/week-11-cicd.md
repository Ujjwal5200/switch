# Week 11 — CI/CD + Production Hygiene

**Goal:** Make changes repeatable and testable before Kubernetes.

## Learn
- GitHub Actions basics
- linting/type checking
- unit/API tests
- build artifacts/images
- Docker image tagging
- secrets management concepts
- deployment environments
- rollback concept

## Source
- GitHub Actions docs: https://docs.github.com/en/actions
- FastAPI testing: https://fastapi.tiangolo.com/tutorial/testing/

## Build
Pipeline:
`push → test → typecheck/lint → build → Docker image`

Do not add deployment complexity until the pipeline is reliable.

## KPI / exit test
A bad test or failed build blocks the pipeline; a successful commit produces a versioned image/artifact.

**Time:** 6–8 hours.