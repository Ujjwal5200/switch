# Switch — Current Execution Track

**Last reviewed:** 22 Aug 2026

This file is the canonical day-to-day execution layer for the current phase of Switch.

## Important correction

The older `weeks/` files describe an earlier 16-week sequence that started with frontend. The current master plan was later rebalanced toward production AI engineering. Do **not** follow the old weekly sequence just because its dates are present in those files.

The current canonical schedule is in `docs/MASTER-CHECKLIST.md`.

## Current position

### 21–31 Aug — Distributed systems + scaling foundations

**Current objective:** learn to reason about workload, bottlenecks, concurrency, queues, failure and scaling before adding infrastructure.

### 22 Aug — Day 2

Focus:
- workload modeling
- concurrency vs parallelism
- synchronous vs asynchronous request paths
- latency decomposition
- identifying the first bottleneck

Build:
- a minimal FastAPI endpoint for the candidate/ranking workload
- one deliberately slow dependency or simulated AI call
- a small load test using k6

Measure:
- RPS
- concurrent requests
- p50/p95/p99 latency
- error rate
- CPU/memory
- dependency latency

Break it:
- increase concurrency
- add artificial downstream latency
- observe where latency and errors rise

End-of-day question:
> If the endpoint becomes slow, how do I prove whether the bottleneck is CPU, I/O, database, network, queueing or model/external-API latency?

### 23 Aug — Day 3

Focus:
- horizontal scaling
- stateless FastAPI services
- load balancing
- connection pooling

Build:
- run two API instances locally
- put a load balancer/reverse proxy in front
- compare one vs two instances

Measure:
- throughput
- p95 latency
- CPU per instance
- DB connection usage

End question:
> What must be stateless before horizontal scaling works correctly?

### 24 Aug — Day 4

Focus:
- queues and workers
- producer/consumer model
- queue depth
- worker utilization
- backpressure

Build:
- API → queue → worker → result store
- make the worker intentionally slower than the producer

Measure:
- queue depth
- job wait time
- worker throughput
- API latency

End question:
> What happens when jobs arrive faster than workers can process them?

### 25 Aug — Day 5

Focus:
- retries
- exponential backoff
- timeouts
- idempotency

Build:
- intentionally failing downstream call
- retry with bounded backoff
- idempotency key for job submission

Break it:
- send the same job twice
- fail after the downstream side effect

End question:
> Can my retry create duplicate work or duplicate side effects?

### 26 Aug — Day 6

Focus:
- failure isolation
- graceful degradation
- circuit breakers
- dependency failure

Break:
- Redis unavailable
- database slow
- model timeout
- worker crash

Document:
`failure → detection → user impact → mitigation → recovery → remaining risk`

### 27 Aug — Day 7

Focus:
- scaling architecture review
- baseline vs optimized architecture

Deliver:
- architecture diagram
- baseline load-test report
- bottleneck report
- failure matrix
- one ADR explaining a major architecture decision

End question:
> What did measurement prove that intuition got wrong?

### 28–31 Aug — Consolidation

Do not start a new technology merely to stay busy.

Use these days to:
- rerun failed experiments
- improve weak measurements
- clean the implementation
- document trade-offs
- prepare the 10 → 100 → 1,000 → defined 10,000-user workload model

## Progress rule

A topic is **not complete** because a video was watched or notes were written.

Mark a concept complete only when you can:

1. explain the mechanism without notes;
2. implement a small version;
3. deliberately break it;
4. measure the behavior;
5. explain the trade-off;
6. connect it to the flagship AI Candidate Intelligence Platform.

## Evidence ledger

Record actual evidence here as the project develops:

| Date | Topic | Built | Broken | Measured | Evidence |
|---|---|---|---|---|---|
| 21 Aug | Distributed systems/scaling foundations | — | — | — | Not yet verified from repository |
| 22 Aug | Workload + concurrency | — | — | — | Not yet verified from repository |

Do not mark rows complete without evidence.

## What I am deliberately not optimizing for

- collecting frameworks
- finishing long video playlists
- certificates
- toy RAG demos
- unsupported claims such as “handles 10k users”
- Kubernetes before a measured bottleneck exists

The target is evidence-backed engineering judgment.
