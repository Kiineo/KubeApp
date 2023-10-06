# Kubernetes Project README

This Kubernetes project includes the following components:

1. **EC2 KOPS Setup**: This project begins with the creation of EC2 instances using KOPS (Kubernetes Operations).

2. **Kubernetes Cluster Creation**: A Kubernetes cluster is set up.

3. **Containerized App Deployment**: A containerized application is deployed from DockerHub.

4. **EBS Volume for DB Pod**: An Elastic Block Store (EBS) volume is created and configured for database persistence.

5. **Node Labeling with Zones**: Kubernetes nodes are labeled based on their availability zones.

## Kubernetes Definition Files

This project includes various Kubernetes definition files for deployments, services, secrets, and volumes. These files define the configuration for the different components of the application:

### Secret Configuration
- `app-secret.yaml`: Defines a Kubernetes Secret containing sensitive data like database and RabbitMQ passwords.

### Database Service Configuration
- `db-CIP.yaml`: Configures a ClusterIP service for the database.

### Memcached Service and Deployment Configuration
- `mc-CIP.yaml`: Configures a ClusterIP service for Memcached.
- `Mc-dep.yaml`: Defines a Memcached Deployment.

### RabbitMQ Service and Deployment Configuration
- `rmq-CIP.yaml`: Configures a ClusterIP service for RabbitMQ.
- `Rmq-dep.yaml`: Defines a RabbitMQ Deployment.

### Application Service and Deployment Configuration
- `Vproapp-service.yaml`: Configures a LoadBalancer service for the application.
- `Vproappdep.yaml`: Defines the Deployment for the containerized application.

## Deployment Steps

Follow these steps to set up the project:

1. **Create EC2 Instances with KOPS**: Use `kops` to create EC2 instances for your Kubernetes cluster. Replace `your-cluster-name` and `your-aws-region` with your desired values.

2. **Create Kubernetes Cluster**: Once the EC2 instances are provisioned, create the Kubernetes cluster using `kops`.

3. **Deploy Containerized App**: Deploy the containerized application from DockerHub by applying the configuration in `Vproappdep.yaml`.

4. **Create EBS Volume for DB Pod**: Create an EBS volume in your AWS account and note its `volumeID`. Update `Vprodbdep.yaml` with the correct `volumeID` and apply the updated configuration.

5. **Label Nodes with Zone Names**: Label nodes with their respective availability zones. Update `Vprodbdep.yaml` and `Mc-dep.yaml` with the appropriate `nodeSelector` section and apply the updated configurations for both deployments.

6. **Link LoadBalancer to Domain**: Finally, link the LoadBalancer to your domain as needed.

Feel free to customize the configurations to meet your specific requirements and cluster setup.

Enjoy working with Kubernetes!
