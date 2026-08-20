# Week 12 — Kubernetes Core

**Dates:** 17–23 Nov 2026  
**Priority:** **CORE**  
**Target:** 8–10 hours

## Objective
Use your existing Kubernetes knowledge to operate the NextSwitch stack rather than rewatching beginner material.

## Learn
- cluster/node/pod mental model
- Deployments
- Services
- namespaces
- ConfigMaps
- Secrets
- requests/limits
- readiness/liveness
- logs/debugging

## Sources
- Kubernetes Basics: https://kubernetes.io/docs/tutorials/kubernetes-basics/
- Kubernetes docs: https://kubernetes.io/docs/home/

Hindi video: use your existing Kubernetes playlist for only the exact missing concept. Do not restart a beginner playlist.

## Build
Deploy FastAPI + Next.js to kind/minikube.

## Labs
1. Kill a pod and observe recovery.
2. Break a readiness probe.
3. Change an image version and roll back.
4. Set a CPU/memory limit and observe behavior.

## AI-engineering focus — VERY HIGH
AI can generate YAML. You decide:
- service boundaries
- resource sizing
- readiness semantics
- scaling triggers
- failure recovery
- config/secret separation
- network exposure

## KPI / exit test
You can deploy, expose, inspect logs, update and roll back a service without a tutorial.
