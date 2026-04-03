````md
## Prerequisites (One-time setup)

### Check Git installation
```bash
git --version
````

### Configure Git (if not already done)

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

### Sanity check

```bash
git config --list
```

---

## 1. Initialize Local Repository

Navigate to your project folder:

```bash
cd /path/to/your/project
```

Initialize Git:

```bash
git init
```

Check status:

```bash
git status
```

---

## 2. Add and Commit Files Locally

Add all files:

```bash
git add .
```

Verify staged files:

```bash
git status
```

Initial commit:

```bash
git commit -m "Initial commit"
```

---

## 3. Create GitHub Repo from Terminal

### Option A (Recommended): Using GitHub CLI

Install GitHub CLI (`gh`) first.

Login:

```bash
gh auth login
```

Create repo and push:

```bash
gh repo create repo-name --public --source=. --remote=origin --push
```

---

### Option B: Without GitHub CLI (Manual)

1. Create a new repo on GitHub website (empty repo, no README)

2. Add remote:

```bash
git remote add origin https://github.com/username/repo-name.git
```

Verify remote:

```bash
git remote -v
```

---

## 4. Push Code to GitHub

Rename branch to `main` (if needed):

```bash
git branch -M main
```

Push to remote:

```bash
git push -u origin main
```

---

## 5. Daily Workflow (Basic)

### Check status

```bash
git status
```

### Pull latest changes

```bash
git pull origin main
```

### Add changes

```bash
git add .
```

### Commit

```bash
git commit -m "Describe your changes"
```

### Push

```bash
git push
```

---

## 6. Branching Workflow

### Create a new branch

```bash
git checkout -b feature-branch
```

### Switch branches

```bash
git checkout main
```

### Push new branch

```bash
git push -u origin feature-branch
```

### Merge branch into main

```bash
git checkout main
git pull origin main
git merge feature-branch
git push
```

---

## 7. Syncing with Remote

### Fetch updates (without merging)

```bash
git fetch
```

### Pull and merge

```bash
git pull
```

### View differences

```bash
git diff
```

---

## 8. Undo / Fix Mistakes

### Unstage file

```bash
git reset <file>
```

### Discard local changes

```bash
git checkout -- <file>
```

### Undo last commit (keep changes)

```bash
git reset --soft HEAD~1
```

### Undo last commit (delete changes)

```bash
git reset --hard HEAD~1
```

---

## 9. Useful Inspection Commands

### Commit history

```bash
git log --oneline --graph --all
```

### Show remote

```bash
git remote -v
```

### Show branches

```bash
git branch -a
```

---

## 10. Good Practices

* Always `git pull` before starting work
* Use meaningful commit messages
* Work in branches for new features
* Avoid committing large/unnecessary files
* Use `.gitignore`

---

## 11. Example `.gitignore`

```bash
# Python
__pycache__/
*.pyc

# VS Code
.vscode/

# Logs
*.log

# OS files
.DS_Store
```

---

## 12. Full Minimal Workflow Summary

```bash
cd project-folder
git init
git add .
git commit -m "Initial commit"
gh repo create repo-name --public --source=. --remote=origin --push
```

---

## 13. Troubleshooting

### Authentication issues

* Use SSH instead of HTTPS OR re-authenticate:

```bash
gh auth login
```

### Merge conflicts

```bash
git status
# manually resolve files
git add .
git commit
```

---

## 14. Optional: SSH Setup (More Stable)

Generate SSH key:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Add key to GitHub, then use:

```bash
git remote set-url origin git@github.com:username/repo-name.git
```

---

## End of Guide

```
```
