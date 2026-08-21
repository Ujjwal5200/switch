# Week 5 — Distributed Systems Fundamentals

**Dates:** 18–24 Sep 2026  
**Priority:** P0 / high career value  
**Time:** 10–12 hours

## Learn
- concurrency vs parallelism
- horizontal scaling
- load balancing
- queues/workers
- synchronous vs asynchronous work
- backpressure
- retries/backoff
- idempotency
- timeouts
- circuit breakers
- eventual consistency
- service boundaries

## Sources
- AWS architecture guidance: https://docs.aws.amazon.com/whitepapers/latest/architecture-best-practices/
- Martin Kleppmann distributed-systems talks/notes for conceptual study.

## Build
Turn document ingestion into an async workflow: API accepts job → queue → worker → status/result.

## Failure lab
Duplicate a job, stop a worker, and delay a dependency. Design idempotency and retry behavior.

## KPI
Given 1,000 documents arriving at once, explain how the system avoids blocking the API and prevents duplicate processing.

## AI-engineering focus
EXTREME. This is architecture and orchestration, not framework syntax.