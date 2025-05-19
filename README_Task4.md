
# DevOps Project

## Build a Version-Controlled DevOps Project with Git

### Project Overview
This project demonstrates a hands-on implementation of a version-controlled DevOps workflow using Git and GitHub. It includes best practices like branching strategy, pull requests, tagging, and proper documentation via README.

---

## Table of Contents
1. [Project Objectives](#project-objectives)
2. [Technologies Used](#technologies-used)
3. [Repository Structure](#repository-structure)
4. [Branching Strategy](#branching-strategy)
5. [Implementation Steps](#implementation-steps)
6. [Key Features](#key-features)
7. [Usage Guide](#usage-guide)
8. [Versioning](#versioning)

---

## Project Objectives
- Manage a DevOps project using Git best practices.
- Implement branching strategies.
- Use pull requests to merge code safely.
- Document progress through README.
- Use Git tags for versioning.

---

## Technologies Used
- **Version Control**: Git
- **Repository Hosting**: GitHub
- **Documentation**: Markdown

---

## Branching Strategy
- **main**: Production-ready stable branch.
- **dev**: Active development happens here.
- **feature/**: Individual feature/task branches.

---

## Implementation Steps

### 1. Initialize Local Repository
```bash
mkdir DevOps-Project-VersionControl
cd DevOps-Project-VersionControl
git init
```

### 2. Add .gitignore and First Commit
```bash
echo "node_modules/" > .gitignore
git add .gitignore
git commit -m "Initial commit with .gitignore"
```

### 3. Link to GitHub
```bash
git remote add origin https://github.com/mani-6666/DevOps-Project-VersionControl.git
git branch -M main
git push -u origin main
```

### 4. Create dev Branch
```bash
git checkout -b dev
git push -u origin dev
```

### 5. Create a Feature Branch
```bash
git checkout -b feature/readme-setup
```

### 6. Add README.md
Write and save this README file, then:
```bash
git add README.md
git commit -m "Add README with project structure and guide"
git push -u origin feature/readme-setup
```

### 7. Create Pull Request (PR)
- Go to GitHub.
- Open a PR from `feature/readme-setup` → `dev`.
- Merge it after review.

### 8. Tag the Release
```bash
git checkout main
git merge dev
git push
git tag -a v1.0 -m "Initial project setup with branching and README"
git push origin v1.0
```

---

## Key Features
- Organized Git branching structure.
- Pull request-based code merging.
- Git tagging for versioning.
- Markdown-based project documentation.

---

## Usage Guide

### Clone the Repository
```bash
git clone https://github.com/mani-6666/DevOps-Project-VersionControl.git
cd DevOps-Project-VersionControl
```

### Work on a New Feature
```bash
git checkout -b feature/new-feature
# make changes...
git add .
git commit -m "Implement new feature"
git push -u origin feature/new-feature
```

### Merge Changes
Create PR → Merge to `dev` → Merge `dev` to `main` → Tag release.

---

## Versioning
Tags are used for version control.

To create a new tag:
```bash
git tag -a v1.1 -m "Add second feature"
git push origin v1.1
```
