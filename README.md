# Kubernetes Project README

This README provides an overview of the steps and components involved in setting up a Kubernetes cluster and deploying a containerized application.

## EC2 KOPS Setup

In the initial phase, the project sets up the necessary infrastructure to get started with Kubernetes. This includes creating an EC2 instance to serve as the KOPS server and configuring an S3 bucket for cluster state storage.

## Kubernetes Cluster

Once the infrastructure is in place, the project proceeds to create and configure the Kubernetes cluster. This section covers the Kubernetes definition and service files, deployment configurations for various components, and node labeling based on availability zones.

## Containerized App Deployment

With the cluster ready, the project moves on to deploying the containerized application from DockerHub. The project specifies the image location and tag to ensure the application runs smoothly.

## EBS Volume for DB Pod

To ensure data persistence for the database pod, an Elastic Block Store (EBS) volume is created and configured, which is then attached to the database pod.

## LABEL Node with Zones Names

The project also labels the Kubernetes nodes based on their availability zones. This node labeling is essential for optimizing resource allocation and redundancy within the cluster.

## Kubernetes Definition Files

Below are the Kubernetes definition files for deployment, services, secrets, and volumes:

- **App-secret.yaml:** Defines a Kubernetes Secret containing sensitive data like database and RabbitMQ passwords.

- **Database Service Configuration (db-CIP.yaml):** Configures a ClusterIP service for the database.

- **Memcached Service and Deployment Configuration (mc-CIP.yaml and Mc-dep.yaml):** Configures a ClusterIP service for Memcached and defines the Memcached Deployment.

- **RabbitMQ Service and Deployment Configuration (rmq-CIP.yaml and Rmq-dep.yaml):** Configures a ClusterIP service for RabbitMQ and defines the RabbitMQ Deployment.

- **Application Service and Deployment Configuration (Vproapp-service.yaml and Vproappdep.yaml):** Configures a LoadBalancer service for the application and defines the Deployment for the containerized application.

- **Database Deployment Configuration (Vprodbdep.yaml):** Defines the Deployment for the database, including volume mounts and environment variables.

## The Final Deployment

This section guides through the final steps to get everything up and running within the Kubernetes cluster. It includes applying configurations, ensuring that all components are deployed correctly, and verifying the setup.

## Linking LoadBalancer with Domain

In the last step, the LoadBalancer is linked to the domain, making the Kubernetes application accessible to external users.
