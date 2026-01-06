# 🧠 Kubernetes Tutorial — MongoDB + Web App

This repository demonstrates a **beginner-friendly Kubernetes project** where you deploy a **MongoDB database** and a **Node.js/Express-based web application** that connects to it.

## 🌟 What You'll Learn

- Deployments
- Services
- ConfigMaps
- Secrets
- Networking inside Kubernetes

---

## 📂 Repository Contents

| File                | Description                                                   |
|---------------------|---------------------------------------------------------------|
| `mongo-secret.yaml` | Stores MongoDB username and password (as a Kubernetes Secret) |
| `mongo-config.yaml` | Defines environment variables like MongoDB URL (as a ConfigMap) |
| `mongo.yaml`        | MongoDB Deployment and Service definition                     |
| `webapp.yaml`       | Web App Deployment and Service definition                     |
| `README.md`         | Full tutorial and documentation (this file)                  |

---

## 🧰 Prerequisites

Before you begin, ensure you have the following:
- A working Kubernetes cluster (e.g., Minikube, Kind, Docker Desktop)
- `kubectl` command-line tool installed
- Basic familiarity with YAML and Kubernetes commands

### Verify Your Setup

Run the following commands to check your Kubernetes setup:

```bash
kubectl version --client
kubectl cluster-info
kubectl get nodes
```

---

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/Sheshta24/kubernetes-tutorial.git
   cd kubernetes-tutorial
   ```

2. Apply the Kubernetes manifests:
   ```bash
   kubectl apply -f mongo-secret.yaml
   kubectl apply -f mongo-config.yaml
   kubectl apply -f mongo.yaml
   kubectl apply -f webapp.yaml
   ```

3. Check the status of your pods:
   ```bash
   kubectl get pods
   ```

4. Check the services:
   ```bash
   kubectl get svc
   ```
   check services in a namespace
   ```bash
   kubectl get svc -n tailscale
   ```

5. Access the web application:
   ```bash
   minikube service webapp-service
   ```

---

## 🔍 Useful Commands

### Get Full Pod Description
```bash
kubectl describe pod webapp-deployment
```

### Find Minikube IP
```bash
minikube ip
```

### Stream Pod Logs
```bash
kubectl logs -f <pod-name>
```

---

## 🧹 Cleanup

When you're done, clean up the resources:
```bash
kubectl delete -f webapp.yaml
kubectl delete -f mongo.yaml
kubectl delete -f mongo-config.yaml
kubectl delete -f mongo-secret.yaml
```

