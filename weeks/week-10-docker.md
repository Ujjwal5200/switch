# Week 10 — Docker

**Dates:** 3–9 Nov 2026  
**Priority:** **CORE**  
**Target:** 7–9 hours

## Objective
Package the whole local system reproducibly and understand why containers behave the way they do.

## Primary Hindi video — MPrashant
**Docker Course For Beginners 2025: Basic to Advance Tutorial [HINDI]**  
https://www.youtube.com/watch?v=OhnTMWmfTBE

The video is ~3 hours and has 500k+ views in the indexed result. **Do not watch it end-to-end.** Watch:
- 00:01:38–00:13:13 — Docker/container/architecture/VM comparison
- 00:14:17–00:17:38 — Dockerfile/registry
- 00:38:11–00:49:24 — Dockerfile + image build
- 00:49:24–01:02:25 — containers
- 01:38:21–02:01:47 — volumes/bind mounts
- 02:01:47–02:13:35 — APIs + DB
- 02:13:35–02:30:04 — multi-container/network
- 02:30:04–03:03:45 — Docker Compose/network/volume/ports

Then verify implementation against:
- Docker Get Started: https://docs.docker.com/get-started/
- Dockerfile reference: https://docs.docker.com/reference/dockerfile/
- Compose: https://docs.docker.com/compose/

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

## Build
Containerize NextSwitch:
- Next.js
- FastAPI
- PostgreSQL
- Redis

Create one `docker compose up` workflow.

## Failure lab
Break and diagnose:
- wrong network name
- missing environment variable
- unhealthy dependency
- port collision

## AI-engineering focus — HIGH
AI can generate Dockerfiles. You decide process boundaries, image size, build/runtime separation, secrets handling, health semantics and service networking.

## KPI / exit test
A clean machine can start the full stack using documented commands, and you can debug a failed container without blindly regenerating the Dockerfile.
