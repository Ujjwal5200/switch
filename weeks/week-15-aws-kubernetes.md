# Week 15 — AWS + Kubernetes Deployment

**Goal:** Connect your Kubernetes knowledge to real cloud infrastructure.

## Learn
- ECR → Kubernetes image flow
- EKS architecture
- ALB/Ingress integration
- IAM for workloads
- RDS connectivity
- S3 access patterns
- CloudWatch logging/metrics
- cost controls and cleanup

## Source
- EKS docs: https://docs.aws.amazon.com/eks/
- EKS workshops: https://www.eksworkshop.com/
- AWS Well-Architected: https://aws.amazon.com/architecture/well-architected/

## Build
Target:
`Internet → ALB → EKS → FastAPI → RDS/Redis/S3`

Use the smallest practical resources and destroy/stop anything not needed.

## KPI / exit test
Deploy a working service to EKS or, if cost/permissions prevent it, reproduce the architecture locally and deploy the backend to ECS. Be able to explain the trade-off.

**Time:** 8–10 hours.