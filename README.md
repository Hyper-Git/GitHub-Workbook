# Git & GitHub Power User Workbook

This interactive workbook will guide you through exercises from beginner to power user. Follow each task step by step and type the commands in your terminal or Git Bash. Feel free to make mistakes — it’s the best way to learn!

---

## 🎓 Phase 1: Git Basics

### Task 1: Git Installation & Configuration

-

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

### Task 2: Initialize a Repository

-

```bash
cd git-practice
git init
touch README.md
echo "# My Git Practice" > README.md
git add README.md
git commit -m "Initial commit"
```

### Task 3: Basic Workflow

-

```bash
git add README.md
git commit -m "Update README with more info"
git log
```

---

## 🚀 Phase 2: GitHub & Branching

### Task 4: Create and Link a GitHub Repo

-

```bash
git remote add origin https://github.com/yourusername/git-practice.git
git branch -M main
git push -u origin main
```

### Task 5: Create and Merge a Branch

-

```bash
git checkout -b feature-branch
echo "New Feature" >> README.md
git add .
git commit -m "Add new feature"
git checkout main
git merge feature-branch
git push origin main
```

---

## ⚙️ Phase 3: Intermediate Git

### Task 6: Rebase a Branch

```bash
git checkout -b another-feature
echo "Another line" >> README.md
git commit -am "Add another line"
git checkout main
echo "Main change" >> README.md
git commit -am "Main branch update"
git checkout another-feature
git rebase main
```

### Task 7: Stash Changes

```bash
echo "Temporary work" >> temp.txt
git stash
# Confirm file is hidden
git stash pop
```

### Task 8: Undo Mistakes

```bash
git commit --allow-empty -m "Dummy commit"
git log --oneline
git revert <commit-id>
```

---

## 🚧 Phase 4: GitHub Power Tools

### Task 9: Use GitHub Issues & PR

-

### Task 10: GitHub Actions

-

```yaml
name: CI
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Run a one-liner script
        run: echo "CI Running"
```

-

---

## 🌟 Bonus Power Tips

### Task 11: Git Aliases

```bash
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
```

### Task 12: Use GitHub CLI

-

```bash
gh repo clone yourusername/git-practice
gh issue list
gh pr create
```

---

## 📃 Notes & Reflections

Use this section to record what you’ve learned, errors you encountered, and how you fixed them.

---

**Congratulations!** You've completed the Git & GitHub Power User workbook.
