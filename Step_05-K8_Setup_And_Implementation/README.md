# ☸️ Step 05 — Kubernetes Setup & Implementation  

## 📌 What is Kubernetes?  
Kubernetes (K8s) is a **container orchestration system** that automates deployment, scaling, and management of containerized applications.  

---

## ⚙️ Installation  

### Minikube (Local Kubernetes)  
```bash
# Ubuntu/Debian
sudo apt update && sudo apt install -y curl
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

Start cluster:  
```bash
minikube start
kubectl get nodes
```

---

## 📝 Example: Deploy an App  
```bash
kubectl create deployment hello-k8s --image=nginx
kubectl expose deployment hello-k8s --type=NodePort --port=80
kubectl get svc
```

✅ Kubernetes is up and running!  
