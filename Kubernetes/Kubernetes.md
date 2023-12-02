# Kubernetes
- Kubernetes is an open-source platform designed to automate deploying, scaling, and managing containerized applications.
- Originally developed by Google and now maintained by the Cloud Native Computing Foundation (CNCF), Kubernetes provides a container-centric infrastructure where you can easily deploy and manage applications in a clustered environment.

# Kubernetes Architecture

### 1. Nodes (Minions)
- A node is a worker machine in a Kubernetes cluster where containers are deployed. Each node can be a physical or virtual machine responsible for running the applications and services.
- A node could be a virtual machine running on a cloud provider like AWS.
- Each node hosts multiple containers and provides resources (CPU, memory, storage) for running those containers.
- ![image](https://github.com/itsarkcodes/Mastering-DevOps/assets/87442305/a1c41ff4-0dba-4365-ad56-ea8bd980c7ed)

### 2. Cluster
-  A cluster in Kubernetes is a set of nodes that collectively run your applications.
-  It includes the master node (control plane) and multiple worker nodes.
-  Ex: Consider a Kubernetes cluster composed of several nodes. This cluster could consist of three worker nodes responsible for running applications and a master node that manages and orchestrates the cluster's resources, scheduling tasks, and ensuring proper communication among nodes.
-  ![image](https://github.com/itsarkcodes/Mastering-DevOps/assets/87442305/a2051ad8-aebf-404b-a290-982b64bcc64b)

### 3. Master 
- The master node in a Kubernetes cluster is responsible for managing the cluster's control plane.
- It oversees the entire cluster, coordinating operations, scheduling applications, and maintaining the desired state of the cluster.
- Ex: the master node handles tasks such as scheduling containers onto nodes, monitoring their health, managing cluster resources, and ensuring the overall cluster's stability. It doesn't typically run user applications but focuses on managing and orchestrating the worker nodes and their resources.
- ![image](https://github.com/itsarkcodes/Mastering-DevOps/assets/87442305/a5e75cc0-d932-4b1f-abdc-971f51e45310)

# Components

### 1. API Server:
- The API server is the core component that exposes the Kubernetes API, which allows users to interact with the cluster.
- It serves as the front-end to the cluster and processes RESTful API requests.
- Example: When a developer uses the kubectl command-line tool to deploy an application or check the status of pods, it sends a request to the API server. For instance, a command like kubectl create deployment ... communicates with the API server to create a deployment in the cluster.

### 2. etcd:
- etcd is a distributed key-value store used for storing the cluster's configuration data, ensuring consistency and providing a reliable source of truth for the entire cluster.
- Example: When you create objects in Kubernetes (e.g., pods, services, deployments), etcd stores their configuration data. For instance, etcd maintains information about the desired state of the cluster, ensuring that if a node or component fails, the cluster can be restored to its desired state based on the stored configuration data.

### 3. Kubelet:
- Kubelet is an agent that runs on each node in the cluster.
- It's responsible for managing and maintaining the state of containers on a node, ensuring they run as expected.
- Example: When a user creates a pod in Kubernetes, the kubelet on the respective node ensures that the pod is started and runs according to the specified configuration. If the pod fails or is not in the desired state, the kubelet takes actions to reconcile the state of the pod.

### 4. Container Runtime:
- The container runtime is responsible for running containers within the pods.
- It interacts with the operating system to start, stop, and manage containers.
- Example: Docker and containerd are examples of container runtimes commonly used with Kubernetes. They manage the execution of containers within pods. For instance, when Kubernetes schedules a pod to run on a node, the container runtime (e.g., Docker) starts and manages the containers within that pod.

### 5. Controller:
- Controllers are control loops that continuously watch the state of the cluster and work towards ensuring that the current state matches the desired state.
- Example: Deployment and ReplicaSet are types of controllers in Kubernetes. For example, when a user defines a deployment with three replicas, the deployment controller constantly monitors the cluster to ensure that there are always three instances (pods) running, reconciling any deviations from the desired state.

### 6. Scheduler:
- The scheduler is responsible for assigning workloads (pods) to nodes based on resource availability and constraints.
- Example: When a new pod is created or when a pod needs to be rescheduled (e.g., due to a node failure), the scheduler evaluates various factors such as resource requirements, node capacity, and constraints to determine the best node to place the pod. For instance, if a pod requires specific hardware capabilities, the scheduler ensures it's placed on a node that meets those requirements.

# Master vs Worker Node
- Here we will see how are the components are distributed across types of server
- ![image](https://github.com/itsarkcodes/Mastering-DevOps/assets/87442305/47b4f4b8-b9d3-4661-b9b4-684a3098f1e7)
