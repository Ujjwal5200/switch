# Week 9 — Redis

**Dates:** 27 Oct–2 Nov 2026  
**Priority:** **CORE**  
**Target:** 6–8 hours

## Objective
Know when Redis improves an AI product and when adding it only adds failure modes.

## Learn
- key/value model
- TTL
- cache-aside pattern
- invalidation basics
- sessions
- rate limiting
- queues/background jobs
- pub/sub vs queues
- Streams concept

## Sources
- Redis University: https://university.redis.com/
- Redis docs: https://redis.io/docs/latest/

Use the Redis University introductory material first; use the docs for the exact commands/features you implement.

## Build
1. Cache candidate/job reads with TTL.
2. Add API rate limiting.
3. Add one background job for an expensive operation (e.g. resume parsing).

## Engineering lab
Test Redis failure:
- What happens when cache is down?
- Does the API fail closed or fall back to PostgreSQL?
- What happens to a queued job?

## AI-engineering focus — VERY HIGH
AI can write Redis code. **You decide:**
- cache vs source of truth
- TTL
- invalidation strategy
- idempotency
- retry behavior
- queue vs synchronous request
- failure fallback

## KPI / exit test
You can justify every Redis use in NextSwitch and explain its failure behavior.
