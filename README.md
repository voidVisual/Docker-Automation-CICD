# Docker-Automation-CICD
# 🚀 Automated Docker Image Deployment to AWS EC2 using Jenkins & Docker Hub

This project showcases a fully automated CI/CD pipeline using **Jenkins (Master-Agent setup)**, **GitHub Webhook**, **Docker**, **Docker Hub**, and **AWS EC2**. The workflow automates the build, push, and deployment of Dockerized applications — from code commit to production container — with zero manual intervention.

---

## 📌 Tech Stack

- **AWS EC2** – Hosting Jenkins master, Jenkins agent, and Docker runtime.
- **Jenkins** – For CI/CD pipeline automation with master-agent architecture.
- **GitHub Webhook** – Triggers Jenkins job on every code push.
- **Docker** – For containerizing the application.
- **Docker Hub** – Used as the Docker image registry.

---

## 🔄 CI/CD Pipeline Workflow

1. 👨‍💻 Developer pushes code to **GitHub**
2. 🔔 **GitHub Webhook** triggers a Jenkins pipeline job
3. 🧠 **Jenkins Master** delegates tasks to **Jenkins Agent**
4. 🤖 Jenkins Agent:
   - Checks out source code from GitHub
   - Builds a Docker image
   - Tags and pushes the image to **Docker Hub**
5. ☁️ EC2 instance pulls the updated image from Docker Hub
6. 🐳 Docker runs the new containerized application version

---

## 🧭 Architecture Overview

```text
[GitHub] ---> [GitHub Webhook] ---> [Jenkins Master on EC2]
                                        |
                                        ---> [Jenkins Agent on EC2]
                                                  |
                                                  ---> [Docker Build] 
                                                  ---> [Push to Docker Hub]
                                                                      |
                                                                [AWS EC2] ---> [Docker Pull + Run]



