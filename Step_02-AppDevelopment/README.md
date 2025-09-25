# 💻 Step 02 — Application Development  

## 📌 What is Application Development?  
Application development is the process of designing, coding, testing, and maintaining software.  
In the DevOps lifecycle, it’s the **core phase where developers build the actual application** before moving to CI/CD, containerization, and deployment.  

---

## ⚙️ Setting Up Your Development Environment  

### 🔧 Install Programming Languages  

#### Python  
```bash
# Ubuntu/Debian
sudo apt update && sudo apt install python3 python3-pip -y

# macOS
brew install python

# Windows
winget install -e --id Python.Python.3.11
```

Verify installation:  
```bash
python3 --version
pip3 --version
```

#### Node.js (JavaScript)  
```bash
# Ubuntu/Debian
sudo apt install -y nodejs npm

# macOS (Homebrew)
brew install node

# Windows
winget install OpenJS.NodeJS
```

Verify installation:  
```bash
node -v
npm -v
```

---

## 📝 Example: Simple Python App  
```python
def main():
    print("Hello, DevOps!")

if __name__ == "__main__":
    main()
```

Run it:  
```bash
python3 app.py
```

✅ You just built your first app!  
