# 🐳 Step 04 — Docker Setup & Implementation  

## 📌 What is Docker?  
Docker is a **containerization platform** that packages applications and dependencies into portable containers.  
This ensures apps run the same across all environments.  

---

## ⚙️ Installation  

### Ubuntu/Debian  
```bash
sudo apt update
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
```

### macOS & Windows  
- Download [Docker Desktop](https://www.docker.com/products/docker-desktop)  

Verify installation:  
```bash
docker --version
```

---

## 📝 Example: Run a Container  
```bash
docker run hello-world
```

✅ Docker is installed and working!  
