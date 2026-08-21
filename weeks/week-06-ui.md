# Week 6 — Async APIs + Queues

**Dates:** 25 Sep–1 Oct 2026  
**Priority:** P0  
**Time:** 10–12 hours

## Learn
- FastAPI async I/O
- background workers
- queue semantics
- retries/backoff
- dead-letter queues
- idempotency keys
- job status APIs
- graceful shutdown
- timeouts and cancellation

## Sources
- FastAPI async docs: https://fastapi.tiangolo.com/async/
- Celery docs: https://docs.celeryq.dev/
- AWS SQS docs: https://docs.aws.amazon.com/sqs/

## Build
Resume ingestion API: upload → object storage → queue → worker → parse/embed → DB → status endpoint.

## KPI
Explain when a task belongs in the request path and when it belongs in a queue. Demonstrate retry without duplicate processing.

## AI-engineering focus
EXTREME: reliable orchestration is a core AI product skill.