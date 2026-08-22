# Week 16 — Final AI Systems Capstone

**Priority:** P0 / final proof

## Project
AI Candidate Intelligence Platform:
`Next.js → FastAPI → queue → workers → PostgreSQL/Redis → RAG/reranking → LLM → monitoring → Docker → Kubernetes → AWS`

### Day 1
Build/review the baseline end-to-end flow.

### Day 2
Load-test and identify the first bottleneck.

### Day 3
Optimize one bottleneck and benchmark before/after.

### Day 4
Introduce a dependency/pod failure and prove recovery.

### Day 5
Measure AI quality, latency, throughput and cost.

### Day 6
Produce architecture decision records and a final cost/performance report.

### Day 7
Final interview-style architecture review.

**Final question:** Given 100k documents, 200 requests/sec and p95 <2s, what architecture do you choose, what breaks first, how do you measure it, and what changes at 10× traffic?

**KPI:** Trace one request end-to-end and defend the architecture, scaling strategy, reliability controls and cost assumptions.