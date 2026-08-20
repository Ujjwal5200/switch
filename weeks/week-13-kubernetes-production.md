# Week 13 — Kubernetes Production Patterns

**Dates:** 24–30 Nov 2026  
**Priority:** **CORE**  
**Target:** 8–10 hours

## Objective
Understand the controls that make Kubernetes workloads safe, observable and scalable.

## Learn
- Ingress
- HPA
- rolling updates
- Helm
- probes in real workloads
- requests/limits
- secrets/config separation
- RBAC basics
- persistent storage concepts
- autoscaling trade-offs

## Sources
- Kubernetes docs: https://kubernetes.io/docs/home/
- Helm docs: https://helm.sh/docs/

Use documentation for exact manifests. Use Hindi video only for a concept you cannot understand from docs.

## Build
Package NextSwitch with Helm. Add HPA + probes to FastAPI. Test rolling deployment and deliberate failure.

## Failure/scale labs
- Kill pods under load.
- Set too-low CPU limits.
- Trigger HPA with controlled traffic.
- Deploy a bad version and roll back.

Record: replicas, CPU/memory, latency, errors and recovery time.

## AI-engineering focus — VERY HIGH
The YAML is easy for AI. The hard decisions are:
- what to scale
- what metric to scale on
- minimum/maximum replicas
- resource requests
- graceful shutdown
- rollout strategy
- failure domain
- cost vs reliability

## KPI / exit test
You can explain what happens when a pod dies, traffic spikes, a version changes, or readiness fails.
