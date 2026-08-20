# Week 1 — JavaScript + TypeScript

**Dates:** 20 Aug–7 Sep 2026  
**Priority:** Supporting skill / fast track  
**Target:** 6–8 focused hours

## Objective
Understand enough JavaScript and TypeScript to read, modify and review AI-generated React/Next.js code.

## Learn — only this
### JavaScript minimum
- variables, functions, objects, arrays
- destructuring/spread
- map/filter/reduce
- modules/import/export
- promises + async/await
- try/catch
- fetch + JSON

### TypeScript
- primitive/object types
- `interface` vs `type`
- unions + optional properties
- function typing
- generics basics
- `unknown` + type narrowing
- API response typing

## Video/source
**TypeScript in Hindi — Code Step By Step:**
https://www.classcentral.com/course/youtube-typescript-in-hindi-55990

Use lessons **1–19 only**: setup, core types, arrays/objects, unions, literals, type aliases, functions, `unknown`, `never`. Skip classes/configuration unless NextSwitch needs them. The indexed course is ~3h30m; you should watch only the relevant lessons, not the whole thing.

**Official references:**
- TypeScript: https://www.typescriptlang.org/docs/handbook/intro.html
- JavaScript/MDN: https://developer.mozilla.org/en-US/docs/Web/JavaScript
- React TypeScript: https://react.dev/learn/typescript

## Build
Create `frontend-lab/ts-api-client`:
- typed `Candidate` interface
- `GET /candidates/:id` client
- success/error response handling
- mock JSON

Use AI for boilerplate. You must explain the types.

## KPI / exit test
You can read a TSX/API file and explain the types, async flow and error handling without asking AI what basic syntax means.

## AI-engineering importance
**Low.** This is implementation literacy. Your engineering judgment is not the differentiator here.
