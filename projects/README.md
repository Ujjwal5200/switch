# Priority Projects

These projects are not equal. Build them in this order.

## P0 — AI Candidate Intelligence Platform

[Project brief](./PRIORITY-PROJECT.md)

This is the flagship project. It combines:

- AI workflow design
- FastAPI
- PostgreSQL
- Redis
- async orchestration
- Docker
- Kubernetes
- AWS
- observability
- scaling
- cost engineering
- Next.js UI

**Target:** finish the engineering progression, not merely the MVP.

## P0 — Scaling Lab

[Scaling Lab](../docs/SCALING-LAB.md)

Use the flagship project as the workload and deliberately take it from a simple local API to a measured high-concurrency deployment.

## P1 — AI Inference Lab

Build a small model-serving benchmark:

`client → FastAPI → inference server → model`

Compare:

- external API
- local CPU inference
- vLLM/GPU when available

Measure latency, throughput, memory/GPU use and cost.

## P1 — Reliability Lab

Take one API and deliberately introduce:

- timeouts
- duplicate requests
- dependency failures
- slow DB queries
- worker crashes

Implement retries, idempotency, circuit-breaking/fallback where justified, and observability.

## P2 — Frontend Lab

Build only enough React/Next.js UI to expose the flagship project's APIs professionally.

Use AI heavily for implementation.
