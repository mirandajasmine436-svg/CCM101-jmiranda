# 🧪 Laboratory 06 — Cloud Deployment Engineer

## 📖 Mission Overview
Congratulations! Your flawless work in deploying data storage solutions has earned you a spot on the Cloud Deployment Team at CloudNova Technologies.

Up until now, you have been deploying single containers (like a standalone web server or a storage bucket). However, real-world enterprise applications are rarely just one container. They are "multi-tier" systems that require a frontend web application communicating seamlessly with a backend database. Deploying these one by one manually is prone to error. 

In this mission, I transitioned to **Infrastructure as Code (IaC)**. Using Docker Compose, I wrote a YAML configuration file to define and deploy a multi-container private cloud storage application (**Nextcloud** and **MariaDB**) and deployed the entire stack simultaneously with a single command. 

---

## 🎯 Objectives
- 🏗️ Explain the concept of a **multi-tier application architecture**
- 📄 Understand the purpose and structure of a **`docker-compose.yml`** file
- 📝 Use a Linux CLI text editor (`nano`) to create configuration files
- 🚀 Deploy a **multi-container application** using Docker Compose
- 📚 Document deployment procedures and IaC principles using Markdown

---

## 💻 Commands Executed

| ⚙️ Command | 📋 Purpose |
|---|---|
| `mkdir nextcloud-deployment` | Created a new project directory for the infrastructure code. |
| `nano docker-compose.yml` | Opened the CLI text editor to write the Infrastructure as Code blueprint. |
| `docker-compose up -d` | Read the YAML file and deployed the database and app containers in the background. |
| `docker-compose ps` | Verified that both containers were running and healthy. |
| `docker-compose down` | Gracefully stopped and removed the containers and the internal network. |

---

## 🎓 Skills Learned
- 🧠 Understanding **multi-tier architecture** (separating the frontend app from the backend database)
- ✍️ Writing valid **YAML files** and understanding strict indentation rules (spaces vs. tabs)
- 🐳 Managing **multi-container environments** with Docker Compose
- 🌐 Using Docker's internal networking to allow containers to communicate via service names (`MYSQL_HOST=database`)
- 🔐 Using **environment variables** to pass sensitive data (like database passwords) to containers securely
- 🛠️ Documenting Infrastructure as Code (IaC) for other engineers
