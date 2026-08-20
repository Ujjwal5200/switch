# Week 5 — Next.js Application Patterns

**Dates:** 29 Sep–5 Oct 2026  
**Priority:** Supporting skill / product integration  
**Target:** 7–9 hours

## Objective
Build a real frontend shell around your AI/backend APIs.

## Learn
- server-side data fetching
- Route Handlers concept
- forms + mutations
- auth flow concept
- cookies/session concept
- environment variables
- caching/revalidation basics
- URL search params
- pagination/search
- reusable layouts

## Sources
- Official Next.js Learn: https://nextjs.org/learn
- Next.js App Router docs: https://nextjs.org/docs/app

Use documentation for the exact feature when implementing it. Do not consume another long course.

## Build
Add to NextSwitch:
- login screen
- protected dashboard concept
- candidate search/filter
- pagination
- candidate detail page

## AI review checklist
When AI writes code, check:
- Is secret data exposed to the browser?
- Is a Server Component unnecessarily converted to Client?
- Is authentication enforced server-side?
- Is pagination happening at the DB/API layer rather than after fetching everything?
- What happens on slow/failing APIs?

## KPI / exit test
A multi-page Next.js app consumes real FastAPI data with sensible loading/error states and no accidental secret exposure.

## AI-engineering importance
**High.** Security boundaries, API contracts, pagination, caching and failure handling matter more than writing JSX.
