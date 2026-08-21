# Hard Engineering Skills — The AI-Resistant Layer

The purpose of this track is not to compete with AI at code generation. It is to become the person who can decide what should be built, diagnose why it is broken, make it safe, and prove that the change works.

## 1. Linux + runtime fundamentals

Learn enough to reason about real services:
- processes and threads
- CPU and memory
- file descriptors
- signals
- ports/sockets
- environment variables
- permissions
- logs
- process inspection
- basic shell scripting

Proof:
- diagnose a CPU, memory, or file-descriptor problem in a running service;
- explain what happens from process start to accepting HTTP traffic.

## 2. Networking + HTTP

Learn:
- DNS
- TCP basics
- TLS/HTTPS
- HTTP methods/status codes/headers
- keep-alive
- connection pools
- proxies/reverse proxies
- load balancers
- latency and timeouts

Proof:
- trace one request from client → DNS → TLS → proxy/load balancer → API → DB/LLM.

## 3. Software engineering + debugging

Learn:
- modular design
- interfaces/contracts
- dependency boundaries
- logging
- debugging methodology
- code review
- Git workflows
- refactoring
- configuration management
- backward compatibility

Rule:
> Do not ask AI "fix this" before you can describe the failure, expected behavior, and evidence.

Proof:
- take a deliberately broken service and identify the root cause using logs, metrics, traces, and targeted experiments.

## 4. Testing

This is currently under-emphasized in the roadmap and should be treated as core.

Learn:
- unit tests
- integration tests
- API/contract tests
- database tests
- end-to-end tests
- mocking boundaries
- regression tests
- load tests
- failure tests
- AI evaluation tests

For AI systems distinguish:
- deterministic software correctness
- retrieval quality
- model output quality
- production reliability

Proof:
- every major flagship-project component has a meaningful test strategy, not merely high line coverage.

## 5. Security

Learn practical application security:
- authentication vs authorization
- RBAC/ABAC concepts
- JWT/session risks
- password/secret handling
- input validation
- SQL injection
- SSRF
- broken access control
- rate limiting
- insecure file uploads
- dependency/supply-chain risk
- least privilege
- tenant isolation
- audit logging

AI-specific security:
- prompt injection
- indirect prompt injection through retrieved documents
- tool permission boundaries
- sensitive-data leakage
- unsafe structured output/tool calls
- tenant data isolation

Proof:
- write a threat model for the candidate platform and perform at least five deliberate security tests.

## 6. Data structures + algorithms — but only to the useful depth

Do not turn Switch into a DSA grind.

Know deeply enough to reason about:
- hash maps/sets
- arrays/lists
- queues/deques
- heaps/priority queues
- trees
- graphs
- sorting/searching
- Big-O
- concurrency-related data structures

Apply them to real engineering problems:
- top-K candidate ranking
- priority queues
- deduplication
- caching
- scheduling
- graph workflows
- bounded queues

Proof:
- explain the complexity of a real algorithm in the flagship project and justify the data structure choice.

## 7. Data and state correctness

Learn:
- invariants
- idempotency
- consistency
- transactions
- isolation
- optimistic/pessimistic concurrency
- schema evolution
- migrations
- source-of-truth vs derived state

Proof:
- demonstrate what happens when two requests update the same candidate/job concurrently.

## 8. Product and API judgment

AI can generate endpoints. It cannot own the product contract for you.

For every major feature define:
- user/business goal
- API contract
- failure behavior
- latency expectation
- authorization boundary
- observability
- cost implication
- rollback/migration plan

Proof:
- write an ADR before introducing a meaningful architectural component.

## 9. Capacity and economics

Always translate vague scale claims into workload:

`users → active users → requests/sec → concurrency → CPU/DB/model work → queue depth → cost`

Proof:
- never write "supports 10k users" without a defined workload and benchmark.

## 10. Architecture decision records

Create an ADR whenever you make a non-trivial choice.

Minimum format:

1. Context
2. Decision
3. Alternatives considered
4. Why this option
5. Trade-offs
6. Failure modes
7. Cost impact
8. How we will validate it
9. Reversal conditions

Good examples:
- PostgreSQL vs MongoDB
- Redis vs no cache
- sync vs async
- queue choice
- hosted model vs self-hosted inference
- ECS vs EKS
- pgvector vs dedicated vector store

## 11. What AI should and should not do

### Let AI accelerate
- boilerplate
- CRUD scaffolding
- UI implementation
- test case generation
- documentation drafts
- refactoring candidates
- exploratory code

### You must own
- requirements
- architecture
- security boundaries
- data model
- failure semantics
- performance diagnosis
- capacity assumptions
- evaluation methodology
- cost decisions
- production incident reasoning

## Exit criterion

By December, given an unfamiliar AI system, you should be able to:

1. clarify the workload;
2. design the simplest viable architecture;
3. identify state and ownership boundaries;
4. define API/data contracts;
5. identify security risks;
6. predict failure modes;
7. instrument the system;
8. benchmark it;
9. diagnose the bottleneck;
10. make one measured change;
11. explain the trade-off;
12. decide whether the added complexity is actually justified.

That is the core skill Switch is trying to build.
