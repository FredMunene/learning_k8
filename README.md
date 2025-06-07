# Kubernetes Major Commands

This README serves as a quick reference for commonly used Kubernetes commands, including how to work with Minikube and `kubectl`.

---

## 🚀 Starting Minikube

### Basic Start

```bash
minikube start
```

### Start with Docker Driver (recommended)

```bash
minikube start --driver=docker
```

### Start with Custom Resources

```bash
minikube start --cpus=2 --memory=4096 --driver=docker
```

### Start Specific Kubernetes Version

```bash
minikube start --kubernetes-version=v1.28.3
```

### Delete and Restart Minikube (clean slate)

```bash
minikube delete
minikube start --driver=docker
```

---

## 🧪 Verify Minikube and Kubernetes

### Check Nodes

```bash
kubectl get nodes -o wide
```

### Get All Pods in All Namespaces

```bash
kubectl get po -A
```

### Check Cluster Info

```bash
kubectl cluster-info
```

### Get Services in All Namespaces

```bash
kubectl get svc -A
```

### reuse 

---

## 🛠️ Useful Minikube Commands

### Stop Minikube

```bash
minikube stop
```

### Check Minikube Status

```bash
minikube status
```

### SSH into Minikube VM

```bash
minikube ssh
```

### Open Kubernetes Dashboard

```bash
minikube dashboard
```

---

## 🧰 Miscellaneous `kubectl` Commands

### Apply a Manifest File

```bash
kubectl apply -f <filename>.yaml
```

### Describe a Pod

```bash
kubectl describe pod <pod-name> -n <namespace>
```

### Delete a Pod

```bash
kubectl delete pod <pod-name> -n <namespace>
```
or
```bash
kubectl delete -f <file.yaml>
```

### Logs for a Pod

```bash
kubectl logs <pod-name> -n <namespace>
```

---

For more, visit the [official Minikube documentation](https://minikube.sigs.k8s.io/docs/) and [Kubernetes docs](https://kubernetes.io/docs/).

### Labels
Labels are key-value pairs attached to Kubernetes objects such as Pods, ReplicaSets, Nodes, Namespaces and Persistent Volumes. 
- `==` or `!= `
- `in` , `notin` , `

###  ReplicationControllers
Ensures a specified number of replicas of a Pod are running at any given time the desired version of the application container, by constantly comparing the actual state with the desired state of the managed application.
The default recommended controller is the `Deployment` which configures a `ReplicaSet` controller to manage application Pods' lifecycle.

### ReplicaSets
With the help of the ReplicaSet, we can scale the number of Pods running a specific application container image. Scaling can be accomplished manually or through the use of an autoscaler. `redis-rs.yaml`
```bash
kubectl create -f redis-rs.yaml
```

A Deployment automatically creates a ReplicaSet, which then creates a Pod. 

### Deployment
the default RollingUpdate strategy  through rollouts and rollbacks
Recreate.
`deploy.yaml`
