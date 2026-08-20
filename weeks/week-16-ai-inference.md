# Week 16 — AI Inference + Final Integration

**Dates:** 15–31 Dec 2026  
**Priority:** **CORE / highest-value specialization**  
**Target:** 10–14 hours + final integration

## Objective
Finish NextSwitch as an AI Product Engineering proof, not a frontend demo.

## Learn
- RAG retrieval/reranking review
- structured outputs
- evaluation
- latency vs throughput
- vLLM basics
- continuous/dynamic batching concept
- KV cache concept
- quantization
- GPU memory
- model serving
- autoscaling
- observability

## Sources
- vLLM docs: https://docs.vllm.ai/
- vLLM examples: https://docs.vllm.ai/en/latest/examples/
- Hugging Face Transformers: https://huggingface.co/docs/transformers/
- MLflow: https://mlflow.org/docs/latest/

Use a Hindi vLLM/LLM-serving video only as an introduction if terminology is unfamiliar. For actual implementation, use vLLM documentation because serving behavior, supported models and flags change quickly.

## Build
Add one serious AI workflow:
`resume + JD → retrieval → reranking → LLM structured score → persistence → dashboard`

Measure:
- p50/p95 latency
- token/model cost assumptions
- retrieval quality
- failure rate
- throughput
- bottleneck

## AI-engineering focus — EXTREME
This is where system context matters most. You must reason about:
- model selection vs quality/cost
- sync vs async inference
- batching
- concurrency
- GPU memory
- caching
- retries/timeouts
- fallback models
- rate limits
- evaluation gates
- autoscaling thresholds
- observability

## Architecture exercise
Write a one-page decision record:
1. Why this model?
2. Why this retrieval strategy?
3. Why this database/vector strategy?
4. Why this serving stack?
5. What is the cost/request assumption?
6. What breaks first at 10× traffic?
7. What changes at 100×?

## KPI / exit test
You can trace one request end-to-end, identify the slowest/most expensive component, and propose a measured optimization rather than blindly adding infrastructure.
