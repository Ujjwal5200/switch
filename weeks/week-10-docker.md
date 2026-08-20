# Week 10 — Docker

**Dates:** 3–9 Nov 2026  
**Priority:** **CORE**  
**Target:** 7–9 hours

## Objective
Package the whole local system reproducibly and understand why containers behave the way they do.

## Learn
- image vs container
- Dockerfile
- layers/build context
- ports
- volumes
- networks
- environment variables
- health checks
- multi-stage builds
- Docker Compose

## Video/source
For a Hindi first pass, use a current high-view Docker beginner course from an established Indian educator; watch only the sections covering the topics above. Do not watch an 8–10 hour course end-to-end.

Then use the authoritative sources:
- Docker Get Started: https://docs.docker.com/get-started/
- Dockerfile reference: https://docs.docker.com/reference/dockerfile/
- Compose: https://docs.docker.com/compose/

## Build
Containerize:
- Next.js
- FastAPI
- PostgreSQL
- Redis

Create one `docker compose up` workflow.

## Engineering lab
Break the setup intentionally:
- wrong network name
- missing environment variable
- unhealthy dependency
- port collision

Diagnose each using logs/network inspection rather than asking AI for the answer immediately.

## AI-engineering focus — HIGH
AI can generate Dockerfiles. You decide:
- process boundaries
- image size
- build/runtime separation
- secrets handling
- health semantics
- service networking
- local vs production configuration

## KPI / exit test
A clean machine can start the full stack using documented commands, and you can debug a failed container without blindly regenerating the Dockerfile.
