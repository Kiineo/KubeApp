# Kubernetes Project README

## EC2 KOPS Setup

In this initial step, we will set up the necessary infrastructure for your Kubernetes cluster. This includes creating an EC2 instance to serve as the KOPS server and setting up an S3 bucket for cluster state storage.

### Prerequisites
- AWS account with appropriate IAM permissions
- `kops` installed on your local machine

## Kubernetes Cluster

This section focuses on creating and configuring the Kubernetes cluster itself. We will cover the Kubernetes definition and service files, including deployment configurations for various components.

### Kubernetes Definition Files

- **Secret Configuration (app-secret.yaml):** Defines a Kubernetes Secret containing sensitive data like database and RabbitMQ passwords.

- **Database Service Configuration (db-CIP.yaml):** Configures a ClusterIP service for the database.

- **Memcached Service and Deployment Configuration (mc-CIP.yaml and Mc-dep.yaml):** Configures a ClusterIP service for Memcached and defines the Memcached Deployment.

- **RabbitMQ Service and Deployment Configuration (rmq-CIP.yaml and Rmq-dep.yaml):** Configures a ClusterIP service for RabbitMQ and defines the RabbitMQ Deployment.

- **Application Service and Deployment Configuration (Vproapp-service.yaml and Vproappdep.yaml):** Configures a LoadBalancer service for the application and defines the Deployment for the containerized application.

- **Database Deployment Configuration (Vprodbdep.yaml):** Defines the Deployment for the database, including volume mounts and environment variables.

### Node Labeling with Availability Zones

Labeling nodes based on their availability zones is essential for optimizing resource allocation and redundancy within the Kubernetes cluster.

## Containerized App Deployment

This section outlines the deployment of a containerized application pulled from DockerHub. We'll specify the image location and tag.

## The Final Deployment

This section guides you through the final steps to get everything up and running within your Kubernetes cluster. It includes applying configurations, ensuring that all components are deployed correctly, and verifying the setup.

## Linking LoadBalancer with Domain

In this final step, you'll link the LoadBalancer to your domain, ensuring that your Kubernetes application is accessible to external users.

Feel free to customize these configurations and instructions to suit your specific project requirements and cluster setup.

Enjoy working with Kubernetes!
