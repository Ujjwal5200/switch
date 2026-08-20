# Switch — Execution Plan

## Calendar

### 20 Aug–7 Sep
Frontend foundations. Do not let this exceed ~8 hours/week.

### 8–30 Sep
Next.js + PostgreSQL. First real vertical slice.

### October
PostgreSQL depth + Redis + Docker + CI.

### November
Kubernetes + AWS.

### December
AI inference + vLLM + end-to-end production integration.

## Weekly operating loop

### Monday–Thursday
Study only what the current week's implementation requires. Prefer official docs and one targeted video for concepts you cannot absorb from docs.

### Friday
Refactor and test what you built.

### Saturday
4-hour build block: no tutorial, only implementation/debugging.

### Sunday
Architecture review:
- What failed?
- What was slow?
- What cost money?
- What could scale badly?
- What did AI generate that you rejected or changed?
- What should be documented?

## KPI hierarchy

1. **Working:** feature actually runs.
2. **Understandable:** you can explain the important code.
3. **Tested:** failure paths are handled.
4. **Measurable:** latency/error/cost is known where relevant.
5. **Deployable:** reproducible environment.
6. **Scalable:** bottlenecks and scaling strategy are understood.

Do not mark a topic complete because you watched a video.

## AI-assisted development rule

For frontend, use AI aggressively. Give it:
- requirements
- API contract
- component boundaries
- state model
- acceptance criteria

Then review:
- security
- data flow
- server/client boundaries
- TypeScript types
- accessibility
- error states
- performance

For AI/infrastructure, keep deeper independent reasoning: architecture, trade-offs, scaling, reliability and cost remain your responsibility.

## December acceptance test

You should be able to take a new AI product requirement and produce:

1. architecture diagram
2. API contract
3. DB schema
4. AI pipeline
5. Next.js UI
6. Docker setup
7. Kubernetes deployment
8. AWS deployment plan
9. CI/CD flow
10. cost/latency/reliability trade-off analysis

If you can do those ten things, the roadmap achieved its purpose.