# Week 16 — AI Inference + Final Integration

**Goal:** Finish the product as an AI Product Engineering proof, not a frontend demo.

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

## Source
- vLLM docs: https://docs.vllm.ai/
- Hugging Face Transformers: https://huggingface.co/docs/transformers/
- MLflow docs: https://mlflow.org/docs/latest/

## Build
Add one serious AI workflow to NextSwitch, for example:
`resume + job description → retrieval → reranking → LLM structured score → persisted result → dashboard`.

Document:
- architecture
- latency
- token/model cost assumptions
- failure modes
- evaluation method
- scaling bottlenecks
- why each infrastructure choice was made

## KPI / exit test
You can explain the end-to-end request path, identify the most expensive/slow component, and propose a scaling or cost optimization without blindly adding infrastructure.

**Time:** 10–14 hours + final integration.
