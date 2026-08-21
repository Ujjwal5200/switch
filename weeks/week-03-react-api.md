# Week 3 — PostgreSQL Performance

**Dates:** 4–10 Sep 2026  
**Priority:** P0  
**Time:** 8–10 hours

## Learn
- schema design
- primary/foreign keys
- joins
- indexes
- EXPLAIN / EXPLAIN ANALYZE
- transactions/isolation basics
- connection pooling
- pagination
- N+1 problems
- migrations

## Sources
- Hindi PostgreSQL course: https://www.youtube.com/watch?v=qw--VYLpxG4 — use only SQL/schema/index/transaction/query-performance sections.
- PostgreSQL docs: https://www.postgresql.org/docs/

## Build
Create candidate/resume/JD tables. Add a deliberately slow search query. Use EXPLAIN ANALYZE, add an index, and compare latency.

## KPI
Explain exactly why the query got faster and when an index would hurt writes/storage.

## AI-engineering focus
High: data modeling and query trade-offs must be reasoned about, not blindly generated.