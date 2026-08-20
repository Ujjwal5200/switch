# Week 15 — AWS + Kubernetes Deployment

**Dates:** 8–14 Dec 2026  
**Priority:** **CORE**  
**Target:** 8–10 hours

## Objective
Connect Kubernetes knowledge to real cloud infrastructure.

## Learn
- ECR → Kubernetes image flow
- EKS architecture
- ALB/Ingress integration
- IAM for workloads
- RDS connectivity
- S3 access patterns
- CloudWatch logging/metrics
- cost controls/cleanup

## Sources
- EKS docs: https://docs.aws.amazon.com/eks/
- EKS Workshop: https://www.eksworkshop.com/
- AWS Well-Architected: https://aws.amazon.com/architecture/well-architected/

Hindi video is optional here. Prefer the official EKS workshop because this is an integration problem, not a vocabulary problem.

## Build
Target:
`Internet → ALB → EKS → FastAPI → RDS/Redis/S3`

If EKS cost/permissions are unavailable, reproduce the architecture locally and deploy the backend to ECS. Document the trade-off.

## Engineering lab
Measure:
- deployment time
- request latency
- resource usage
- monthly cost estimate
- failure recovery

## AI-engineering focus — EXTREMELY HIGH
AI can generate manifests/Terraform. You own:
- topology
- IAM boundaries
- networking
- autoscaling
- cost controls
- observability
- failure recovery

## KPI / exit test
You can explain the complete request path from internet → load balancer → workload → data/AI services and defend the architecture.
