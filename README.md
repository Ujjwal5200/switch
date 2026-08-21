# Switch — Production AI Engineering Roadmap

**Goal:** By 31 Dec 2026, become a strong early-career AI Product/Systems Engineer: able to design, build, deploy, observe, scale and cost-optimize AI systems. Frontend is a supporting skill, not the specialization.

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

## Start here
- [MASTER CHECKLIST](docs/MASTER-CHECKLIST.md)
- [Core priorities](docs/CORE-PRIORITIES.md)
- [AI systems interview mastery](docs/INTERVIEW-MASTERY.md)
- [Scaling lab](docs/SCALING-LAB.md)
- [Priority project](projects/PRIORITY-PROJECT.md)
- [Resources](RESOURCES.md)

## Weekly roadmap

1. [Week 1 — Frontend literacy fast-track](weeks/week-01-js-typescript.md)
2. [Week 2 — React/Next.js fast-track](weeks/week-02-react.md)
3. [Week 3 — PostgreSQL performance](weeks/week-03-react-api.md)
4. [Week 4 — Redis + caching](weeks/week-04-nextjs.md)
5. [Week 5 — Distributed systems fundamentals](weeks/week-05-nextjs-app.md)
6. [Week 6 — Async APIs + queues](weeks/week-06-ui.md)
7. [Week 7 — Docker + production containers](weeks/week-07-postgresql.md)
8. [Week 8 — CI/CD + deployment](weeks/week-08-postgres-fastapi.md)
9. [Week 9 — Kubernetes core for AI APIs](weeks/week-09-redis.md)
10. [Week 10 — Kubernetes scaling/failure labs](weeks/week-10-docker.md)
11. [Week 11 — AWS architecture](weeks/week-11-cicd.md)
12. [Week 12 — AWS + Kubernetes deployment](weeks/week-12-kubernetes.md)
13. [Week 13 — RAG scaling](weeks/week-13-kubernetes-production.md)
14. [Week 14 — AI evaluation + monitoring](weeks/week-14-aws.md)
15. [Week 15 — LLM inference/vLLM](weeks/week-15-aws-kubernetes.md)
16. [Week 16 — End-to-end scale/cost capstone](weeks/week-16-ai-inference.md)

**Rule:** Learn enough theory to make a correct decision. Then build → measure → break → debug → document. Use AI heavily for implementation; own architecture, security, reliability, scaling and cost decisions.