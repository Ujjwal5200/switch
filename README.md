# Switch — Production AI Engineering Roadmap

**Goal:** By 31 Dec 2026, become a strong early-career AI Product/Systems Engineer: able to design, build, deploy, observe, scale and cost-optimize AI systems. Frontend is a supporting skill, not the specialization.

## Current execution

- **Canonical daily track:** [EXECUTION TRACK](docs/EXECUTION-TRACK.md)
- **Master plan:** [MASTER CHECKLIST](docs/MASTER-CHECKLIST.md)
- **Core priorities:** [CORE PRIORITIES](docs/CORE-PRIORITIES.md)
- **AI systems interview mastery:** [INTERVIEW MASTERY](docs/INTERVIEW-MASTERY.md)
- **Scaling lab:** [SCALING LAB](docs/SCALING-LAB.md)
- **Priority project:** [AI Candidate Intelligence Platform](projects/PRIORITY-PROJECT.md)
- **Resources:** [RESOURCES](RESOURCES.md)

> **Important:** the `weeks/` directory contains the earlier 16-week sequence. The roadmap was later rebalanced toward production AI engineering. Follow `MASTER-CHECKLIST.md` and `EXECUTION-TRACK.md` as the current source of truth.

## Priority

### P0 — deep
1. AI/LLM engineering: RAG, evaluation, inference, agents/tools, model selection.
2. Backend: Python/FastAPI, async, API contracts, retries, timeouts, idempotency, testing.
3. Distributed systems: queues, workers, caching, rate limits, backpressure, consistency, failure isolation.
4. PostgreSQL: schema, indexes, EXPLAIN, transactions, pooling, query performance.
5. Kubernetes for AI: workloads, resources, HPA, GPU scheduling concepts, model serving, failure recovery.
6. AWS: IAM, VPC, S3, RDS, ECR, ALB, EKS/ECS, CloudWatch, cost.
7. Performance/cost/observability.
8. System design + interview reasoning.

### P1 — competent
Redis, CI/CD, TypeScript, React, Next.js, Tailwind, shadcn/ui.

### P2 — defer
Advanced frontend internals/CSS/animation, every AWS service, every Kubernetes add-on, framework memorization.

## Engineering rule

Learn → build → break → measure → explain → document.

Use AI heavily for implementation. Own architecture, security, reliability, scaling, evaluation and cost decisions.

## Weekly roadmap

See [MASTER-CHECKLIST](docs/MASTER-CHECKLIST.md) for the current calendar and exit gates.

The current flagship project is the **AI Candidate Intelligence Platform**: resume + JD → filtering → retrieval → reranking → structured LLM scoring → persistence → API → UI, progressively hardened with async processing, caching, Docker, Kubernetes, AWS, observability, scaling and inference work.
