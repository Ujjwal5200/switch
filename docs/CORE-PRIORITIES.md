# Core Priorities — What Actually Matters for the Switch

## The goal

The goal is **not** to become a frontend developer who also knows AI.

The target profile is:

> **AI Product Engineer:** able to take an AI requirement from architecture → data/API design → AI workflow → reliability → deployment → observability → scaling → cost control, while being capable of owning enough frontend to ship the product.

Frontend is a supporting capability. AI systems + backend + infrastructure + system design are the specialization.

---

## Priority order

### P0 — Own deeply

1. **Python + FastAPI**
   - async/concurrency basics
   - API contracts
   - authentication/authorization
   - validation
   - background jobs
   - retries/timeouts
   - idempotency
   - pagination
   - testing
   - observability

2. **AI/LLM engineering**
   - RAG architecture
   - chunking/retrieval/reranking
   - structured outputs
   - tool calling/agents
   - evaluation
   - guardrails
   - model selection
   - latency/quality/cost trade-offs
   - prompt/context management
   - inference serving

3. **System design + orchestration**
   - service boundaries
   - synchronous vs asynchronous flows
   - queues
   - retries/backoff
   - idempotency
   - caching
   - rate limiting
   - failure isolation
   - circuit breakers
   - database ownership
   - consistency trade-offs
   - load shedding

4. **PostgreSQL**
   - schema design
   - indexes
   - query plans/EXPLAIN
   - transactions/isolation
   - connection pooling
   - migrations
   - pagination
   - avoiding N+1

5. **Docker + Kubernetes**
   - deployment model
   - health/readiness
   - resource requests/limits
   - autoscaling
   - rolling deployment
   - service discovery
   - ingress
   - failure recovery
   - debugging

6. **AWS**
   - IAM
   - VPC/networking
   - S3
   - RDS
   - ECR
   - ALB
   - ECS/EKS decisions
   - CloudWatch
   - cost controls

7. **Performance + cost engineering**
   - latency budget
   - throughput
   - concurrency
   - CPU/memory/GPU bottlenecks
   - DB bottlenecks
   - token/model cost
   - caching
   - batching
   - horizontal scaling

### P1 — Become competent

- Redis
- CI/CD
- GitHub Actions
- TypeScript
- React
- Next.js
- Tailwind
- shadcn/ui
- basic frontend auth/state/error handling

### P2 — Do not over-invest yet

- advanced CSS
- frontend animation
- deep browser internals
- advanced React rendering internals
- learning every AWS service
- learning every Kubernetes add-on
- memorizing framework APIs

---

## What employers should be able to trust you with

By the end of Switch, you should be able to take this requirement:

> "Build an AI API that receives a job description and resumes, ranks candidates, returns results to a web UI, and survives increasing traffic."

…and independently decide:

- API contract
- synchronous vs asynchronous architecture
- database schema
- retrieval/ranking flow
- model choice
- queue/background-job strategy
- caching strategy
- retry/idempotency strategy
- rate limiting
- container boundaries
- Kubernetes deployment
- autoscaling signals
- AWS architecture
- observability
- security boundaries
- failure behavior
- cost model

AI can help implement the pieces. **You own the decisions.**

---

## The scaling concept you must understand

Do not say "10,000 users" as if that is a technical capacity number.

You must translate users into workload:

`users → active users → requests/user → requests/sec → concurrency → CPU/memory/GPU work → database load → queue depth`

For each load level, measure:

- requests/sec
- p50/p95/p99 latency
- error rate
- CPU
- memory
- DB connections
- DB query latency
- cache hit rate
- queue depth
- worker utilization
- model inference latency
- tokens/sec
- GPU utilization when applicable
- cost/request

**Never claim "supports 10k users" without defining the traffic model and measuring it.**

---

## Engineering judgment checklist

Before adding infrastructure, ask:

1. What bottleneck am I fixing?
2. How did I measure it?
3. Is the bottleneck CPU, memory, I/O, database, network, model inference or external API latency?
4. Can code/query/caching solve it first?
5. What does the change cost?
6. What new failure mode does it introduce?
7. What happens when the dependency is unavailable?
8. How will I observe it?
9. How will I roll it back?
10. What load test proves the improvement?

This checklist is more important than memorizing another framework.
