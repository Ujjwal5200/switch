# Week 4 — Redis + Caching

**Dates:** 11–17 Sep 2026  
**Priority:** P0  
**Time:** 8–10 hours

## Learn
- cache-aside pattern
- TTL/invalidation
- cache stampede
- hot keys
- rate limiting
- sessions
- Redis data structures
- when NOT to cache

## Sources
- Redis docs: https://redis.io/docs/latest/
- Redis caching tutorial: https://redis.io/docs/latest/develop/get-started/

## Build
Add Redis caching to candidate search. Measure DB latency and cache hit/miss. Add a rate limiter.

## Failure lab
Turn Redis off. Decide whether requests fail, bypass cache or degrade gracefully.

## KPI
Explain cache invalidation, stale data risk and why Redis improves the chosen workload.

## AI-engineering focus
High: cache placement, TTL and failure behavior are architecture decisions.