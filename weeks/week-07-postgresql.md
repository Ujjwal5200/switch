# Week 7 — PostgreSQL Foundations

**Dates:** 13–19 Oct 2026  
**Priority:** **CORE**  
**Target:** 8–10 hours

## Objective
Move beyond CRUD. Learn to make database decisions that affect AI-system latency, correctness, concurrency and cost.

## Learn
- relational modeling
- primary/foreign keys
- one-to-many/many-to-many
- joins
- constraints
- indexes
- transactions
- isolation basics
- `EXPLAIN` basics
- migrations

## Video — Hindi first pass
Search/use a current Hindi PostgreSQL full course from a high-view Indian educator only for the initial mental model. Do **not** treat the video as the authority; verify every feature in the official docs.

Because YouTube rankings/views change and search results are unstable, the durable source is:
- PostgreSQL docs: https://www.postgresql.org/docs/
- SQLBolt interactive SQL: https://sqlbolt.com/

## Build
Design NextSwitch schemas for:
- users
- jobs
- resumes
- candidates
- candidate_scores

Then write the important queries and indexes.

### Engineering lab
Create 100k+ candidate rows. Compare:
1. query without index
2. query with index
3. query with a bad index

Use `EXPLAIN ANALYZE` and record execution time.

## AI-engineering focus — HIGH
AI can generate SQL. **You must decide:**
- schema boundaries
- normalization vs denormalization
- which indexes are justified
- transaction boundaries
- pagination strategy
- consistency requirements
- what data should never be duplicated

## KPI / exit test
You can explain every important index, transaction boundary and query plan in NextSwitch.
