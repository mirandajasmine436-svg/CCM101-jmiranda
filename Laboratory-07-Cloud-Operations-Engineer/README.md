# 🧪 Laboratory 07 — Cloud Operations Engineer

## 📖 Mission Overview
Congratulations! Your ability to deploy multi-tier architectures has proven your technical capabilities. You have now been promoted to the Cloud Operations Team (often referred to in the industry as Site Reliability Engineering, or SRE) at CloudNova Technologies.

Deploying a cloud application is only the first step; keeping it running smoothly is the real challenge. When a server crashes or a web page takes ten seconds to load, you cannot simply guess what is wrong. You must rely on Observability and Monitoring to see inside your infrastructure.

In this mission, I stepped into the role of a Cloud Operations Engineer. I established a performance baseline for a Linux server, deployed a containerized application, generated artificial web traffic, and hunted down performance metrics and system logs to prove the application is healthy.

## 🎯 Objectives
- 📊 Utilize native Linux CLI tools to monitor host CPU, Memory, and Disk.
- 🐳 Deploy a web container and track its performance using Docker metrics.
- 📜 Generate web traffic and extract application access logs.
- 📝 Translate raw performance data into a readable technical report.

## 💻 Monitoring Commands Executed

| ⚙️ Command | 📋 Purpose |
|---|---|
| `free -h` | Checked the host server's total and available RAM. |
| `df -h /` | Checked the host server's total and available disk space. |
| `top` | Viewed active processes and real-time CPU load. |
| `docker run -d -p 8080:80 --name client-website nginx` | Deployed the Nginx web server container. |
| `curl http://localhost:8080` | Generated successful HTTP traffic (200 OK). |
| `curl http://localhost:8080/hidden-admin-page` | Simulated a user accessing a missing page (404 Not Found). |
| `docker logs client-website` | Extracted application logs to find the 404 error. |
| `docker stats` | Monitored live CPU and Memory metrics of the container. |

## 🎓 Skills Learned
- 🩺 Establishing a baseline health check for a Linux server.
- 🐳 Deploying web applications via Docker.
- 🔍 Using `curl` to simulate user traffic and generate errors.
- 📜 Analyzing container logs to troubleshoot HTTP status codes.
- 📈 Reading real-time metrics (`docker stats`) to ensure resource efficiency.
