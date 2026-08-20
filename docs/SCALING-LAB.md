# Scaling Lab — 0 → 10,000+ Concurrent Users

## Purpose

This is the **highest-priority practical lab** in Switch.

The objective is not to fake a "million-user" benchmark. The objective is to learn how an AI service breaks, how to identify the bottleneck, and how architecture changes remove that bottleneck.

## The system

Build a small AI service:

`Client → Next.js → FastAPI API → Redis → PostgreSQL`

AI workflow:

`FastAPI → retrieval → reranker/LLM → structured result → PostgreSQL`

Start with one FastAPI process and one database.

---

## Phase 0 — Baseline

### Build
- `/health`
- `/rank`
- `/jobs/{id}`
- PostgreSQL persistence
- one AI workflow
- structured JSON response

### Measure
Run a load test and record:

- RPS
- p50/p95/p99 latency
- error rate
- CPU
- memory
- DB connections
- DB latency
- AI inference latency
- cost/request

**Deliverable:** baseline report.

---

## Phase 1 — 1 user → 10 users

Understand the simplest system.

Test:
- sequential requests
- concurrent requests
- slow model response
- slow database query

Find your first bottleneck.

**Do not scale anything yet. Fix one measurable bottleneck.**

---

## Phase 2 — 100 users

Introduce:
- connection pooling
- indexes
- pagination
- request timeouts
- structured logging

Run the same benchmark.

Create a before/after table.

---

## Phase 3 — 1,000 users

Introduce:
- Redis caching
- rate limiting
- background jobs
- worker process
- retry/backoff
- idempotency key

Change the architecture where appropriate:

`request → queue → worker → AI inference → DB`

The API should not hold a user request open while doing work that can safely be asynchronous.

Measure queue depth and worker utilization.

---

## Phase 4 — Kubernetes

Containerize the API and worker.

Deploy to kind/minikube:

- Deployment
- Service
- ConfigMap
- Secret
- readiness probe
- liveness probe
- resource requests/limits
- HPA

Load test again.

### Experiments
1. 1 replica
2. 2 replicas
3. 4 replicas
4. CPU pressure
5. pod failure
6. rolling update
7. worker scaling

Record what actually changes.

---

## Phase 5 — 10,000 users / defined workload

**Important:** 10,000 users is not a valid benchmark by itself.

Define a workload, for example:

- 10,000 registered users
- 1,000 active users
- 100 requests/sec peak
- 10% AI requests
- 90% normal API requests

Then test.

Adjust the workload to match what your machine/cloud budget can realistically generate.

### Measure
- API RPS
- p50/p95/p99
- error rate
- pod count
- CPU/memory
- DB connections
- DB CPU
- Redis hit rate
- queue depth
- worker throughput
- model throughput
- external API latency
- cost

**Deliverable:** scaling report explaining the first bottleneck and every architectural change made to remove it.

---

## Phase 6 — AWS

Deploy the architecture to AWS.

Target:

`Internet → ALB → EKS/ECS → FastAPI → Redis/RDS/S3`

For AI inference, decide whether the model should be:

- external API
- CPU service
- GPU service
- dedicated inference server such as vLLM

The decision must be justified by latency, traffic, model size, quality and cost.

---

## Phase 7 — Failure engineering

Deliberately break the system:

- PostgreSQL unavailable
- Redis unavailable
- model API timeout
- worker crash
- pod killed
- bad deployment
- traffic spike
- slow query
- exhausted DB pool
- malformed AI output

For each failure document:

`failure → detection → impact → mitigation → recovery → remaining risk`

---

## Phase 8 — Optimization

You must produce at least **three measured improvements**.

Examples:

- DB index improves p95
- Redis reduces DB load
- async workers increase throughput
- batching improves inference throughput
- smaller model reduces cost
- quantization reduces memory
- HPA improves burst handling

Every improvement requires a benchmark before and after.

---

## Final deliverables

Create:

- `architecture.md`
- `load-test.md`
- `bottlenecks.md`
- `failure-matrix.md`
- `cost-analysis.md`
- `scaling-decisions.md`
- architecture diagrams
- benchmark results

The final interview explanation should be:

> "Here was my baseline. This was the bottleneck. I measured it. I changed X. It improved Y but introduced Z. Then I changed A. At the target workload, the bottleneck moved to B."

That is substantially stronger than saying "I know Kubernetes."
