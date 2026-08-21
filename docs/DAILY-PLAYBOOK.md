# Switch — Daily Playbook

This is the **one clean path** to follow each study day. Do not open the whole roadmap and choose randomly.

## Daily operating loop

### Step 1 — Learn
Watch/read only the listed source and only the listed sections.

### Step 2 — Reproduce
Write one tiny example yourself without copying the video.

### Step 3 — Apply
Put the concept into the current Switch project/lab.

### Step 4 — Break it
Change one assumption, overload it, fail a dependency, or create a bad implementation.

### Step 5 — Measure
Record the metric that proves whether your change helped.

### Step 6 — Explain
Write 5–10 lines answering: **What problem did this solve? Why this design? What trade-off did it introduce?**

### Step 7 — End-of-day architecture question
Answer the day's question without looking at notes. If the answer is weak, carry the topic forward.

---

# Week 1 — Frontend literacy fast-track

**Purpose:** only enough frontend knowledge to direct/review AI-generated UI. Do not turn this into a frontend specialization.

## Day 1 — JavaScript minimum
**Learn:** functions, objects, arrays, destructuring, spread, map/filter/reduce, modules.

**Source:** MDN JavaScript Guide — https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide

**Do:** write a small function that transforms a list of candidates into ranked output.

**End question:** Could I read AI-generated JavaScript that transforms API data without needing AI to explain every line?

## Day 2 — Async JavaScript + TypeScript basics
**Learn:** promises, async/await, try/catch, fetch, JSON; TS primitives, objects, interfaces, type aliases.

**Source:** TypeScript Handbook — https://www.typescriptlang.org/docs/handbook/intro.html

**Do:** type a FastAPI candidate response and fetch it.

**End question:** What happens when an API call fails or returns unexpected data?

## Day 3 — React fundamentals
**Learn:** components, JSX/TSX, props, state, useState, events, lists.

**Source:** Sheryians React course — https://www.youtube.com/watch?v=3LRZRSIh_KE

**Watch only:** components (~01:06), props (~01:26), hooks/state (~04:56–05:20), forms (~05:55).

**Do:** candidate card + candidate list.

**End question:** Which state actually belongs in the component, and which should come from the API?

## Day 4 — React API integration
**Learn:** useEffect, API calls, loading/error/empty states, basic custom hooks.

**Source:** same Sheryians course; API calls (~07:33), useEffect (~07:54).

**Do:** connect candidate list to FastAPI.

**End question:** What happens when the API is slow, fails, or returns 10,000 records?

## Day 5 — Next.js literacy
**Learn:** App Router, pages, layouts, Server vs Client Components, data fetching.

**Source:** Next.js Learn — https://nextjs.org/learn

**Do:** create a small dashboard route consuming the FastAPI API.

**End question:** Why is this component server-side or client-side?

## Day 6 — Tailwind + shadcn/ui
**Learn:** flex/grid, spacing, responsive layout, Button/Card/Input/Table/Dialog.

**Sources:** https://tailwindcss.com/docs and https://ui.shadcn.com/docs

**Do:** make the candidate dashboard usable on desktop/mobile.

**End question:** What UI work should I delegate entirely to AI?

## Day 7 — Frontend checkpoint
Build one small end-to-end page: Next.js → FastAPI → response → UI.

**Do not learn new frontend topics.**

**End question:** Can I review AI-generated frontend code and identify unnecessary state, bad API calls, unsafe assumptions, and incorrect Server/Client boundaries?

---

# Week 2 — PostgreSQL + performance

## Day 1 — Schema design
**Learn:** tables, primary/foreign keys, constraints, relationships.
**Source:** PostgreSQL docs — https://www.postgresql.org/docs/current/tutorial.html
**Do:** design candidates/jobs/applications schema.
**Question:** What data belongs together and what must be normalized?

## Day 2 — SQL + joins
**Learn:** SELECT, WHERE, JOIN, GROUP BY, HAVING, subqueries.
**Do:** write candidate-ranking queries.
**Question:** Which query becomes expensive as data grows?

## Day 3 — Indexes
**Learn:** B-tree, composite indexes, selectivity, write cost.
**Do:** generate 100k+ rows and compare indexed/unindexed queries.
**Question:** Why did this index help this query but not another?

## Day 4 — EXPLAIN ANALYZE
**Learn:** sequential scan, index scan, cost, actual time, rows.
**Do:** benchmark a slow query before/after optimization.
**Question:** What evidence proves the optimization worked?

## Day 5 — Transactions + pooling
**Learn:** ACID, isolation basics, connection pooling.
**Do:** create concurrent writes and inspect behavior.
**Question:** What can go wrong if 1,000 API requests each open a DB connection?

## Day 6 — FastAPI + PostgreSQL
**Learn:** SQLAlchemy/SQLModel or your chosen ORM, migrations, repository/service separation.
**Do:** integrate the schema with FastAPI.
**Question:** Where should DB logic live and why?

## Day 7 — PostgreSQL checkpoint
Load-test the API against the DB and identify one real bottleneck.
**Question:** If candidates grow from 100k to 10M, what changes first and why?

---

# Week 3 — Redis + caching

## Day 1 — Redis fundamentals
**Source:** Redis University/docs — https://redis.io/docs/latest/develop/
**Learn:** keys, values, TTL, common data structures.
**Do:** cache candidate/job reads.
**Question:** What should be cached?

## Day 2 — Cache patterns
**Learn:** cache-aside, invalidation, TTL.
**Do:** implement cache-aside.
**Question:** When can stale data become dangerous?

## Day 3 — Rate limiting
**Learn:** counters, sliding-window/token-bucket concepts.
**Do:** rate-limit an AI endpoint.
**Question:** What happens when one client floods the API?

## Day 4 — Redis failure
**Do:** turn Redis off and observe behavior.
**Question:** Does the system fail open or fail closed, and why?

## Day 5 — Redis + FastAPI
**Do:** integrate caching/rate limiting cleanly.
**Question:** Does Redis actually reduce latency/cost? Measure it.

## Day 6 — Queue concepts
**Learn:** producer, consumer, queue depth, retry, dead-letter queue.
**Question:** Why should long AI work leave the request path?

## Day 7 — checkpoint
Write a one-page architecture for API + Redis + queue.

---

# Week 4 — Distributed systems fundamentals

## Day 1 — Distributed-system model
**Learn:** multiple nodes, network calls, partial failure, latency.
**Source:** Perfect Computer Engineer Hindi intro — https://www.youtube.com/watch?v=klUH2wqxzyw
**Do:** draw single-node vs multi-node architecture.
**Question:** What new failures appear when one service becomes five?

## Day 2 — Scaling
**Learn:** vertical vs horizontal scaling, stateless services, load balancing.
**Do:** run 1 vs 2 FastAPI replicas.
**Question:** What must be stateless for horizontal scaling to work?

## Day 3 — Concurrency
**Learn:** concurrency vs parallelism, I/O-bound vs CPU-bound, async.
**Do:** benchmark synchronous vs async I/O.
**Question:** What actually limits this endpoint: CPU or waiting?

## Day 4 — Queues/workers
**Learn:** producer/consumer, workers, retries, DLQ.
**Do:** document ingestion API → queue → worker.
**Question:** What happens if jobs arrive faster than workers process them?

## Day 5 — Reliability
**Learn:** timeout, retry, exponential backoff, idempotency.
**Do:** make an LLM call timeout and safely retry it.
**Question:** Can retrying create duplicate side effects?

## Day 6 — Backpressure + rate limiting
**Do:** deliberately overload workers.
**Question:** How do you prevent the system from collapsing under overload?

## Day 7 — distributed design interview
Design the resume-processing system for 10 → 1,000 → 10,000 concurrent users.
**Question:** Which component becomes the first bottleneck, and how do you know?

---

# Week 5 — Docker + production containers

## Day 1:** Docker mental model; image/container/process.
Source: https://docs.docker.com/get-started/
Do: containerize FastAPI.
Question: What belongs inside an image?

## Day 2:** Dockerfile layers, caching, environment variables.
Do: optimize image build.
Question: Why is the image slow/large?

## Day 3:** Docker Compose.
Do: Next.js + FastAPI + PostgreSQL + Redis.
Question: How do services discover each other?

## Day 4:** health checks and graceful shutdown.
Do: add health/readiness behavior.
Question: How does the platform know a service is safe to receive traffic?

## Day 5:** resource limits and logs.
Do: constrain CPU/memory and observe behavior.
Question: What happens when the container hits its limit?

## Day 6:** security basics.
Do: non-root user, secrets outside image.
Question: What information must never be baked into an image?

## Day 7:** production container checkpoint.
Run the full local stack and document every dependency.

---

# Week 6 — CI/CD + deployment

## Day 1:** GitHub Actions basics — https://docs.github.com/en/actions
Do: lint/test workflow.
Question: What should fail the build?

## Day 2:** build/test/container pipeline.
Do: build Docker image in CI.
Question: How do you prevent broken images reaching production?

## Day 3:** registry.
Do: push image to a registry.
Question: How should images be versioned?

## Day 4:** deployment strategy.
Learn rolling/canary/blue-green concepts.
Question: How do you roll back safely?

## Day 5:** secrets/configuration.
Do: separate config from code.
Question: What belongs in secrets management?

## Day 6:** failure test.
Deploy a deliberately broken version and roll it back.

## Day 7:** checkpoint.
Document your pipeline from commit to running service.

---

# Week 7 — Kubernetes core for AI APIs

**Source:** Kubernetes Basics — https://kubernetes.io/docs/tutorials/kubernetes-basics/

## Day 1:** Pods + Deployments.
Do: deploy FastAPI.
Question: Why isn't a Pod a deployment strategy?

## Day 2:** Services.
Do: expose API internally.
Question: How does service discovery work?

## Day 3:** ConfigMaps + Secrets.
Do: externalize configuration.
Question: What should never be stored in a ConfigMap?

## Day 4:** readiness/liveness.
Do: break a health check and observe traffic behavior.
Question: What is the difference between "alive" and "ready"?

## Day 5:** resources.
Do: requests/limits.
Question: What happens when a pod has no resource discipline?

## Day 6:** Ingress/load balancing.
Do: expose the API.
Question: Where should TLS/traffic routing happen?

## Day 7:** checkpoint.
Deploy the AI API from scratch without following a copy-paste tutorial.

---

# Week 8 — Kubernetes scaling + failure lab

## Day 1:** HPA basics.
Do: scale API replicas from load.
Question: What metric should trigger scaling?

## Day 2:** load testing.
Use k6 or Locust.
Source: https://grafana.com/docs/k6/latest/
Do: baseline 1 replica.
Question: What is the current throughput and p95?

## Day 3:** 1 → 2 → 5 replicas.
Measure each step.
Question: Did throughput actually scale linearly? Why not?

## Day 4:** kill pods.
Question: How quickly does the system recover?

## Day 5:** DB bottleneck.
Question: What if API replicas scale but PostgreSQL cannot?

## Day 6:** queue bottleneck.
Question: What if workers consume slower than producers produce?

## Day 7:** scaling report.
Document bottlenecks, measurements and architecture changes.

---

# Week 9 — AWS architecture

## Day 1:** IAM + security.
Source: AWS Skill Builder — https://skillbuilder.aws/
Do: least-privilege design.
Question: Which component needs which permission?

## Day 2:** VPC/subnets/security groups.
Do: draw private/public architecture.
Question: What should never be publicly reachable?

## Day 3:** S3 + ECR.
Do: store resumes/images in S3 and images in ECR.
Question: Why object storage instead of DB blobs?

## Day 4:** RDS/PostgreSQL.
Do: connect securely.
Question: What changes when DB becomes managed?

## Day 5:** ALB + compute.
Compare ECS vs EKS.
Question: Why choose EKS instead of ECS here?

## Day 6:** CloudWatch/observability.
Do: monitor service health.
Question: What signals tell you the system is unhealthy?

## Day 7:** AWS architecture review.
Produce cost-aware architecture.

---

# Week 10 — RAG scaling

## Day 1:** baseline RAG: 10 documents.
Do: chunk/embed/retrieve/generate.
Question: What exactly determines retrieval quality?

## Day 2:** evaluation.
Learn precision@k, recall@k, MRR, NDCG, context relevance, faithfulness.
Question: How do you know retrieval improved?

## Day 3:** 1,000 documents.
Do: batch ingestion and metadata filters.
Question: What becomes slower?

## Day 4:** 10,000 documents.
Do: ANN/hybrid retrieval experiment.
Question: When does brute-force retrieval stop being practical?

## Day 5:** reranking.
Do: retrieve bounded candidates → rerank.
Question: Why not rerank the entire corpus?

## Day 6:** multi-tenant/caching/index versioning concepts.
Question: How do you prevent tenant data leakage?

## Day 7:** RAG architecture interview.
Design 100k-document RAG and defend every component.

---

# Week 11 — AI evaluation + monitoring

## Day 1:** system metrics: RPS, p50/p95/p99, errors, saturation.
Do: instrument API.

## Day 2:** AI quality metrics.
Do: create evaluation dataset.

## Day 3:** retrieval evaluation.
Do: measure recall@k/precision@k.

## Day 4:** answer evaluation.
Do: measure relevance/faithfulness/hallucination cases.

## Day 5:** tracing/logging.
Source: OpenTelemetry — https://opentelemetry.io/docs/
Do: trace API → retrieval → LLM.

## Day 6:** dashboard.
Use Prometheus/Grafana concepts.
Do: display latency/errors/AI quality/cost.

## Day 7:** monitoring incident.
Create a quality regression and identify it from telemetry.

---

# Week 12 — LLM inference + vLLM

## Day 1:** inference fundamentals: tokens, latency, throughput, concurrency.
Source: vLLM docs — https://docs.vllm.ai/
Question: What is the difference between latency and throughput?

## Day 2:** batching + continuous batching.
Question: Why can batching improve GPU utilization?

## Day 3:** KV cache.
Question: What consumes GPU memory during generation?

## Day 4:** quantization.
Question: What quality/performance trade-off does quantization create?

## Day 5:** model serving.
Do: serve a suitable open model locally if hardware permits.

## Day 6:** benchmark.
Measure concurrency, latency, tokens/sec, memory.

## Day 7:** inference architecture.
Compare hosted API vs self-hosted vLLM.

---

# Week 13 — AI cost engineering

## Day 1:** token economics.
Calculate cost/request.

## Day 2:** caching.
Measure saved model calls.

## Day 3:** model routing.
Compare small vs large model strategy.

## Day 4:** retrieval optimization.
Reduce unnecessary context.

## Day 5:** batching/asynchronous workloads.
Measure throughput/cost.

## Day 6:** infrastructure cost.
Compare CPU/GPU/managed API options.

## Day 7:** cost report.
State quality, latency and cost trade-offs.

---

# Week 14 — Reliability engineering for AI

## Day 1:** timeouts/retries.

## Day 2:** circuit breakers/fallbacks.

## Day 3:** idempotency.

## Day 4:** malformed LLM output.
Do: schema validation + retry/fallback.

## Day 5:** dependency failure.
Kill Redis/DB/LLM and observe.

## Day 6:** rate limits/load shedding.

## Day 7:** failure matrix.
Document failure → detection → impact → mitigation → recovery.

---

# Week 15 — System design interview mastery

Each day choose one prompt and follow:

**clarify workload → baseline → bottleneck → scale → reliability → observability → cost → trade-offs.**

## Day 1
Design AI resume processing for 10 → 10,000 users.

## Day 2
Design RAG for 100k documents.

## Day 3
Design asynchronous document ingestion.

## Day 4
Design multi-tenant AI API.

## Day 5
Design model-serving platform.

## Day 6
Design monitoring/evaluation platform.

## Day 7
Whiteboard one complete architecture from memory.

---

# Week 16 — Final capstone

Build and document the **AI Candidate Intelligence Platform**.

Required path:

`Next.js → FastAPI → queue → workers → PostgreSQL/Redis → RAG → LLM → monitoring → Docker → Kubernetes → AWS`

## Day 1
Baseline MVP.

## Day 2
Load test.

## Day 3
Find first bottleneck.

## Day 4
Fix and benchmark.

## Day 5
Introduce failure and recover.

## Day 6
Cost/performance optimization.

## Day 7
Final architecture review + README.

## Final question
**If traffic, documents, latency requirements and AI cost all increase by 10×, what changes first, why, how do you measure it, and what trade-offs do you accept?**

---

# Daily rule

If you finish the day's learning but cannot answer the end-of-day question, the day is **not complete**.

If you cannot explain why a component exists, do not add another component.

If you cannot measure an optimization, do not claim it improved the system.

If AI writes the code, **you still own the architecture and the explanation.**
