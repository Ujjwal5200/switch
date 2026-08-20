# AI Systems Interview Mastery

This is the **high-value reasoning track**. It exists to answer questions such as:

- How does a RAG system change from 1 document to 1,000 to 100,000?
- What becomes the bottleneck?
- What do you cache, queue, batch or shard?
- How do you monitor retrieval quality and production health?
- How do you improve precision/recall without destroying latency or cost?
- How do you scale an AI API from a prototype to a production workload?

Do not memorize interview answers. Build the system, measure it, break it, and explain the trade-offs.

---

## 1. RAG scaling ladder

### Level 0 — 1–10 documents

Architecture:

`documents → chunk → embed → vector store → retrieve → LLM`

Know:
- chunk size/overlap
- embedding model
- top-k
- prompt/context construction
- basic relevance evaluation

Measure:
- retrieval hit rate
- answer correctness
- latency
- token cost

### Level 1 — 100–1,000 documents

Ask:
- Is embedding done synchronously?
- Can ingestion be asynchronous?
- Do we need metadata filters?
- Is retrieval latency acceptable?
- Is the vector index configured correctly?
- Are duplicate/low-quality chunks hurting retrieval?

Introduce:
- background ingestion jobs
- metadata filtering
- batching embeddings
- indexes
- caching where useful
- evaluation dataset

### Level 2 — 10,000–100,000+ documents

Ask:
- How large is the index?
- What is the ingestion rate?
- What is the query rate?
- Do all tenants share one index?
- Do we need tenant partitioning?
- What is the consistency requirement?
- Is vector search still the bottleneck?
- Do we need hybrid retrieval?
- Does reranking become expensive?

Consider:
- hybrid BM25 + vector retrieval
- metadata/tenant partitioning
- ANN indexes
- reranking only a bounded candidate set
- asynchronous ingestion
- queue-based processing
- embedding/model versioning
- index rebuild strategy
- cache strategy
- horizontal scaling

### Level 3 — production multi-tenant RAG

Reason about:
- tenant isolation
- authorization before retrieval
- noisy-neighbor protection
- rate limits
- quotas
- index lifecycle
- backfills
- model migration
- observability
- disaster recovery
- cost attribution

---

## 2. Retrieval quality mastery

Know the difference between:

- precision@k
- recall@k
- MRR
- NDCG
- hit rate
- answer faithfulness
- answer relevance
- context relevance

Practice questions:

1. Retrieval recall is low. What do you change first?
2. Retrieval recall is high but answers are bad. Why?
3. Top-k is increased and latency explodes. What now?
4. Reranking improves quality but doubles latency. Where should it run?
5. Relevant chunks are consistently missed. Is the problem chunking, embeddings, filters or query formulation?
6. How do you create a representative evaluation set?

Never answer "increase top-k" without discussing latency, context size and reranking cost.

---

## 3. AI API scaling ladder

Start with one FastAPI instance.

### Stage A — baseline

`client → FastAPI → LLM → response`

Measure:
- RPS
- p50/p95/p99
- error rate
- CPU/memory
- external API latency

### Stage B — concurrency

Test:
- async I/O
- connection pooling
- timeouts
- rate limiting

### Stage C — horizontal scaling

`Load Balancer → N FastAPI replicas`

Learn:
- stateless services
- session storage
- health checks
- graceful shutdown

### Stage D — slow work becomes asynchronous

`API → queue → worker → DB/object store`

Use for:
- document parsing
- embedding
- bulk ingestion
- long AI jobs

Know:
- retries
- backoff
- dead-letter queues
- idempotency
- job status

### Stage E — Kubernetes

Add:
- Deployment
- Service
- Ingress
- resource requests/limits
- readiness/liveness
- HPA

### Stage F — model bottleneck

Ask:
- Is the LLM provider/API the bottleneck?
- Should inference be batched?
- Should a smaller model handle easy requests?
- Can results be cached?
- Can retrieval be optimized before adding compute?
- Should vLLM serve the model?

---

## 4. Monitoring mastery

Separate **system health** from **AI quality**.

### System health

- RPS
- latency p50/p95/p99
- errors
- saturation
- CPU/memory
- DB latency
- DB connections
- Redis hit/miss
- queue depth
- worker utilization
- model latency
- GPU utilization
- tokens/sec

### AI quality

- retrieval recall@k
- precision@k
- MRR/NDCG
- context relevance
- answer relevance
- faithfulness
- hallucination rate
- refusal rate where relevant
- user feedback

### Cost

- tokens/request
- model cost/request
- embedding cost
- storage
- database cost
- compute cost
- total cost per successful task

The key interview answer is not "use Prometheus." It is:

> **What do you measure, why does it matter, what threshold indicates a problem, and what action follows?**

---

## 5. Bottleneck diagnosis framework

When performance degrades, classify the bottleneck first:

1. CPU-bound
2. Memory-bound
3. GPU-bound
4. Network-bound
5. Database-bound
6. External API-bound
7. Queue/worker-bound
8. Retrieval-bound
9. Model-inference-bound

Then measure before changing architecture.

Example:

`p95 latency = 4s`

Do not immediately add Kubernetes replicas.

Break the request into:

`API 100ms + DB 200ms + retrieval 300ms + reranker 700ms + LLM 2.5s + network 200ms`

Now you have evidence about where to optimize.

---

## 6. Architecture trade-off questions

Practice explaining:

- PostgreSQL vs MongoDB
- pgvector vs dedicated vector DB
- sync vs async
- Redis cache vs database
- SQS vs Kafka
- ECS vs EKS
- hosted LLM vs self-hosted model
- small model vs large model
- reranker vs larger top-k
- one service vs microservices
- CPU workers vs GPU workers
- batch processing vs real-time processing

For every choice answer:

**Why? → What does it improve? → What does it cost? → What new failure mode appears? → When would I remove it?**

---

## 7. Required failure experiments

Run these in your projects:

- Kill one API pod.
- Kill half the API pods.
- Make PostgreSQL slow.
- Exhaust DB connections.
- Make Redis unavailable.
- Make the LLM timeout.
- Return malformed model output.
- Fill the queue faster than workers consume it.
- Send a traffic spike.
- Deploy a deliberately bad version.
- Make retrieval return irrelevant context.
- Make an embedding/index version incompatible.

For each experiment document:

`failure → detection → user impact → mitigation → recovery → permanent fix`

---

## 8. Interview drill format

For every question, answer in this order:

1. **Clarify workload** — users, RPS, document count, payload size, latency target.
2. **Baseline architecture** — simplest system that works.
3. **Identify bottleneck** — what fails first and why.
4. **Scale that bottleneck** — don't scale everything blindly.
5. **Add reliability** — retries, timeouts, idempotency, health checks.
6. **Add observability** — metrics, logs, traces, AI-quality signals.
7. **Discuss cost** — compute, DB, network, tokens.
8. **State trade-offs** — what you gained and what complexity you added.

This structure is more valuable than memorizing a fixed architecture.

---

## 9. Mastery projects

### Project A — RAG Scale Lab

Same RAG system, four datasets:

- 10 documents
- 1,000 documents
- 10,000 documents
- 100,000+ documents if hardware permits

Compare:
- ingestion time
- index size
- retrieval latency
- recall@k
- reranking latency
- answer quality
- cost

### Project B — AI API Scale Lab

One FastAPI endpoint.

Load test it at increasing concurrency.

Progress:

`1 instance → multiple instances → queue/workers → Kubernetes → HPA → AWS`

Record before/after metrics.

### Project C — Production AI Monitoring Lab

Dashboard:
- API latency/errors
- DB latency
- queue depth
- model latency
- token usage
- retrieval metrics
- cost/request

Add an alert for at least one system and one AI-quality metric.

---

## Exit criterion

You are ready for this interview track when you can receive an unfamiliar AI-system prompt and, without memorized wording:

- ask for missing workload assumptions;
- propose a simple baseline;
- predict bottlenecks;
- scale only the required component;
- explain failure modes;
- choose meaningful metrics;
- discuss quality/latency/cost trade-offs;
- describe how you would validate the design with a load/evaluation test.
