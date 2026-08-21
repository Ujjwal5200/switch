# Week 14 — AI Evaluation + Monitoring

**Dates:** 20–26 Nov 2026  
**Priority:** P0  
**Time:** 10–12 hours

## Learn
System health:
- RPS
- p50/p95/p99
- errors
- CPU/memory
- DB latency/connections
- queue depth
- model latency
- GPU utilization

AI quality:
- precision@k
- recall@k
- MRR/NDCG
- context relevance
- answer relevance
- faithfulness
- hallucination rate

Cost:
- tokens/request
- model cost
- embedding cost
- infra cost
- cost/successful task

## Sources
- OpenTelemetry: https://opentelemetry.io/docs/
- Prometheus: https://prometheus.io/docs/
- Grafana: https://grafana.com/docs/
- MLflow evaluation: https://mlflow.org/docs/latest/

## Build
Create a dashboard and evaluation dataset for your RAG/API. Add one system alert and one AI-quality regression check.

## KPI
When latency or quality degrades, identify the likely component and propose a measured change.

## AI-engineering focus
EXTREME: monitoring is useful only when metrics map to decisions.