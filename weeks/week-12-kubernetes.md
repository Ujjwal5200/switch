# Week 12 — AWS + Kubernetes Deployment

**Dates:** 6–12 Nov 2026  
**Priority:** P0  
**Time:** 10–12 hours

## Learn
- ECR → workload image flow
- EKS architecture
- ALB/Ingress
- IAM for workloads
- RDS connectivity
- S3 access
- CloudWatch
- secrets/configuration
- cost controls

## Sources
- EKS docs: https://docs.aws.amazon.com/eks/
- EKS Workshop: https://www.eksworkshop.com/

## Build
Target: Internet → ALB → EKS → FastAPI → RDS/Redis/S3.

If EKS cost/permissions are unavailable, deploy the same service on ECS and document the trade-off.

## Failure lab
Remove a permission, kill a pod, make the DB unreachable. Document detection and recovery.

## KPI
Trace one request end-to-end and explain the security/network/data path.

## AI-engineering focus
EXTREME.