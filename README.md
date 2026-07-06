# Connect a GitHub Repository with AWS

## 📖 Overview

This project is the second part of the **6-Day DevOps Challenge**, where I connected a GitHub repository to AWS to establish the source stage of a CI/CD pipeline.

The objective was to host the application's source code in GitHub, securely connect the repository to AWS using **AWS CodeConnections**, and prepare the environment for automated builds and deployments in later stages using AWS Developer Tools.

This project demonstrates the importance of version control, source code management, and secure integration between GitHub and AWS services.

> **Naming Convention:** All AWS resources follow the **Orange** naming convention.

---

# 🏗️ Architecture

```text
                    Developer
                        │
                        │
                Git Push / Commit
                        │
                        ▼
               GitHub Repository
                        │
                        │ OAuth Authorization
                        ▼
             AWS CodeConnections
                        │
                        ▼
               AWS CodePipeline
                  (Source Stage)
                        │
                        ▼
             Future Build & Deploy
```

---

# 🎯 Project Objectives

- Create a GitHub repository for the application.
- Upload the Java web application source code.
- Connect GitHub to AWS securely.
- Configure AWS CodeConnections.
- Verify repository synchronization.
- Prepare the application for automated CI/CD workflows.

---

# 🛠️ AWS Services Used

| Service | Purpose |
|----------|---------|
| AWS CodeConnections | Secure connection between GitHub and AWS |
| AWS IAM | Access management |
| AWS CodePipeline | Future CI/CD pipeline |
| GitHub | Source code repository |

---

# 📋 Prerequisites

Before starting this project, I completed:

- AWS Account Setup
- Java Web Application on EC2
- Git installed locally
- GitHub account
- AWS Console access

---

# ⚙️ Step 1 – Create a GitHub Repository

A new GitHub repository was created to host the Java web application.

Repository contents included:

- Maven project
- Java source files
- JSP pages
- `pom.xml`

---

# ⚙️ Step 2 – Initialize Git

Inside the project directory, Git was initialized.

```bash
git init
```

Verify repository status:

```bash
git status
```

---

# ⚙️ Step 3 – Stage Project Files

All application files were staged.

```bash
git add .
```

Verify staged files:

```bash
git status
```

---

# ⚙️ Step 4 – Commit Changes

The first project snapshot was committed.

```bash
git commit -m "Initial commit"
```

This created the first version in Git history.

---

# ⚙️ Step 5 – Connect Local Repository to GitHub

Rename the default branch:

```bash
git branch -M main
```

Connect to GitHub:

```bash
git remote add origin https://github.com/<username>/<repository>.git
```

Verify:

```bash
git remote -v
```

---

# ⚙️ Step 6 – Push Code to GitHub

Upload the project.

```bash
git push -u origin main
```

GitHub now stores the application's source code.

---

# ⚙️ Step 7 – Create an AWS CodeConnection

Inside AWS:

Developer Tools → CodeConnections

Create a new connection.

Configuration:

- Provider: GitHub
- Connection Type: GitHub App
- Authentication: OAuth

---

# ⚙️ Step 8 – Authorize GitHub

AWS redirected to GitHub.

Permissions were granted to:

- Access repositories
- Read repository contents
- Receive repository events

After authorization, the connection status became:

```text
Available
```

---

# ⚙️ Step 9 – Verify Repository Access

AWS successfully displayed the GitHub repository.

This confirms:

- Authentication works.
- AWS can access repository contents.
- Repository is ready for CodePipeline.

---

# 📂 Project Workflow

```text
Developer
      │
      ▼
Git Add
      │
      ▼
Git Commit
      │
      ▼
GitHub Repository
      │
      ▼
AWS CodeConnections
      │
      ▼
CodePipeline Source Stage
```

---

# 💻 Git Commands Used

Initialize repository

```bash
git init
```

Check repository

```bash
git status
```

Stage files

```bash
git add .
```

Commit

```bash
git commit -m "Initial commit"
```

Rename branch

```bash
git branch -M main
```

Connect remote

```bash
git remote add origin <repository-url>
```

Verify remote

```bash
git remote -v
```

Push project

```bash
git push -u origin main
```

Pull updates

```bash
git pull
```

---

# 🔍 Troubleshooting

| Issue | Cause | Solution |
|--------|-------|----------|
| Authentication failed | GitHub not authorized | Re-authorize AWS CodeConnections |
| Repository not visible | Wrong GitHub account | Select correct GitHub account |
| Push rejected | Local branch behind remote | Pull latest changes then push |
| Connection pending | OAuth incomplete | Complete GitHub authorization |

---

# 🔐 Security Considerations

This project uses **AWS CodeConnections**, which securely connects AWS services to GitHub without storing GitHub credentials directly inside AWS.

Benefits include:

- Secure OAuth authentication
- Fine-grained repository permissions
- Easy revocation
- Centralized connection management

---

# 📚 Key Concepts Learned

## Git

A distributed version control system used to track source code changes.

---

## GitHub

A cloud-based platform for hosting Git repositories and collaborating on software projects.

---

## AWS CodeConnections

A managed AWS service that securely integrates external repositories like GitHub with AWS Developer Tools.

---

## Source Control

Maintaining a complete history of application changes, allowing collaboration, rollback, and automation.

---

## CI/CD Source Stage

The first stage of every CI/CD pipeline where application source code is retrieved before building and deployment.

---

# 🎓 Lessons Learned

- Git tracks every change made to application code.
- GitHub serves as a centralized source code repository.
- AWS CodeConnections provides a secure integration between GitHub and AWS.
- Proper version control is essential before implementing CI/CD.
- Source repositories become the trigger point for automated pipelines.

---

# 🚀 Skills Demonstrated

- Git Fundamentals
- GitHub Repository Management
- Version Control
- AWS CodeConnections
- AWS Developer Tools
- Cloud DevOps Foundations
- Source Code Management
- CI/CD Preparation

---

# 🔄 CI/CD Flow

```text
Developer
     │
     ▼
Git Commit
     │
     ▼
GitHub Repository
     │
     ▼
AWS CodeConnections
     │
     ▼
CodePipeline
     │
     ▼
CodeBuild
     │
     ▼
CodeDeploy
```

---

# 🧹 Cleanup

After completing the project:

- Delete unused CodeConnections (optional).
- Remove test repositories if no longer required.
- Revoke GitHub authorization if the environment is temporary.

---

# 🌟 Real-World Use Case

Modern DevOps teams store all application source code in GitHub and integrate it directly with AWS. Every code change pushed to the repository can automatically trigger a CI/CD pipeline that builds, tests, and deploys the application without manual intervention.

Using AWS CodeConnections provides a secure and scalable way to integrate GitHub with AWS services while maintaining centralized authentication and access control.

---

# 📌 Technologies Used

- Amazon Web Services (AWS)
- AWS CodeConnections
- AWS IAM
- AWS CodePipeline
- Git
- GitHub
- Java
- Apache Maven
- Linux
- Visual Studio Code

---

## 👤 Author

**Khaled Ashraf**

Technical Support Engineer | AWS Learner | Cloud & DevOps Enthusiast

---
⭐ *This project is part of my AWS & DevOps learning journey, documenting hands-on experience with cloud infrastructure, version control, and CI/CD practices.*
