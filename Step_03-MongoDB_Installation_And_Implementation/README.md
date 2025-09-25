# 🍃 Step 03 — MongoDB Installation & Configuration  

## 📌 What is MongoDB?  
MongoDB is a **NoSQL document-based database** used for storing application data in JSON-like format.  
It’s highly scalable and integrates well with modern applications.  

---

## ⚙️ Installation  

### Ubuntu/Debian  
```bash
sudo apt update
sudo apt install -y mongodb
sudo systemctl start mongodb
sudo systemctl enable mongodb
```

### macOS  
```bash
brew tap mongodb/brew
brew install mongodb-community@6.0
brew services start mongodb-community@6.0
```

### Windows  
- Download installer: [MongoDB Download](https://www.mongodb.com/try/download/community)  
- Run setup wizard and install as a service.  

---

## 📂 Verify Installation  
```bash
mongo --version
```

Run Mongo shell:  
```bash
mongosh
```

✅ MongoDB is ready!  
