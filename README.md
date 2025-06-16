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

## 🛠️ Real Project Ideas

### 1. Portfolio Website with GitHub Pages

- Build a simple HTML/CSS or Hugo-based website
- Host it via GitHub Pages
- Add CI/CD deployment with GitHub Actions

### 2. Open Source Contribution Tracker

- Create a script/app that uses the GitHub API to track PRs, stars, or activity
- Practice using personal access tokens and REST calls

### 3. Dotfiles Repository

- Version control your terminal, editor, and Git configurations
- Use symbolic links and setup scripts for portability

### 4. Team Project Using GitHub Flow

- Collaborate with others on a real app or tool
- Use pull requests, issues, projects, and protected branches

### 5. Build a GitHub Action

- Create a reusable GitHub Action (e.g., linting, automation, custom script)
- Write an `action.yml` and test in public repos

### 6. Markdown Docs Site with CI

- Build documentation with MkDocs or Docsify
- Auto-deploy updates with GitHub Actions

### 7. Change History Visualizer

- Use `git log` to parse commit data
- Visualize activity with graphs using Python or JavaScript

---

## 🧠 Git & GitHub Flashcards

### 🔧 Git Commands

- `git init` → Start a new Git repository
- `git clone <url>` → Copy a repo to your machine
- `git add <file>` → Stage file for commit
- `git commit -m "msg"` → Save staged changes
- `git status` → See current repo status
- `git log` → View commit history
- `git diff` → View unstaged changes
- `git reset` → Unstage or undo changes
- `git stash` → Temporarily save uncommitted work
- `git branch` → List branches
- `git checkout <branch>` → Switch branches
- `git merge <branch>` → Merge a branch into current
- `git rebase <branch>` → Rebase current onto another
- `git revert <commit>` → Create commit to undo a change

### 🐙 GitHub Essentials

- `git remote add origin <url>` → Connect local repo to GitHub
- `git push origin main` → Push changes to GitHub
- Pull Request (PR) → Propose code changes to a repo
- Issue → Track tasks, bugs, or features
- GitHub Actions → Automate workflows
- `gh pr create` → Create a pull request from CLI

---

## 🧪 Advanced Git & DevOps Workflow Guide

### 🔄 Git Flow (Feature Branch Workflow)

1. Clone the repo
2. Create a feature branch: `git checkout -b feature/xyz`
3. Commit changes on feature branch
4. Push: `git push origin feature/xyz`
5. Open PR to `main`
6. Review + merge PR

### 🛠 DevOps Git Integration

- Use GitHub Actions to auto-lint, test, and deploy:

```yaml
on: [push]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - run: npm install && npm test
```

- Use branch protection rules for quality gates
- Enforce reviewers before merging
- Integrate with tools like SonarQube, CodeCov, or Terraform

### 🔁 CI/CD Best Practices

- Keep `main` deployable at all times
- Use `.env` and secrets for configuration
- Separate build, test, and deploy stages
- Include rollback strategies (e.g., keep previous deployment archive)

### 🌍 Multi-Environment Deploy

- Use environment-specific branches: `dev`, `staging`, `prod`
- Set environment secrets in GitHub Actions
- Auto-deploy to S3, EC2, or containers

---

## ☁️ GitHub Actions + AWS S3 Deployment Guide

### Prerequisites

- An AWS account
- An S3 bucket created (e.g., `my-website-bucket`)
- GitHub repo connected
- AWS credentials stored as GitHub Secrets (`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`)

### Example GitHub Action Workflow

```yaml
name: Deploy to S3

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout source
        uses: actions/checkout@v3

      - name: Sync to S3
        uses: jakejarvis/s3-sync-action@master
        with:
          args: --acl public-read --delete
        env:
          AWS_S3_BUCKET: my-website-bucket
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_REGION: us-east-1
          SOURCE_DIR: ./
```

### Steps to Test

1. Push a change to `main` branch.
2. Check Actions tab on GitHub for workflow status.
3. Visit your S3 bucket's public endpoint to see the deployed site.

---

## 📃 Notes & Reflections

Use this section to record what you’ve learned, errors you encountered, and how you fixed them.

---

**Congratulations!** You've completed the Git & GitHub Power User workbook.
