# Elastic Kubernetes Service
- managed Kubernetes service
- Alternative to ECS, similar goal but different API
- Supports EC2 and Fargate deployment
- ![image](https://github.com/itsarkcodes/Mastering-DevOps/assets/87442305/2a2f8dd2-15ce-4afd-a044-c60d72d10a50)

# Node Types
1. Managed Node Groups:
  - Create and manage Nodes (EC2 instance) for you
  - Nodes are part of ASG managed by EKS
  - Supports On-Demand and Spot Instances

2. Self Managed Nodes:
  - Nodes created by you and registered to EKS cluster and managed by ASG
  - You can use - Amazon EKS Optimised AMI
  - Supports On-Demand and Spot Instances

3. AWS Fargate:
  - No maintenance required; no nodes managed

# Data Volumes
- Need to specify StorageClass manifest on EKS Cluster
- Support for EBS, EFS (Fargate), FSx for Lustre, FSx for NetApp ONTAP
