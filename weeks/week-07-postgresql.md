# Week 7 — Docker for Production AI Services

**Dates:** 2–8 Oct 2026  
**Priority:** P0  
**Time:** 8–10 hours

## Learn
- image vs container
- Dockerfile
- multi-stage builds
- networks/volumes
- environment/secrets handling
- health checks
- Compose
- container resource limits
- image size/security basics

## Source
Docker getting started: https://docs.docker.com/get-started/

Hindi optional: use a recent Hindi Docker course only for first-pass terminology; then use Docker docs for implementation.

## Build
Containerize NextSwitch API + worker + PostgreSQL + Redis. Use Compose for local orchestration.

## Failure lab
Kill/restart a worker and database. Verify health checks and recovery behavior.

## KPI
One command starts the local production-shaped stack and you can explain each container boundary.

## AI-engineering focus
High: container boundaries and resource limits matter more than Docker syntax.