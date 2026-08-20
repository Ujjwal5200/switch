# Week 13 — Kubernetes Production Patterns

**Goal:** Understand the controls that make Kubernetes workloads safer and scalable.

## Learn
- Ingress
- HPA
- rolling updates
- Helm
- probes in real workloads
- resource requests/limits
- secrets/config separation
- RBAC basics
- persistent storage concepts
- autoscaling trade-offs

## Source
- Kubernetes docs: https://kubernetes.io/docs/home/
- Helm docs: https://helm.sh/docs/

## Build
Package NextSwitch deployment manifests with Helm. Add HPA and probes to FastAPI. Test a rolling update and deliberate failure.

## KPI / exit test
You can explain what happens when a pod dies, traffic spikes, a new version is deployed, or a container fails readiness.

**Time:** 8–10 hours.