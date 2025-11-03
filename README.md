# k8s-platform

**GitOps platform applications for k8s-base-cluster**

This repository contains ArgoCD applications that extend your base Kubernetes cluster with additional DevOps capabilities.

## Quick Start

After setting up your cluster with [k8s-base-cluster](https://github.com/r-aas/k8s-base-cluster):

```bash
# Add this platform repo to ArgoCD
kubectl apply -f bootstrap/platform-app.yaml
```

## What's Included

- **Monitoring Stack** - Prometheus, Grafana, AlertManager
- **Logging** - Loki for log aggregation  
- **Security** - Vault for secrets management
- **Storage** - MinIO for S3-compatible object storage
- **Backup** - Velero for cluster backup/restore

## Structure

```
apps/
├── monitoring/     # Prometheus stack
├── logging/        # Loki setup
├── security/       # Vault configuration
├── storage/        # MinIO deployment
└── backup/         # Velero setup

bootstrap/
└── platform-app.yaml  # ArgoCD "app of apps"
```

## Usage

1. Deploy base cluster: `git clone https://github.com/r-aas/k8s-base-cluster && cd k8s-base-cluster && ./standalone.sh`
2. Add platform apps: `kubectl apply -f https://raw.githubusercontent.com/r-aas/k8s-platform/main/bootstrap/platform-app.yaml`
3. Access ArgoCD to monitor deployments: `https://argocd.127-0-0-1.sslip.io:8443`

All applications will be automatically deployed and managed by ArgoCD!