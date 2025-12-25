# Jenkins

This directory contains the Jenkins CI/CD pipeline configuration for the DevOps E-commerce Platform.

## Overview

The pipeline automates the build, test, and deployment processes for the application's backend, frontend, and infrastructure components using Kubernetes and Terraform.

## Files

- [`Jenkinsfile`](Jenkinsfile): Defines the declarative pipeline stages, including code checkout, building Docker images, running tests, deploying to Kubernetes, and infrastructure provisioning with Terraform.

## Prerequisites

- Jenkins server with required plugins (e.g., Docker, Kubernetes, Terraform).
- Access to Docker registry, Kubernetes cluster, and cloud provider credentials.

## Usage

1. Configure Jenkins with the repository URL and necessary credentials.
2. The pipeline triggers on SCM changes or can be run manually.
3. Monitor builds and deployments via the Jenkins dashboard.

For more details, refer to the main [README.md](../README.md) in the root directory.