# README for the Kubernetes Project

This README is a comprehensive resource that provides a structured overview of the Kubernetes project. It offers practical insights and guidance on setting up a Kubernetes cluster and deploying a containerized application. 

## Kubernetes Project Overview

![Kubernetes Visual](https://github.com/Kiineo/KubeApp/assets/103956412/0496b051-c82f-4019-9e18-cd5f73b66c95)

## Parameters

The project encapsulates a collection of critical parameters and configurations that underpin its core functionality:

- **KOPS Configuration Parameters**: This section delineates fundamental settings governing the Kubernetes cluster. Parameters encompass the cluster name, AWS region, node instance types, and assorted variables.

- **Container Parameters**: Parameters related to the containerized application are enumerated, encompassing image names, environment variables, and resource allocation requests.

- **Secrets and Credentials**: Sensitive data, including database and RabbitMQ passwords, are housed in this section.

- **LoadBalancer Configuration Parameters**: Detailed here are parameters germane to LoadBalancer services, including service type and port assignments.

- **Elastic Block Store (EBS) Volume Parameters**: Configuration parameters pertaining to EBS volumes are expounded, addressing size and type considerations.

- **Node Labeling Parameters**: Parameters employed in the process of node labeling based on availability zones are presented.

- **Application-Specific Configuration**: This section encompasses parameters tailored to the specific behavior and functionality of the containerized application.

## KOPS/S3

### Infrastructure Setup

The project's preliminary phase is characterized by the establishment of essential infrastructure components:

- **EC2 Instance and S3 Bucket**: An EC2 instance is commissioned to function as the KOPS server, and an S3 bucket is configured to serve as the repository for cluster state storage.

## Kubernetes Cluster/Nodes

### Cluster Configuration

This section elucidates the orchestration of the Kubernetes cluster, underpinned by a series of configuration steps and practices:

- **Kubernetes Definition and Service Files**: Configuration files, employing the YAML format, are the keystone of cluster management. These files delineate resource specifications and behavioral attributes.

- **Deployment Configurations**: The project entails deployment configurations for various components within the Kubernetes cluster, ensuring streamlined execution and management.

- **Node Labeling**: A detailed examination of node labeling strategies, hinged upon availability zones, is presented. Node labeling optimizes resource allocation and fortifies redundancy.

### Application Deployment

Central to the project is the deployment of the containerized application:

- **Containerized App Deployment**: The Kubernetes cluster, primed for operation, hosts the deployment of a containerized application sourced from DockerHub. Stringent image specifications and tags are stipulated to guarantee operational continuity.

#### Containerized Application Components

- Application Container: kiineo/vprofileapp:latest
- Database Container: kiineo/vprofiledb:latest
- Memcached Container: memcached
- RabbitMQ Container: rabbitmq

## Data Persistence

### Elastic Block Store (EBS) Volume

In an effort to uphold data persistence for the database pod, a dedicated Elastic Block Store (EBS) volume is instantiated and configured. Subsequently, the volume is seamlessly affixed to the database pod, assuring the integrity of the data.

## Kubernetes Resource Definitions

### Kubernetes Definition Files

The project encompasses a diverse array of Kubernetes definition files, each affording granular control over pivotal resources. The following YAML-based definitions are enumerated:

- **App-secret.yaml**: This file orchestrates a Kubernetes Secret, housing sensitive data such as database and RabbitMQ passwords.

- **Database Service Configuration (db-CIP.yaml)**: Configuration specifications for a ClusterIP service governing database connectivity are encapsulated herein.

- **Memcached Service and Deployment Configuration (mc-CIP.yaml and Mc-dep.yaml)**: This segment configures a ClusterIP service for Memcached and orchestrates the Memcached Deployment.

- **RabbitMQ Service and Deployment Configuration (rmq-CIP.yaml and Rmq-dep.yaml)**: The project articulates ClusterIP service configuration for RabbitMQ and prescribes the RabbitMQ Deployment.

- **Application Service and Deployment Configuration (Vproapp-service.yaml and Vproappdep.yaml)**: A LoadBalancer service configuration for the application is outlined alongside deployment definitions for the containerized application.

- **Database Deployment Configuration (Vprodbdep.yaml)**: This section delineates the Deployment specifications for the database, incorporating volume mounts and environment variable definitions.

## Domain Integration

### Linking LoadBalancer with Domain

In the final project phase, the LoadBalancer assumes a pivotal role by becoming intricately linked with the project's domain. This integration culminates in the seamless accessibility of the Kubernetes application to external users.
