# Kubernetes Project README

This README provides an overview of the Kubernetes project and its components. The project's main goal is to set up a Kubernetes cluster, deploy an application within it, and configure advanced routing using Kubernetes resources.

## Project Components

### EC2 Instance for KOPS
- An EC2 instance is hosted to facilitate the creation of a Kubernetes cluster using KOPS (Kubernetes Operations).
  
### YAML Service Script
- A YAML Service script is engineered to ensure a stable and load-balanced network endpoint for application pods within the Kubernetes cluster.
  
### YAML Deployment Script
- A YAML Deployment script is orchestrated to optimize application management within Kubernetes.
- The deployment script utilizes the `kiineo/vprofileapp` container image from DockerHub.

### Configuration
- A CNAME record is configured for hostname-to-Load Balancer mapping.
- An Ingress YAML script is created to streamline advanced routing in Kubernetes.

## Secrets
- A Kubernetes Secret named `app-secret` is defined.
- It contains sensitive data (`db-pass` and `rmq-pass`) encoded as base64.

## Deployment (vprodb)
- A Kubernetes Deployment named `vprodb` is specified.
- It deploys a single replica of the `kiineo/vprofiledb:latest` container.
- The deployment mounts a volume for MySQL data persistence.
- Init containers are used to perform specific tasks before the main container starts.

## Getting Started
1. **KOPS Cluster Setup**: Follow the necessary steps to set up a Kubernetes cluster using KOPS.
2. **Deploy the Application**: Apply the provided YAML Deployment script to deploy the `kiineo/vprofileapp` container within your Kubernetes cluster.
3. **Configure Routing**: Ensure that the CNAME record is correctly configured for hostname-to-Load Balancer mapping. Apply the Ingress YAML script to set up advanced routing.


Please feel free to reach out for any questions or clarifications regarding this Kubernetes project.

*Author: Michael*

