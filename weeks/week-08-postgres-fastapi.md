# Week 8 — PostgreSQL + FastAPI Integration

**Dates:** 20–26 Oct 2026  
**Priority:** **CORE**  
**Target:** 8–10 hours

## Objective
Turn the database layer into something production-shaped.

## Learn
- SQLAlchemy 2.x
- Pydantic schemas vs DB models
- repository/service separation
- Alembic migrations
- connection pooling
- pagination
- filtering/sorting
- transaction handling
- N+1 query problem

## Sources
- FastAPI SQL databases: https://fastapi.tiangolo.com/tutorial/sql-databases/
- SQLAlchemy: https://docs.sqlalchemy.org/
- Alembic: https://alembic.sqlalchemy.org/

No long video is required because you already know FastAPI. Use a Hindi tutorial only when a SQLAlchemy/Alembic concept blocks you, then verify against the docs.

## Build
Implement:
`Next.js → FastAPI → service/repository → PostgreSQL`

Features:
- candidate CRUD
- filtering
- sorting
- pagination
- Alembic migrations
- transaction for score update

## Engineering lab
Create an N+1 query deliberately, measure it, then fix it. Record the before/after query count and latency.

## AI-engineering focus — VERY HIGH
AI can generate SQLAlchemy models. Your job is deciding:
- service boundaries
- transaction boundaries
- query shape
- pagination method
- failure behavior
- connection-pool sizing assumptions
- what should be synchronous vs background work

## KPI / exit test
A fresh database can be recreated entirely through migrations, and the API does not load unbounded result sets into memory.
