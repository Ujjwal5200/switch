# Week 3 — React API Integration

**Dates:** 15–21 Sep 2026  
**Priority:** Supporting skill, but directly relevant to your FastAPI work  
**Target:** 6–8 hours

## Objective
Make the frontend consume the kind of FastAPI services you already build.

## Learn
- fetch/request lifecycle
- typed API clients
- loading/error/empty states
- form submission
- reusable components
- custom hooks for API state
- environment variables concept
- client-side validation basics
- CORS concept

## Sources
- React Learn: https://react.dev/learn
- Fetch API (MDN): https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API
- React + TypeScript: https://react.dev/learn/typescript

No long video is required. If a concept is unclear, search that exact concept in Hindi rather than starting another full React course.

## Build
Connect a React page to a local FastAPI endpoint:

`React form → FastAPI → JSON → typed state → UI`

Use a real endpoint from your existing backend where possible.

## AI workflow
1. You define the OpenAPI/request-response contract.
2. AI generates the client/UI.
3. You inspect types, error paths, CORS, loading states and security assumptions.
4. You test the complete request path.

## KPI / exit test
Given a FastAPI endpoint, you can independently explain how the request reaches the backend and how the response becomes UI state.

## AI-engineering importance
**High for integration judgment.** The difficult part is not JSX; it is deciding API boundaries, state ownership, failure handling and what belongs on client vs server.
