# Week 8 — Kubernetes Scaling + Failure Labs

**Priority:** P0
Source: https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/
Load testing: https://grafana.com/docs/k6/latest/

### Day 1
Baseline one replica with k6. Record RPS/p95/p99/errors.

### Day 2
Scale 1 → 2 → 5 replicas. Measure whether scaling is linear.

### Day 3
Configure HPA and choose a meaningful scaling signal.

### Day 4
Kill pods during load; measure recovery.

### Day 5
Create a PostgreSQL bottleneck and show why adding API replicas stops helping.

### Day 6
Create a worker/queue bottleneck and scale workers instead of API replicas.

### Day 7
Write a scaling report: workload, bottleneck, intervention, metric, result, trade-off.

**KPI:** Never say "the system scales" without measurements.