# Week 10 — Docker

**Goal:** Package the complete local system reproducibly.

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

## Source
- Docker Get Started: https://docs.docker.com/get-started/
- Docker Compose docs: https://docs.docker.com/compose/

## Build
Containerize:
- Next.js
- FastAPI
- PostgreSQL
- Redis

Create a single `docker compose up` workflow for development.

## KPI / exit test
A clean machine can start the full stack with documented commands, and services can reach each other using Compose networking rather than localhost hacks.

**Time:** 7–9 hours.