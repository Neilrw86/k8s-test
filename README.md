# k8s-test

This repository is for managing a Kubernetes cluster using Ingress NGINX and Helm.

## Overview

This project includes configurations for various services and their ingress rules to manage traffic within the Kubernetes cluster.

## Directory Structure

- `apps/`: Contains application-specific configurations.
  - `Jellyfin/`: Configuration for Jellyfin application.
    - `jellyfin-ingress.yaml`: Ingress configuration for Jellyfin.
- `ingress_files/`: Contains ingress configurations for various services.
  - `console.minio_ingress.yaml`: Ingress configuration for MinIO console.
  - `grafana_ingress.yaml`: Ingress configuration for Grafana.
  - `minio_ingress.yaml`: Ingress configuration for MinIO.
  - `uptime-kuma_ingress.yaml`: Ingress configuration for Uptime Kuma.
- `ingress-service.yaml`: Service configuration for the ingress controller.
- `knative/`: Contains Knative service configurations.
  - `homer/`: Configuration for Homer service.
    - `homer-serving.yaml`: Knative service configuration for Homer.
- `README.md`: This file.

## Usage

1. Deploy the ingress controller using the provided `ingress-service.yaml`.
2. Apply the ingress configurations from the `ingress_files/` directory.
3. Deploy application-specific configurations from the `apps/` directory.
4. Deploy Knative services from the `knative/` directory.

## Prerequisites

- Kubernetes cluster
- Helm
- Ingress NGINX controller
- MetalLB (optional, for LoadBalancer IP allocation)

## Installation

1. Install the Ingress NGINX controller:
   ```sh
   helm install ingress-nginx ingress-nginx/ingress-nginx