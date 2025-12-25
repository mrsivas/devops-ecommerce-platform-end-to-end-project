# Kubernetes Configuration for E-Commerce Platform

This directory contains Kubernetes manifests for deploying the e-commerce platform, including backend API, frontend, and supporting resources.

## Overview

The setup includes:
- **Namespace**: [namespace.yaml](namespace.yaml) - Defines the `ecommerce` namespace.
- **Secrets and ConfigMaps**: [secret.yaml](secret.yaml) for database credentials and [configmap.yaml](configmap.yaml) for app environment.
- **Deployments**: [backend-deployment.yaml](backend-deployment.yaml) for the backend API and [frontend-deployment.yaml](frontend-deployment.yaml) for the frontend.
- **Services**: [backend-service.yaml](backend-service.yaml) and [frontend-service.yaml](frontend-service.yaml) to expose the deployments.
- **Ingress**: [ingress.yaml](ingress.yaml) for external access via ALB.

## Prerequisites

- Kubernetes cluster (e.g., EKS as configured in `../terraform/eks/`).
- `kubectl` configured to access the cluster.
- Docker images: `mrsivas/ecommerce-backend:latest` and `mrsivas/ecommerce-frontend:latest` built and pushed.

## Deployment

1. Apply the namespace:
   ```bash
   kubectl apply -f namespace.yaml
   ```

2. Apply secrets and configmaps:
   ```bash
   kubectl apply -f secret.yaml -f configmap.yaml
   ```

3. Deploy backend and frontend:
   ```bash
   kubectl apply -f backend-deployment.yaml -f backend-service.yaml -f frontend-deployment.yaml -f frontend-service.yaml
   ```

4. Apply ingress:
   ```bash
   kubectl apply -f ingress.yaml
   ```

5. Verify:
   ```bash
   kubectl get pods -n ecommerce
   kubectl get services -n ecommerce
   kubectl get ingress -n ecommerce
   ```

## Notes

- Backend runs on port 8080 internally, exposed via service on 80.
- Frontend runs on port 80.
- Ingress uses AWS ALB for internet-facing access.
- Adjust replicas or images as needed.
