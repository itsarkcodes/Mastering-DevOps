# Replication Controller
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
