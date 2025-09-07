# [K8s Crash Course](https://www.youtube.com/watch?v=s_o8dwzRlu4&ab_channel=TechWorldwithNana)

## Setup 

Start Docker daemon
```bash
open -a Docker
```

Start minikube
```bash
minikube start
```

Check no components running
```bash
kubectl get pod
```

---
## Create components

Create external configurations
Config and secret must be created before Deployments 
```bash
kubectl apply -f mongo-config.yaml
kubectl apply -f mongo-secret.yaml
```

Create db
```bash
kubectl apply -f mongo.yaml
```

Create webapp service
```bash
kubectl apply -f webapp.yaml
```
![alt text](image.png)

---
## Interacting with the cluster

Get all components in the cluster
```bash
kubectl get all
```
![alt text](image-1.png)

```bash
kubectl get config map
kubectl get secret
kubectl get pod
kubectl get svc
```
![alt text](image-2.png)

#### kubectl help / describe

```bash
kubectl help
kubectl get --help
```

```bash
kubectl describe service mongo-service
```
![alt text](image-3.png)

```bash
kubectl describe pod webapp-deployment-6bb4795f54-mhrxs
```
![alt text](image-4.png)

#### kubectl logs
View logs in the pod

```bash
kubectl logs webapp-deployment-6bb4795f54-mhrxs
```
![alt text](image-5.png)

## Accessing the webapp from outside k8s

Get the minikube ip (192.168.49.2)
```bash
minikube ip
kubectl get node -o wide
```
![alt text](image-6.png)

```bash
open http://192.168.49.2:30100
```