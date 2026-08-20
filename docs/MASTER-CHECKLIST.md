# Switch — Master Execution Checklist

**This is the file to open first during off-hours.**

Do not browse the entire repository every day. Follow the current week, complete its exit criterion, then move forward.

## Calendar

| Dates | Main target | Secondary target | Exit proof |
|---|---|---|---|
| 20 Aug–7 Sep | JS/TypeScript + React literacy | AI/LLM continuity | Read/modify TSX + API UI |
| 8–14 Sep | Next.js foundations | PostgreSQL basics | Next.js app + API call |
| 15–21 Sep | Next.js app patterns | PostgreSQL schema/queries | CRUD flow |
| 22–30 Sep | Frontend → FastAPI → PostgreSQL | RAG continuity | Real data in UI |
| 1–7 Oct | PostgreSQL performance | Redis | Measured query/index change |
| 8–14 Oct | Redis + async jobs | AI ingestion | Queue-backed job |
| 15–21 Oct | Docker | Testing | Full local stack |
| 22–31 Oct | Docker + CI/CD | System design | One-command local startup + CI |
| 1–7 Nov | Kubernetes core | Load testing | API deployed to cluster |
| 8–14 Nov | Kubernetes scaling | Observability | HPA/load test |
| 15–21 Nov | AWS core | Security/cost | Cloud architecture |
| 22–30 Nov | AWS + Kubernetes | Failure testing | Deployed service + recovery drill |
| 1–7 Dec | RAG scaling | Evaluation | RAG Scale Lab v1 |
| 8–14 Dec | AI API scaling | vLLM | API Scale Lab |
| 15–21 Dec | Monitoring | Cost optimization | AI monitoring dashboard |
| 22–31 Dec | Integration + interview mastery | System design | Final NextSwitch + design review |

---

# DAILY EXECUTION

## On a normal workday — 2 hours

### 60 min — Core
Current weekly core topic.

### 30 min — Build
Implement the week's feature in NextSwitch or a lab.

### 20 min — AI/LLM
Continue your existing LLM work.

### 10 min — Engineering log
Record:
- what changed
- what broke
- what metric changed
- what you learned
- one architecture decision

## Saturday — 4 hours
Deep build/load/failure experiment.

## Sunday — 2 hours
Review + documentation + next-week plan.

---

# PRIORITY SCALE

### P0 — never skip
- AI/LLM engineering
- FastAPI/backend
- PostgreSQL
- system design/orchestration
- Docker/Kubernetes
- AWS
- scaling/performance
- monitoring
- cost engineering

### P1 — complete by December
- TypeScript
- React
- Next.js
- Tailwind
- shadcn/ui
- Redis
- CI/CD

### P2 — only when required
- advanced frontend internals
- extra frameworks
- extra cloud services
- extra agent frameworks

---

# MASTER PROJECTS

## 1. NextSwitch — product build
End-to-end AI product demonstrating frontend + backend + AI + infrastructure.

## 2. RAG Scale Lab
10 → 1,000 → 10,000 → 100,000+ documents where practical.

Track:
- ingestion throughput
- index size
- retrieval latency
- recall@k
- precision@k
- reranker latency
- answer quality
- cost/query

See `docs/INTERVIEW-MASTERY.md`.

## 3. AI API Scale Lab
1 instance → multiple instances → queue/workers → Kubernetes → HPA → AWS.

Track:
- RPS
- concurrency
- p50/p95/p99
- error rate
- CPU/memory
- DB latency
- queue depth
- model latency
- cost/request

See `docs/SCALING-LAB.md`.

## 4. Production Monitoring Lab
Build a dashboard combining system and AI-quality metrics.

---

# EVERY DESIGN REVIEW

Before declaring a system "scalable", answer:

1. What is the workload?
2. What is the SLO?
3. What is the bottleneck?
4. What happens at 10× load?
5. What happens when the dependency fails?
6. Is the service stateless?
7. Where does state live?
8. What can be cached?
9. What can be asynchronous?
10. What must remain synchronous?
11. How is duplicate work prevented?
12. How do we scale the bottleneck?
13. How do we observe it?
14. How much does it cost?
15. How do we roll it back?

---

# MONTH-END GATE

Do not move to the next month merely because the calendar changed.

Move when you can **demonstrate** the milestone.

### September gate
Next.js frontend calls FastAPI and persists/reads PostgreSQL data.

### October gate
NextSwitch runs as a containerized multi-service stack and has basic CI.

### November gate
The service is deployed to Kubernetes/AWS and you have performed a scaling/failure experiment.

### December gate
You can explain and demonstrate RAG scaling, AI API scaling, monitoring, quality evaluation, inference/cost trade-offs and the complete NextSwitch architecture.

---

# FINAL DECEMBER SELF-TEST

Given:

> "A RAG API currently handles 1,000 documents and 5 requests/sec. We need 100,000 documents and 200 requests/sec with p95 < 2 seconds."

You should be able to answer:

- What do you measure first?
- Where will ingestion happen?
- How do you index and partition data?
- How do you prevent retrieval quality from degrading?
- Where does reranking happen?
- What gets cached?
- What becomes asynchronous?
- How do API replicas scale?
- What does Kubernetes scale on?
- What is the database bottleneck?
- What happens when the LLM times out?
- How do you monitor quality?
- How do you measure cost?
- What would you simplify if the traffic never arrives?

If you can reason through those questions with measurements and trade-offs, you are progressing toward the target profile.
