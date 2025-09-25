# 🖥️ Step 01 — Git & GitHub Basics  

## 📌 What is Git?  
Git is a **distributed version control system** that helps developers track code changes, collaborate with others, and manage project history.  

## 📌 What is GitHub?  
GitHub is a **cloud platform** that hosts Git repositories and adds collaboration features such as:  
- Pull Requests (PRs)  
- Issue Tracking  
- Project Management Boards  
- CI/CD (GitHub Actions)  

---

## ⚙️ Installation  

### 🔧 Install Git  
- [Download Git](https://git-scm.com/downloads)  

Or install using a package manager:  
```bash
# Ubuntu/Debian
sudo apt update && sudo apt install git -y

# macOS
brew install git

# Windows
winget install --id Git.Git -e --source winget
```

---

## 🔑 Configure Git  

After installation, configure your identity:  
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Verify configuration:  
```bash
git config --list
```

---

## 📂 Creating a Local Repository  

```bash
# Initialize a new repo
git init my-project
cd my-project

# Add a file and commit
echo "# My Project" > README.md
git add README.md
git commit -m "Initial commit"
```

---

## 🌍 Connecting to GitHub  

1. Create a repository on GitHub.  
2. Link your local repo to GitHub:  
```bash
git remote add origin https://github.com/username/repo.git
git branch -M main
git push -u origin main
```

---

## 🔄 Common Git Commands  

| Command | Description |
|---------|-------------|
| `git status` | Show changed files |
| `git add <file>` | Stage a file |
| `git commit -m "msg"` | Save changes with a message |
| `git push` | Upload commits to GitHub |
| `git pull` | Download changes from GitHub |
| `git log` | Show commit history |

---

## ✅ Best Practices  
- Commit small, frequent changes.  
- Write clear commit messages.  
- Use branches for features and bug fixes.  
- Sync (`git pull`) before starting new work.  

---

🎉 Congrats! You’ve completed **Step 01** — now you’re ready to start developing apps in **Step 02** 🚀
