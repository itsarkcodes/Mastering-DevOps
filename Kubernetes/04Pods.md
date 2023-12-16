# Kubernetes Pod
A pod is the smallest deployable unit in Kubernetes, representing a single instance of an application. It's a group of one or more containers, with shared storage/network resources and a unique IP address within the Kubernetes cluster.

```yaml
apiVersion: v1 # apiVersion: Specifies the version of the Kubernetes API being used.
kind: Pod  # kind: Defines the type of Kubernetes resource, in this case, a Pod.
metadata: # metadata: Contains information about the object. Like the name, labels, and other metadata of the pod.
  name: mypod
  labels:
    app: myapp # can be anything... Just need to identify it
spec:  # spec: Describes the pod's specification, including the containers running inside it.
  containers: # containers: An array of containers within the pod.
  - name: my-container1 # name: Name of the container.
    image: myimage:latest # image: Docker image used for the container.
    ports:  # ports: Port mappings to expose from the container.
    - containerPort: 8080
```
Eg:
![image](https://github.com/itsarkcodes/Mastering-DevOps/assets/87442305/979318ad-0ec4-4490-af82-307b111608eb)

### Once the file is created we can run the below commands
- ```kubectl create -f filename.yaml```: Creates a pod from the specified YAML file.  
- ```kubectl describe pods <pod_name>```: Provides detailed information about a specific pod.  
- ```kubectl get pods```: Lists all pods in the current namespace.
