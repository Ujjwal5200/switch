# Week 10 — Kubernetes Scaling + Failure Labs

**Dates:** 23–29 Oct 2026  
**Priority:** P0 / very high value  
**Time:** 10–12 hours

## Learn
- HPA
- CPU/memory signals
- custom metrics concept
- horizontal vs vertical scaling
- pod disruption
- graceful shutdown
- load balancing
- resource requests/limits
- queue-based worker scaling

## Sources
- Kubernetes HPA: https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/
- Kubernetes resource management: https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/

## Build
Load-test FastAPI and scale 1 → 2 → 4 replicas. Add HPA. Separately scale workers based on queue depth concept.

## Scaling ladder
1 user → baseline → 100 concurrent → 1,000 → defined 10,000-user workload.

Never claim capacity without a traffic model.

## KPI
Produce a before/after report with RPS, p95 latency, error rate, CPU/memory and replica count.

## AI-engineering focus
EXTREME: diagnose the bottleneck before adding replicas.