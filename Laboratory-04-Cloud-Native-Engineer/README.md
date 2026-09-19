# 🐳 Laboratory 04 – Cloud-Native Engineer

## 📌 Mission Overview

Congratulations! After successfully guiding our clients through multi-cloud evaluations, you have been promoted to the Cloud-Native Engineering Team at CloudNova Technologies.
Modern cloud computing is no longer just about renting Virtual Machines (VMs) from AWS or Azure. Today's enterprise applications are built using lightweight, portable, and lightning-fast technologies called **Containers**.
Your new mission is to understand the shift from traditional virtualization to containerization. Using the KillerCoda Playground, you will step into the shoes of a Cloud-Native Engineer. You will research the differences between VMs and containers, execute your first Docker commands, and deploy a live, containerized web server in seconds.

## 🎯 Objectives

At the end of this laboratory activity, you should be able to:

- Differentiate between traditional Virtual Machines (VMs) and Containers.
- Access a Docker-enabled cloud environment using KillerCoda.
- Execute fundamental Docker CLI (Command Line Interface) commands.
- Pull, run, manage, and terminate a containerized application (Nginx).
- Create professional technical documentation of container operations using Markdown.
- Continue developing a well-organized GitHub Cloud Computing Portfolio.

## 🐳 Docker Commands Executed

### Checkpoint 3 – Verify Docker

**Check Docker version:**

```bash
docker --version
```

This command checks whether Docker is installed and displays its version.

**Check Docker environment:**

```bash
docker info
```

This command displays detailed information about the Docker environment.

**List running containers:**

```bash
docker ps
```

This command displays the containers that are currently running.

### Checkpoint 4 – Deploy Nginx

**Pull the Nginx image:**

```bash
docker pull nginx
```

This command downloads the official Nginx image from Docker Hub.

**Run the Nginx container:**

```bash
docker run -d --name nginx-server -p 8080:80 nginx
```

This command runs the Nginx container in detached mode and maps port 8080 on the host to port 80 inside the container.

**Test the Nginx web server:**

```bash
curl http://localhost:8080
```

This command sends an HTTP request to the Nginx server and displays the HTML response in the terminal.

### Checkpoint 5 – Container Lifecycle

**List running containers:**

```bash
docker ps
```

This command lists the containers that are currently running.

**Stop the Nginx container:**

```bash
docker stop nginx-server
```

This command stops the running Nginx container.

**Verify the container is stopped:**

```bash
docker ps
```

This command verifies that the Nginx container is no longer running.

**List all containers:**

```bash
docker ps -a
```

This command displays all containers, including stopped containers.

**Remove the container:**

```bash
docker rm nginx-server
```

This command removes the stopped Nginx container completely.

## 🧠 Skills Learned

- Understanding Virtual Machines and containers
- Using the Docker CLI
- Pulling Docker images from Docker Hub
- Running and managing containers
- Port mapping
- Testing a web server using `curl`
- Managing the Docker container lifecycle
- Using Linux terminal commands
- Creating technical documentation using Markdown
- Organizing and updating a GitHub portfolio

## 🛠️ Challenges Encountered

One challenge I encountered was understanding the difference between a Docker image and a running container. I also had to understand how port mapping works when connecting port 8080 on the host to port 80 inside the Nginx container. Another challenge was remembering the correct commands for stopping and removing the container. After practicing the commands and observing the terminal output, I became more comfortable using Docker and managing containers.
