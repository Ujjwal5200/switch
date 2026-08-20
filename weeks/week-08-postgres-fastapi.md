# Week 8 — PostgreSQL + FastAPI Integration

**Goal:** Make the database layer production-shaped rather than tutorial-shaped.

## Learn
- SQLAlchemy 2.x basics
- Pydantic schemas vs DB models
- repository/service separation
- migrations with Alembic
- connection pooling
- pagination
- filtering/sorting
- transactions in FastAPI
- N+1 query problem

## Source
- SQLAlchemy: https://docs.sqlalchemy.org/
- Alembic: https://alembic.sqlalchemy.org/
- FastAPI SQL databases: https://fastapi.tiangolo.com/tutorial/sql-databases/

## Build
Connect NextSwitch FastAPI to PostgreSQL with migrations. Implement candidate CRUD, filtering and pagination.

## KPI / exit test
Restarting the project from an empty DB should recreate the schema through migrations, and the API should handle pagination/filtering without loading everything into memory.

**Time:** 8–10 hours.