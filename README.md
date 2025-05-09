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
kubectl get nodes
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

### Logs for a Pod

```bash
kubectl logs <pod-name> -n <namespace>
```

---

For more, visit the [official Minikube documentation](https://minikube.sigs.k8s.io/docs/) and [Kubernetes docs](https://kubernetes.io/docs/).
