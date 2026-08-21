# Switch — Master Execution Checklist

**Open this file first.** It is the canonical plan. The old frontend-heavy weekly sequence is no longer the priority plan.

## Priority model

### P0 — deep and non-negotiable
AI/LLM engineering, distributed systems, FastAPI/backend, PostgreSQL, queues/workers, Docker, Kubernetes for AI, AWS, scaling, observability/evaluation, inference, reliability and cost engineering.

### P1 — fast-track competence
TypeScript, React, Next.js, Tailwind, shadcn/ui, Redis, CI/CD.

### P2 — defer unless required
Advanced frontend internals, animation/CSS specialization, every cloud service, every Kubernetes add-on, framework collecting.

## Daily rule
1. Learn the listed concept.
2. Build one small implementation.
3. Apply it to the AI Candidate Intelligence Platform or a scale lab.
4. Break/overload one part.
5. Measure the result.
6. Write the architecture decision and trade-off.
7. Answer the end-of-day question.

If you cannot explain the day's concept or answer its question, carry it forward. Do not advance just because the date changed.

## Calendar and weekly gates

| Period | Primary work | Proof before moving on |
|---|---|---|
| 21–31 Aug | Distributed systems + scaling foundations | Explain and diagram 10→1k→10k workload architecture |
| 1–7 Sep | Queues, workers, retries, idempotency, backpressure | Working async document-processing flow |
| 8–14 Sep | PostgreSQL performance | EXPLAIN + measured index/query optimization |
| 15–21 Sep | Redis + caching/rate limiting | Measured cache benefit + failure behavior |
| 22–30 Sep | Docker + production containers | Full local AI stack runs reproducibly |
| 1–7 Oct | CI/CD + testing | Commit→test→build→deploy pipeline |
| 8–14 Oct | Kubernetes core for AI APIs | FastAPI AI service deployed to cluster |
| 15–21 Oct | Kubernetes scaling/failure | Load test + HPA + pod failure report |
| 22–31 Oct | AWS architecture/deployment | Secure cloud architecture + deployed service |
| 1–7 Nov | RAG fundamentals + evaluation | 10-document baseline with evaluation set |
| 8–14 Nov | RAG scaling | 1k→10k document benchmark |
| 15–21 Nov | RAG production architecture | 100k-scale design: partitioning/hybrid/rerank/tenant isolation |
| 22–30 Nov | Monitoring + observability | System + AI quality dashboard |
| 1–7 Dec | LLM inference/vLLM | Benchmark latency/throughput/memory |
| 8–14 Dec | AI cost engineering | Cost/request report + optimization experiment |
| 15–21 Dec | AI reliability | Failure matrix + retries/fallbacks/idempotency/load shedding |
| 22–31 Dec | Final capstone + interview mastery | End-to-end architecture, load test, cost report and design review |

## Normal weekday — 2 hours

- **75 min P0 core**
- **30 min implementation/experiment**
- **15 min AI/LLM continuity**
- **10 min engineering log**

If work is heavy, drop P1 frontend first. Do not drop the core experiment repeatedly.

## Saturday — 4 hours
Deep implementation + load/failure experiment.

## Sunday — 2 hours
Review metrics, document decisions, revise weak concepts.

## Main projects

### 1. AI Candidate Intelligence Platform
FastAPI + PostgreSQL + Redis + queue/workers + RAG/reranking + LLM + Docker + Kubernetes + AWS + monitoring.

### 2. RAG Scale Lab
10 → 1,000 → 10,000 → 100,000+ documents where practical.
Measure ingestion throughput, retrieval latency, recall@k, precision@k, reranking latency, answer quality and cost/query.

### 3. AI API Scale Lab
1 instance → multiple replicas → queue/workers → Kubernetes/HPA → AWS.
Measure RPS, concurrency, p50/p95/p99, errors, CPU/memory, DB latency, queue depth, model latency and cost/request.

## Design review checklist

Before adding infrastructure, answer:

1. What workload are we designing for?
2. What SLO/latency target matters?
3. What is the current bottleneck?
4. How did we measure it?
5. What is synchronous and what is asynchronous?
6. Where does state live?
7. Is the API stateless?
8. What can be cached?
9. How are retries bounded?
10. How is duplicate work prevented?
11. What happens when a dependency fails?
12. What scales first?
13. What metric triggers scaling?
14. What does the change cost?
15. How do we roll it back?

## Final December self-test

Given: **100,000 documents, 200 requests/sec, p95 < 2 seconds.**

You should be able to reason through ingestion, indexing, retrieval, reranking, caching, queues, API replicas, Kubernetes scaling, database limits, model serving, monitoring, quality evaluation, failure handling and cost — and explain why each decision exists.
