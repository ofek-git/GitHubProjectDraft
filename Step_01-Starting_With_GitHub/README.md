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

## ⚙️ Prerequisites  

<details>
<summary>🔧 Install Git</summary>

- [Download Git](https://git-scm.com/downloads) (Windows, macOS, Linux)  

Or install via package manager:

```bash
# Ubuntu/Debian
sudo apt update && sudo apt install git -y

# macOS (Homebrew)
brew install git

# Windows (winget)
winget install --id Git.Git -e --source winget

</details> <details> <summary>🔑 Configure Git (once per machine)</summary>
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --list   # verify settings

</details>
🚀 Getting Started with GitHub
<details> <summary>1️⃣ Initialize a Local Repo</summary>
mkdir my-first-repo
cd my-first-repo
git init

</details> <details> <summary>2️⃣ Create a File and Commit</summary>
echo "# My First Repo" > README.md
git add README.md
git commit -m "Initial commit"

</details> <details> <summary>3️⃣ Connect to GitHub</summary>

Create a repository on GitHub and copy the URL.

Run:

git remote add origin https://github.com/<your-username>/<repo-name>.git
git branch -M main
git push -u origin main

</details>
🌱 Common Git Commands
Command	Description
git status	🔹 Show repo status
git add <file>	🔹 Stage changes
git commit -m "msg"	🔹 Save changes
git log --oneline	🔹 View history
git push origin main	🔹 Push to GitHub
git pull	🔹 Get latest changes
git clone <url>	🔹 Copy an existing repo
🖼️ Visual Workflow
<p align="center"> <img src="https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png" alt="Git Logo" width="120"/> <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Logo" width="120"/> </p>
📚 Resources

📘 Git Documentation

📗 GitHub Docs

🎓 GitHub Learning Lab

🌐 Atlassian Git Tutorial

✅ After completing this step, you’ll have:

Installed & configured Git ✅

Created your first repository ✅

Connected local code to GitHub ✅

Learned basic version control commands ✅
