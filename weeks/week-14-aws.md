# Week 14 — AWS Foundations for AI Products

**Dates:** 1–7 Dec 2026  
**Priority:** **CORE**  
**Target:** 8–10 hours

## Objective
Understand the AWS pieces behind your architecture; do not memorize services.

## Primary Hindi video — MPrashant
**AWS in ONE VIDEO — For Beginners 2025 [HINDI]**  
https://www.youtube.com/watch?v=N4sJj-SxX00

This is a long ~10-hour survey. **Do not watch it all.** Watch only:
- 00:28:21–00:43:41 — AWS overview + account setup
- 00:43:41–01:09:00 — IAM
- 02:56:44–03:38:14 — ELB/Auto Scaling
- 03:38:14–04:25:05 — S3
- 04:25:05–04:55:53 — RDS
- 06:53:57–07:39:24 — VPC + practical VPC
- 08:30:57–08:48:27 — ECS
- 08:48:27–09:16:05 — EKS

The indexed result reports 1.3M+ views, so it is a strong Hindi first-pass resource. Do not treat it as your architecture authority.

## Authoritative sources
- AWS Skill Builder: https://builder.aws.com/learn
- AWS Architecture Center: https://aws.amazon.com/architecture/
- AWS Workshops: https://workshops.aws/

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

## Build
Move one non-critical NextSwitch component to AWS. Start with S3 or a small backend deployment.

## Architecture lab
Draw 3 versions:
1. low-cost MVP
2. production SaaS
3. high-traffic AI inference service

For each, justify compute, network, storage and observability choices.

## AI-engineering focus — EXTREMELY HIGH
AI can tell you what AWS services exist. **Your differentiator is choosing fewer services intelligently.** Think about cost, latency, blast radius, security, operational burden and scaling.

## KPI / exit test
Given an AI product requirement, you can draw the AWS architecture and explain each major boundary and trade-off.
