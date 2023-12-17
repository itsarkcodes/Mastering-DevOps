# Replica Set [New, Recommended]
- ReplicaSets are the next-generation version of Replication Controllers. They are more flexible and offer richer pod selection mechanisms.
- Allows more expressive label-based selectors, offering greater flexibility in identifying pods.
- Enables rolling updates and more sophisticated deployment strategies compared to Replication Controllers.
- Example:
```yaml
apiVersion: v1
kind: ReplicaSet
metadata:
  name: rs-myapp
  labels:
    app: myapp
    type: front-end
spec:
  template:
  # Nginx Pod 
    metadata:
      name: pod-myapp
      labels:
        app: myapp
        type: front-end
    spec:
      containers:
        - name: nginx-container
          image: nginx
  replicas: 3
  selector:
    matchLabels:
      type: front-end 
```
- ```selector```: Indicates the criteria used to select which pods the ReplicaSet will manage.
- ```matchLabels```: Specifies the labels that the ReplicaSet uses to find the pods it should control.
# Replication Controller [Old]
- Replication Controllers ensure a specified number of pod replicas are running at any given time. If there are too few or too many pods, it adjusts the count to the desired state.
- Example: To create ReplicationController for Nginx pods. It will create 3 pods of nginx 
```yaml
apiVersion: v1
kind: ReplicationController
metadata:
  name: rc-myapp
  labels:
    app: myapp
    type: front-end
spec:
  template:
  # Nginx Pod 
    metadata:
      name: pod-myapp
      labels:
        app: myapp
        type: front-end
    spec:
      containers:
        - name: nginx-container
          image: nginx
  replicas: 3
```
- ```template```: Describes the pod template that the ReplicationController will use to create new pods.


# How to Scale replicaset?
- You started with 3 replicas but now you want it to have 6
1. Change the replicas in file and Run replace command  
- ```kubectl replace -f replicaset-file.yml```
2. Run scale command (This will not update the file)  
- ```kubectl scale --replicas=6 -f replicaset-file.yml```  
OR  
- ```kubectl scale --replicas=6 replicaset rs-myapp``` Definition file will still have 3
3. You can scale it automatically depending on load (Advance)

# Commands
1. Create replicaset: ```kubectl create -f file.yml```
2. Get replicaset: ```kubectl get replicaset```
3. Delete: ```kubectl delete replicaset rs-myapp``` (Also deletes all underlying POD's)
4. Replace the changes: ```kubectl replace -f replicaset-file.yml```
5. Scale (without modifying the file): ```kubectl scale --replicas=6 -f replicaset-file.yml```
