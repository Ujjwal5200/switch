# Switch — Resource Map & Engineering Priorities

## How to use resources

**Frontend:** learn just enough, then let AI implement.  
**Backend/infrastructure/AI:** understand the mechanism, reproduce it, measure it, break it, and make the architecture decision yourself.

A long video is a reference library, not a requirement to watch every minute.

---

## Frontend

### JavaScript + TypeScript
- TypeScript Handbook: https://www.typescriptlang.org/docs/handbook/intro.html
- MDN JavaScript: https://developer.mozilla.org/en-US/docs/Web/JavaScript
- React TypeScript: https://react.dev/learn/typescript
- Hindi TypeScript course index: https://www.classcentral.com/course/youtube-typescript-in-hindi-55990

**Target:** understand types, async code, API contracts and generated TSX. Do not pursue advanced JS internals.

### React
- Sheryians ReactJS Full Course: https://www.youtube.com/watch?v=3LRZRSIh_KE
- React Learn: https://react.dev/learn

Watch only the component/props/hooks/state/forms/API/useEffect/routing/context sections listed in Week 2.

### Next.js
- Official Learn: https://nextjs.org/learn
- Official docs: https://nextjs.org/docs
- Hindi full course: https://www.youtube.com/watch?v=Mct6dyl_gz4

For the Hindi video, use only App Router (35:09 onward), navigation/image/font, TypeScript (4:05:37 onward), API routes (6:23:59 onward) and data fetching (6:59:20 onward). Skip the projects if time is limited.

### Tailwind / shadcn
- Tailwind: https://tailwindcss.com/docs
- shadcn/ui: https://ui.shadcn.com/docs

No long course required. Learn from docs while building the dashboard.

---

## Data / Backend

### PostgreSQL
- Hindi: **Master POSTGRESQL in ONE VIDEO — Beginner to Advanced — MPrashant**. Search by exact title on the MPrashant channel if the YouTube URL changes.
- MPrashant channel: https://www.youtube.com/@MPrashant
- PostgreSQL docs: https://www.postgresql.org/docs/
- SQLBolt: https://sqlbolt.com/

The indexed 2026 ranking lists the MPrashant Hindi PostgreSQL course at ~4h48m and ~790k views. Watch the sections on relational model, CRUD, joins, constraints, indexes, transactions and query optimization; skip DBA/admin material not used by NextSwitch.

### FastAPI + SQLAlchemy + Alembic
- FastAPI SQL databases: https://fastapi.tiangolo.com/tutorial/sql-databases/
- SQLAlchemy: https://docs.sqlalchemy.org/
- Alembic: https://alembic.sqlalchemy.org/

No full new backend course: this is already your work domain.

### Redis
- Redis University: https://university.redis.com/
- Redis docs: https://redis.io/docs/latest/

Focus on cache-aside, TTL, invalidation, rate limiting, queues and failure behavior.

---

## Containers / CI

### Docker
- Hindi: MPrashant — Docker Course For Beginners 2025: https://www.youtube.com/watch?v=OhnTMWmfTBE
- Docker docs: https://docs.docker.com/get-started/
- Dockerfile: https://docs.docker.com/reference/dockerfile/
- Compose: https://docs.docker.com/compose/

Watch only the timestamps in Week 10.

### GitHub Actions
- Docs: https://docs.github.com/en/actions
- Quickstart: https://docs.github.com/en/actions/get-started/quickstart

Use a Hindi video only if YAML/workflow concepts are unclear. Do not spend a week on CI/CD syntax.

---

## Kubernetes

- Kubernetes Basics: https://kubernetes.io/docs/tutorials/kubernetes-basics/
- Kubernetes docs: https://kubernetes.io/docs/home/
- Helm: https://helm.sh/docs/

You already have Kubernetes knowledge. **Do not restart a beginner playlist.** Learn by deploying NextSwitch and deliberately breaking pods/probes/rollouts.

---

## AWS

### Hindi first pass
MPrashant — AWS in ONE VIDEO [HINDI]: https://www.youtube.com/watch?v=N4sJj-SxX00

Watch only the IAM, ELB/ASG, S3, RDS, VPC, ECS and EKS timestamps in Week 14.

### Authority
- AWS Skill Builder: https://builder.aws.com/learn
- AWS Architecture Center: https://aws.amazon.com/architecture/
- AWS Workshops: https://workshops.aws/
- EKS docs: https://docs.aws.amazon.com/eks/
- EKS Workshop: https://www.eksworkshop.com/
- Well-Architected: https://aws.amazon.com/architecture/well-architected/

---

## AI / Inference

### vLLM
- Docs: https://docs.vllm.ai/
- Examples: https://docs.vllm.ai/en/latest/examples/

### Transformers
- https://huggingface.co/docs/transformers/

### MLflow
- https://mlflow.org/docs/latest/

Do not optimize for knowing flags. Optimize for understanding latency, throughput, GPU memory, batching, KV cache, quantization, concurrency, cost and failure behavior.

---

# What requires your own engineering judgment

These are the parts you should spend the most effort on because AI-generated code is not enough without system context:

1. **Architecture boundaries** — monolith vs services; sync vs async.
2. **Data modeling** — schema, indexes, consistency, transactions.
3. **Caching** — what is cached, TTL, invalidation, fallback.
4. **Queues** — idempotency, retries, DLQ, ordering and backpressure.
5. **API contracts** — payloads, versioning, pagination, errors.
6. **Security** — secrets, auth, IAM, network boundaries.
7. **Scaling** — what metric triggers scaling and where the bottleneck actually is.
8. **AI model selection** — quality vs latency vs cost.
9. **RAG design** — chunking, retrieval, reranking, evaluation.
10. **Inference** — batching, concurrency, GPU memory, caching, fallbacks.
11. **Reliability** — timeouts, retries, circuit breakers, graceful degradation.
12. **Observability** — what to measure and why.
13. **Cost** — cost per request/user/document and where the money goes.
14. **Trade-offs** — why the simplest architecture that satisfies the requirement is preferable.

## Rule
**AI writes implementation. You own the decision.**

For every major feature, write a short ADR containing:
- Context
- Decision
- Alternatives considered
- Cost/latency impact
- Failure mode
- Why this choice wins
