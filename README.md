# MySQL Kubernetes Cluster (3-node GTID Replication)

This repo sets up a 3-node MySQL GTID-based replication cluster using Kubernetes StatefulSets.

## Components

- ConfigMap for MySQL config
- StatefulSet for pods
- Headless service for discovery

## Usage

```bash
kubectl apply -f k8s/secret.yaml
kubectl apply -f k8s/mysql-config.yaml
kubectl apply -f k8s/headless_service.yaml
kubectl apply -f k8s/statefulset.yaml
```

## Shutdown / Restart

```bash
kubectl scale statefulset mysql --replicas=0
kubectl scale statefulset mysql --replicas=3
```
