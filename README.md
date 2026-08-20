# Switch — AI Product Engineering Roadmap

A focused Aug–Dec 2026 plan to become an **AI Product Engineer** who can take an AI feature from architecture → backend/API → AI pipeline → frontend → deployment → scaling → observability → cost control.

## 🚨 Start here — priority order

### P0 — Career-critical

1. **AI/LLM engineering:** RAG, retrieval/reranking, structured outputs, agents/tools, evaluation, guardrails, model selection, inference.
2. **Backend/API:** Python, FastAPI, async/concurrency, API contracts, auth, validation, jobs, retries, timeouts, idempotency, testing.
3. **System design/orchestration:** service boundaries, sync vs async, queues, caching, rate limits, failure isolation, consistency and reliability.
4. **PostgreSQL:** schema design, indexes, EXPLAIN, transactions, pooling, migrations, query performance.
5. **Docker + Kubernetes:** containers, probes, resources, deployments, services, HPA, rolling updates, debugging and failure recovery.
6. **AWS:** IAM, VPC, S3, RDS, ECR, ALB, ECS/EKS, CloudWatch and cost.
7. **Performance/cost:** latency, throughput, concurrency, bottlenecks, batching, caching, model cost, resource utilization.

### P1 — Important supporting skills

- Redis
- CI/CD
- TypeScript
- React
- Next.js
- Tailwind
- shadcn/ui

### P2 — Do not over-invest yet

Advanced CSS, animations, deep browser internals, learning every AWS service, learning every Kubernetes add-on, and memorizing framework APIs.

## 🔥 Priority project

**[AI Candidate Intelligence Platform](projects/PRIORITY-PROJECT.md)**

This is the flagship project. Do not stop at the MVP. Progressively turn it into a production-shaped AI system.

## 📈 Priority scaling exercise

**[0 → 10,000+ Scaling Lab](docs/SCALING-LAB.md)**

Start with a simple API. Measure it. Find the bottleneck. Then progressively introduce PostgreSQL optimization, Redis, async workers, Docker, Kubernetes, autoscaling and AWS.

Do **not** claim "1 million users" without defining the workload. Convert users into active users → requests/sec → concurrency → resource/model/database load.

## 🎯 What you must be able to demonstrate

By December, you should be able to take an AI requirement and independently produce:

`requirements → architecture → API contract → data model → AI workflow → async orchestration → reliability strategy → deployment → load test → bottleneck analysis → scaling plan → cost analysis`

AI can write much of the implementation. **You own the engineering decisions.**

## 📚 Core documents

- [Core priorities](docs/CORE-PRIORITIES.md)
- [Priority projects](projects/README.md)
- [Resource map](RESOURCES.md)

## 📅 Weekly roadmap

- [Week 1 — JavaScript + TypeScript](weeks/week-01-js-typescript.md)
- [Week 2 — React fundamentals](weeks/week-02-react.md)
- [Week 3 — React API integration](weeks/week-03-react-api.md)
- [Week 4 — Next.js foundations](weeks/week-04-nextjs.md)
- [Week 5 — Next.js application patterns](weeks/week-05-nextjs-app.md)
- [Week 6 — Tailwind + shadcn/ui](weeks/week-06-ui.md)
- [Week 7 — PostgreSQL foundations](weeks/week-07-postgresql.md)
- [Week 8 — PostgreSQL + FastAPI](weeks/week-08-postgres-fastapi.md)
- [Week 9 — Redis](weeks/week-09-redis.md)
- [Week 10 — Docker](weeks/week-10-docker.md)
- [Week 11 — CI/CD](weeks/week-11-cicd.md)
- [Week 12 — Kubernetes core](weeks/week-12-kubernetes.md)
- [Week 13 — Kubernetes production](weeks/week-13-kubernetes-production.md)
- [Week 14 — AWS foundations](weeks/week-14-aws.md)
- [Week 15 — AWS + Kubernetes](weeks/week-15-aws-kubernetes.md)
- [Week 16 — AI inference + vLLM](weeks/week-16-ai-inference.md)

## Rule for the whole roadmap

**Learn only enough theory to make a correct engineering decision. Then build, measure, break, debug and document.**

For frontend, use AI aggressively. For architecture, security, reliability, scaling and cost, do the reasoning yourself and use AI as a reviewer—not as the decision maker.
