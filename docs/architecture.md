# System Architecture

## Overview
DevOps Simulator follows a microservices architecture designed for high availability and scalability. This document covers both production and development configurations.

## Components

### 1. Application Server
- **Technology**: Node.js + Express
- **Production Port**: 8080
- **Development Port**: 3000
- **Scaling**: Horizontal auto-scaling (production only)
- **Development Features**: Hot reload, debug mode

### 2. Database Layer
- **Database**: PostgreSQL 14
- **Production**: Master-slave replication with automated backups
- **Development**: Single local instance with seed data

### 3. Monitoring System
- **Production**: Prometheus + Grafana with email alerts
- **Development**: Console logging with verbose output
- **Metrics**: CPU, Memory, Disk, Network

## Deployment Strategy

### Production
- **Method**: Rolling updates
- **Zero-downtime**: Yes
- **Rollback**: Automated on failure
- **Region**: us-east-1

### Development
- **Method**: Docker Compose
- **Features**: Hot reload, instant feedback
- **Testing**: Automated tests before deployment

## Security
- **Production**: SSL/TLS encryption, strict access controls
- **Development**: Relaxed security for easier debugging

## Experimental Architecture (NOT PRODUCTION-READY)

> WARNING: The following describes experimental architecture options retained for reference. These are untested, may be unstable, and must not be enabled in production. To enable experimental features, use the `experimental` flags in `config/app-config.yaml` and `config/database-config.json`, and run in a dedicated testing environment.

### Summary
The experimental build explores AI/ML integration, multi-cloud orchestration, and chaos engineering. It is intended for research, canary testing, and feature validation in non-production environments.

### Highlights of experimental features
- Event-driven microservices with Kafka-based event streaming.
- AI/ML pipeline for anomaly detection, load prediction, and auto-scaling.
- Multi-cloud orchestration with Kubernetes and custom CRDs.
- Global load-balancing and cross-cloud failover strategies.
- Long-term metrics storage (Thanos) and AI log analysis (ELK + ML).

### How to try experimental features (testing only)
1. Make a copy of this repository in a dedicated test account/cluster.
2. In `config/app-config.yaml` set `experimental.enabled: true` and review the experimental block.
3. In `config/database-config.json` set `experimental.enabled: true`.
4. Set environment variables such as `DEPLOY_ENV=experimental` and `MONITOR_EXPERIMENTAL=true` before running deploy or monitor scripts.
5. Monitor closely and keep rollback/backup plans ready.

### Notes
- Experimental components may require additional services (Kafka, TensorFlow, model artifacts, multi-region cloud credentials).
- Keep production configuration unchanged; experimental settings are intentionally isolated to preserve backward compatibility.

For production documentation and operational runbooks, refer to the sections above.
