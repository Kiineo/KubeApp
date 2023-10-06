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

## Linking LoadBalancer with Domain

In the last step, the LoadBalancer is linked to the domain, making the Kubernetes application accessible to external users.

### The URL is now under my domain

![URL](https://github.com/Kiineo/KubeApp/assets/103956412/aee1eb18-610a-4fdf-9786-c9b6efde5923)


## Confirming that the services are working

### The HomePage is Working
![HomePage](https://github.com/Kiineo/KubeApp/assets/103956412/6ca24fe0-0c13-4adc-80af-74d6030b526a)

### RabbitMQ is Working
![RabbitMQ](https://github.com/Kiineo/KubeApp/assets/103956412/c1fbf2bb-994f-4991-8570-f821d1bf4489)

## Memcache Has Access To User List
![Memcache](https://github.com/Kiineo/KubeApp/assets/103956412/3243c86d-bf66-4c6b-8411-0d4189cca0dc)

### Memcache Can Access Data From Individual Users
![memcache2](https://github.com/Kiineo/KubeApp/assets/103956412/9b6033af-8632-4b52-bf0c-cd2c96b1c3db)



