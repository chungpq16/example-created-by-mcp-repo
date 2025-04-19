# Nginx Kubernetes Deployment

This repository contains Kubernetes manifests for deploying Nginx with best practices.

## Components

1. **Deployment**
   - 3 replicas of Nginx
   - Resource limits and requests
   - Liveness and readiness probes
   - ConfigMap mounted for custom configuration

2. **Service**
   - LoadBalancer type
   - Exposes port 80

3. **ConfigMap**
   - Custom Nginx configuration

## Prerequisites

- Kubernetes cluster
- kubectl configured to connect to your cluster

## Deployment

1. Clone this repository:
   ```bash
   git clone https://github.com/chungpq16/example-created-by-mcp-repo.git
   cd example-created-by-mcp-repo
   ```

2. Apply the manifests:
   ```bash
   kubectl apply -f k8s/
   ```

3. Verify the deployment:
   ```bash
   kubectl get pods
   kubectl get services
   ```

## Configuration

- The Nginx deployment uses the official nginx:1.25.4 image
- Resource limits: 200m CPU, 256Mi memory
- Resource requests: 100m CPU, 128Mi memory
- Custom Nginx configuration is mounted from ConfigMap

## Scaling

To scale the deployment:
```bash
kubectl scale deployment nginx-deployment --replicas=5
```

## Cleanup

To remove all resources:
```bash
kubectl delete -f k8s/
```