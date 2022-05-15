# Practice-Kubernetes

## kind
The kind refers to the type of object

## metadata
The metadata is data about the object like its name labels etc.
## Pod
```
kubectl delete pod my-app-replicaset-xxx
kubectl get pods
```

## ReplicaSet
```
kubectl create -f replicaset.yaml
kubectl get replicaset
kubectl describe replicaset myapp-replicaset
kubectl scale replicaset myapp-replicaset --replicas=2
```

## Deployment
```
# Create
kubectl create -f deployment-definition.yml
kubectl create -f delpoyment.yml --record

# Get
kubectl get deployments

# Update
kubectl apply -f deployment-definition.yml
kubectl set image deployment/myapp-deployment nginx:nginx:1.9.1

# Status
kubectl rollout history deployment/myapp-deployment
kubectl rollout status deployment/myapp-deplpyment

# Rollback
kubectl rollout undo deployment/myapp-deployment

# Delete
kubectl delete deployment/myapp-deployment

# View
kubectl describe depliyment myapp-deployment

# Edit
kubectl edit deployment myapp-deployment --record=true
kubectl set image deployment myapp-deployment nginx=nginx:1.18-perl --record

# Able to see the replicaset in the name of the deployment
kubectl get replicaset
kubectl get pods
kubectl get all
kubectl describle deployment myapp-deployment
kubectl create deployment http-frontend --image=https:2.4-alpine
kubectl scale deployment --replicas=3 httpd-frontend
```

### Deployments- Update and Rollback
The deployment has two ways. One is recreate, another one is RollingUpdate. The default setting is rolling update.

### kubectl get all
```
# kubectl get all can get all the resources in the cluster
kubectl get all
```