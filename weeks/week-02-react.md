# Week 2 — Queues, Workers, Retries + Backpressure

**Priority:** P0

## Goal
Turn the Day-1 API into a reliable asynchronous AI workload system.

### Day 1 — Queue fundamentals
Learn producer/consumer, queue depth, job lifecycle.
Source: https://redis.io/docs/latest/develop/data-types/streams/
Build FastAPI → Redis queue → worker.
Question: What happens when producers outrun consumers?

### Day 2 — Job lifecycle
Build `queued → processing → completed/failed` state tracking.
Question: How does a client know when a long AI job finishes?

### Day 3 — Retries
Learn bounded retries, exponential backoff, transient vs permanent failure.
Build retry policy and failure simulation.
Question: When does retrying make an outage worse?

### Day 4 — Idempotency
Build idempotency keys for document/AI jobs.
Question: What happens if the same request is delivered twice?

### Day 5 — Dead-letter handling
Build failed-job/DLQ behavior and replay.
Question: Which failures should be retried automatically?

### Day 6 — Backpressure + rate limits
Overload workers, measure queue growth, add rate limiting/load shedding.
Question: How do you keep overload from taking down the whole system?

### Day 7 — Production review
Document throughput, queue depth, worker capacity and failure behavior.
KPI: Explain API → queue → worker architecture and its trade-offs.