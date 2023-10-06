# Kubernetes Project README

This Kubernetes project sets up a Kubernetes cluster using KOPS on Amazon EC2 instances, deploys a containerized application from DockerHub, creates an EBS Volume for a database pod, and labels nodes based on availability zones.

## Prerequisites
Before you begin, ensure you have the following prerequisites in place:

- An AWS account with appropriate IAM permissions
- `kops` installed on your local machine
- A DockerHub account to access container images
- The AWS Elastic Block Store (EBS) volume ID for database persistence

## Getting Started

### Create EC2 Instances with KOPS
1. Use `kops` to create EC2 instances for your Kubernetes cluster. Replace `your-cluster-name` and `your-aws-region` with your desired values.

   ```shell
   kops create cluster --node-count=2 --node-size=t2.micro --zones=us-east-1a your-cluster-name
Edit the cluster configuration to meet your requirements.

shell
Copy code
kops edit cluster your-cluster-name
Apply the cluster configuration.

shell
Copy code
kops update cluster your-cluster-name --yes
Create Kubernetes Cluster
Once the EC2 instances are provisioned, create the Kubernetes cluster.

shell
Copy code
kops create cluster --name=your-cluster-name --state=s3://your-state-bucket --zones=us-east-1a --yes
Deploy Containerized App
Deploy the containerized application from DockerHub. Replace kiineo/vprofileapp:latest with your desired image and tag.

shell
Copy code
kubectl apply -f Vproappdep.yaml
Create EBS Volume for DB Pod
Create an EBS volume in your AWS account and note its volumeID.

Update Vprodbdep.yaml with the correct volumeID and any other necessary configurations.

Apply the updated configuration.

shell
Copy code
kubectl apply -f Vprodbdep.yaml
Label Nodes with Zone Names
Label nodes with their respective availability zones. Update Vprodbdep.yaml and Mc-dep.yaml with the appropriate nodeSelector section.

yaml
Copy code
nodeSelector:
  zone: us-east-1a
Apply the updated configurations for both deployments.

shell
Copy code
kubectl apply -f Mc-dep.yaml
kubectl apply -f Vprodbdep.yaml
Kubernetes Definitions
Secret Configuration
app-secret.yaml: Defines a Kubernetes Secret containing sensitive data like database and RabbitMQ passwords.
Database Service Configuration
db-CIP.yaml: Configures a ClusterIP service for the database.
Memcached Service and Deployment Configuration
mc-CIP.yaml: Configures a ClusterIP service for Memcached.
Mc-dep.yaml: Defines a Memcached Deployment.
RabbitMQ Service and Deployment Configuration
rmq-CIP.yaml: Configures a ClusterIP service for RabbitMQ.
Rmq-dep.yaml: Defines a RabbitMQ Deployment.
Application Service and Deployment Configuration
Vproapp-service.yaml: Configures a LoadBalancer service for the application.
Vproappdep.yaml: Defines the Deployment for the containerized application.
After setting up the cluster and deploying the application, link the LoadBalancer to your domain as needed.

Feel free to modify these configurations to suit your specific requirements and cluster setup. Enjoy using Kubernetes!
