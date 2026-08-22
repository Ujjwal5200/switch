# Week 1 — Distributed Systems + AI API Scale Lab

**Priority:** P0. This replaces the old frontend-first Week 1.

## Goal
Build one FastAPI AI-style API from zero and learn how workload, concurrency and horizontal scaling change its behavior.

## Day 1 — Baseline
Learn: distributed-system model, network latency, partial failure, vertical vs horizontal scaling.
Source: https://www.youtube.com/watch?v=klUH2wqxzyw
Build: `POST /generate` with a mock 1–2s AI delay.
Test: k6 at 1/10/50/100 VUs. Record RPS, p50/p95/p99, errors, CPU/memory.
Question: What is the current bottleneck?

## Day 2 — Replicas
Learn: stateless services, load balancing, health checks.
Build: 2 FastAPI instances behind a local reverse proxy/load balancer.
Measure 1 vs 2 instances.
Question: Did throughput double? If not, why?

## Day 3 — Async/concurrency
Learn: concurrency vs parallelism, I/O-bound vs CPU-bound, async/await, workers.
Build `/generate-sync` and `/generate-async` and load-test both.
Question: Is the endpoint CPU-bound or I/O-bound? Prove it with measurements.

## Day 4 — Queue + workers
Learn: producer, consumer, queue, worker, queue depth.
Build: FastAPI → Redis queue → worker → mock AI.
Add `POST /jobs` and `GET /jobs/{id}`.
Question: Why should long AI work leave the HTTP request path?

## Day 5 — Reliability
Learn: timeout, retry, exponential backoff, idempotency.
Build job IDs, idempotency keys and bounded retries. Deliberately fail the AI call.
Question: Can a retry create duplicate work or side effects?

## Day 6 — Backpressure
Learn: rate limiting, queue saturation, load shedding, producer/consumer mismatch.
Overload workers deliberately and test rate limits/backpressure.
Question: What should happen when traffic arrives faster than workers can process it?

## Day 7 — Architecture review
Design 10 → 1,000 → 10,000-user versions of the system.
For every component document: problem → change → metric → trade-off → new bottleneck.

## KPI
You can explain and measure why a simple AI API needs replicas, queues, workers, retries and backpressure as workload increases. Do not move on because the calendar changed; carry weak topics forward.