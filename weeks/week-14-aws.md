# Week 14 — AWS Foundations for AI Products

**Dates:** 1–7 Dec 2026  
**Priority:** **CORE**  
**Target:** 8–10 hours

## Objective
Understand the AWS pieces behind your architecture; do not memorize services.

## Learn
- IAM
- VPC basics
- public/private subnets
- security groups
- ECR
- S3
- RDS/PostgreSQL
- ALB
- CloudWatch
- ECS vs EKS decision basics

## Sources
- AWS Skill Builder: https://builder.aws.com/learn
- AWS Architecture Center: https://aws.amazon.com/architecture/
- AWS Workshops: https://workshops.aws/

For Hindi learning, use an AWS Hindi beginner video only for the initial concepts. Then reproduce the architecture with AWS docs/workshops. Do not watch a 10-hour AWS course end-to-end.

## Build
Move one non-critical NextSwitch component to AWS. Start with S3 or a small backend deployment.

## Architecture lab
Given 3 requirements, draw architectures:
1. low-cost MVP
2. production SaaS
3. high-traffic AI inference service

For each, justify compute, network, storage and observability choices.

## AI-engineering focus — EXTREMELY HIGH
AI can tell you what AWS services exist. **Your differentiator is choosing fewer services intelligently.**

Think about:
- cost
- latency
- blast radius
- security boundary
- operational burden
- scaling
- managed vs self-managed

## KPI / exit test
Given an AI product requirement, you can draw the AWS architecture and explain each boundary and major trade-off.
