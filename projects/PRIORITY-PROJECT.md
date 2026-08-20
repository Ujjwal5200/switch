# Priority Project — AI Candidate Intelligence Platform

## Why this project

This project is deliberately close to the kind of system you already understand, but it forces you to solve the harder engineering problems you need for a stronger AI Product Engineer profile.

Do **not** make this another RAG demo.

The goal is to build a small AI product and then progressively turn it into a reliable, observable and scalable service.

---

## Product

A company uploads:

- job description
- candidate resumes

The platform:

1. parses resumes
2. normalizes candidate data
3. filters hard constraints
4. retrieves relevant evidence
5. reranks candidates
6. asks an LLM for structured reasoning/score
7. persists the result
8. exposes APIs
9. displays rankings in Next.js
10. supports asynchronous processing for larger batches

---

## Architecture progression

### V0 — single service

`Next.js → FastAPI → PostgreSQL → LLM`

Build the smallest useful version.

### V1 — separate responsibilities

`API → job queue → worker → AI pipeline → PostgreSQL`

Separate request handling from long-running AI work.

### V2 — caching + rate limits

`API → Redis → PostgreSQL`

Add only when measurements justify it.

### V3 — production containerization

`Next.js | API | Worker | Redis | PostgreSQL`

Docker Compose locally.

### V4 — Kubernetes

Deploy:

- API
- workers
- frontend
- Redis
- PostgreSQL or managed DB

Add:

- probes
- resources
- HPA
- rolling deployment
- observability

### V5 — AWS

`Internet → ALB → Kubernetes/ECS → API/Workers → RDS/Redis/S3 → AI inference`

Choose EKS vs ECS based on the workload and explain why.

---

## Core engineering challenges

### 1. API design

Define contracts before implementation.

Examples:

- `POST /jobs`
- `POST /jobs/{id}/screen`
- `GET /jobs/{id}/results`
- `GET /candidates/{id}`
- `GET /health`
- `GET /metrics`

Define status codes, validation, pagination, authentication and error schema.

### 2. Async orchestration

Decide:

- what must be synchronous
- what can be queued
- retry policy
- timeout policy
- idempotency
- dead-letter handling
- job status model

### 3. AI pipeline

Measure each stage:

`parse → retrieve → rerank → LLM → validate → persist`

Record latency, failures and cost for every stage.

### 4. Data architecture

Design tables before coding.

Consider:

- candidates
- jobs
- resumes
- processing_jobs
- scores
- model_runs
- evaluation_runs

Decide what is source-of-truth data and what is derived/cache data.

### 5. Reliability

The system must behave predictably when:

- LLM times out
- Redis disappears
- DB connection is exhausted
- worker crashes
- duplicate request arrives
- malformed model output appears
- traffic suddenly increases

### 6. Scaling

Run the dedicated [Scaling Lab](../docs/SCALING-LAB.md).

Never jump directly to Kubernetes. First establish a baseline and identify the bottleneck.

### 7. Cost

For every AI architecture, calculate approximately:

`cost/request = model + embeddings + reranking + compute + database + cache + network`

Compare at least two model/infrastructure options.

### 8. Observability

Track:

- request latency
- errors
- throughput
- queue depth
- DB latency
- model latency
- token usage
- cost
- resource utilization

---

## Project stages

### Stage 1 — MVP

Target: working product.

Exit:
- upload JD/resumes
- process candidates
- return ranking
- show result in UI

### Stage 2 — Production API

Add:
- authentication
- validation
- pagination
- PostgreSQL indexes
- tests
- structured errors
- logging

### Stage 3 — Async AI processing

Add:
- queue
- worker
- retry/backoff
- idempotency
- job status

### Stage 4 — Performance

Benchmark.

Fix one bottleneck at a time.

### Stage 5 — Kubernetes

Deploy and scale.

### Stage 6 — AWS

Cloud deployment + IAM/networking/observability.

### Stage 7 — AI inference

Compare external API vs self-hosted inference/vLLM where appropriate.

### Stage 8 — Final engineering review

Produce:

- HLD
- LLD
- API specification
- data model
- architecture diagram
- load-test report
- bottleneck report
- failure matrix
- cost report
- ADRs (architecture decision records)

---

## What makes this project valuable

The frontend is not the achievement.

The achievement is being able to explain:

> Why is this service split this way?
>
> Why is this task asynchronous?
>
> Why PostgreSQL here and Redis there?
>
> Why this model?
>
> What happens when the model fails?
>
> What is the bottleneck at 100 RPS?
>
> What happens at 10× traffic?
>
> What does scaling cost?
>
> What breaks first?
>
> How do you know?

If you cannot answer those questions with measurements or explicit trade-offs, the project is not finished.
