# 🚀 Step 07 — Continuous Deployment (CD)  

## 📌 What is CD?  
Continuous Deployment automates the release of applications to production after CI tests pass.  
We’ll use **ArgoCD** for GitOps-style deployment.  

---

## ⚙️ Install ArgoCD  

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Check pods:  
```bash
kubectl get pods -n argocd
```

Access ArgoCD UI:  
```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

✅ You now have CD with ArgoCD!  
