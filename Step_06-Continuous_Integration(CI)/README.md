# 🔄 Step 06 — Continuous Integration (CI)  

## 📌 What is CI?  
Continuous Integration is the practice of **automatically testing and integrating code** whenever changes are pushed.  
This ensures fewer bugs and faster delivery.  

---

## ⚙️ GitHub Actions Setup  

Create a workflow file `.github/workflows/ci.yml`:  

```yaml
name: CI Pipeline

on:
  push:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: "3.x"

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Run Tests
        run: pytest
```

✅ Now your repo automatically tests code on push!  
