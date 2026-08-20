# Week 4 — Next.js Foundations

**Dates:** 22–28 Sep 2026  
**Priority:** Supporting skill  
**Target:** 7–9 hours

## Objective
Understand the modern Next.js App Router model. Do not learn the old Pages Router unless maintaining legacy code.

## Learn
- `app/` router
- pages/layouts
- nested + dynamic routes
- Server Components
- Client Components
- `use client`
- navigation
- loading/error UI
- metadata
- basic data fetching

## Primary source
**Official Next.js Learn:** https://nextjs.org/learn

Use the React Foundations and Next.js App Router sections needed for the topics above. The official course is preferred over old long YouTube courses because Next.js changes quickly.

**Docs:** https://nextjs.org/docs

## Build
Convert the candidate UI into Next.js:
- dashboard layout
- `/candidates`
- `/candidates/[id]`
- loading state
- error state
- metadata

## Critical concept
For every component ask:
- Does it need browser state/event handlers?
- If not, can it remain a Server Component?
- Where should data be fetched?

## KPI / exit test
You can explain Server vs Client Components and create nested/dynamic routes without copying a tutorial.

## AI-engineering importance
**Medium-high.** The syntax is easy to generate; server/client boundaries, data flow and security are engineering decisions.
