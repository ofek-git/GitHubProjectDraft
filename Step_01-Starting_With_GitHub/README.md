# 🖥️ Step 01 — Introduction & Git Basics  

Welcome to the first step of the **DevOps Final Project** 🎉.  
In this step, we’ll learn how to set up Git, create a repository, and start version controlling our code.  

---

## 📌 What is Git?  

Git is a **distributed version control system** that helps developers:  

- 📝 Track changes in source code  
- 👥 Collaborate with teams  
- ⏪ Revert to older versions if needed  
- 🌐 Work both online (GitHub, GitLab, Bitbucket) and offline  

---

## 📝 Git Cheat Sheet (Quick Reference)

```bash
# Configure Git
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --list

# Initialize local repo
mkdir my-first-repo
cd my-first-repo
git init

# Create file and commit
echo "# My First Repo" > README.md
git add README.md
git commit -m "Initial commit"

# Connect to GitHub
git remote add origin https://github.com/<your-username>/<repo-name>.git
git branch -M main
git push -u origin main

# Common commands
git status
git log --oneline
git add <file>
git commit -m "msg"
git push origin main
git pull
git clone <url>
