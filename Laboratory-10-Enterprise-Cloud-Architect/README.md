# ☁️ Enterprise Cloud Architect

## 📌 Project Overview

**CloudNova** is a cloud infrastructure project developed for CCM101 – Cloud Computing. It demonstrates how to build, manage, and secure a web application using a virtual machine and Docker.

The project uses Ubuntu Server to run two connected services: WordPress and MariaDB. WordPress handles the website, while MariaDB stores its data.

The system also includes firewall protection, secure remote access, permanent data storage, and automatic database backups.

## 🎯 Project Objectives

- Set up a Linux server using Oracle VirtualBox.
- Configure network connections between the laptop and the virtual machine.
- Install Docker and Docker Compose.
- Deploy WordPress and MariaDB as connected services.
- Set up storage to keep application and database data safe.
- Protect the server using firewall rules and secure SSH access.
- Create a Bash script for automatic database backups.
- Schedule backups using Cron.
- Document the setup and maintenance procedures.

## 🏗️ System Architecture

CloudNova uses the following setup:

1. **Host Machine:** Windows 11 laptop used to manage and access the server.
2. **VirtualBox:** Runs the Ubuntu Server virtual machine.
3. **Ubuntu Server:** Hosts Docker and the application.
4. **Network:** NAT provides internet access, while Host-only networking connects the laptop to the server.
5. **Firewall:** UFW and Docker firewall rules control incoming connections.
6. **Docker:** Runs and manages the application containers.
7. **WordPress:** Provides the website.
8. **MariaDB:** Stores the website's data.
9. **Storage:** Docker volumes keep application and database files even when containers restart.
10. **Backup Automation:** Bash and Cron create database backups automatically.

See [`architecture-diagram.png`](architecture-diagram.png) for the complete system diagram.

## 🛠️ Technologies Used

| Component | Technology |
|---|---|
| Host Operating System | Windows 11 |
| Virtualization Software | Oracle VirtualBox |
| Server Operating System | Ubuntu Server 26.04.1 LTS |
| Container Platform | Docker Engine 29.9.2 |
| Container Management | Docker Compose 5.6.1 |
| Website | WordPress |
| Database | MariaDB 11.4 |
| Firewall | UFW and iptables |
| Automation | Bash and Cron |
| Remote Access | OpenSSH |
| SSH Authentication | ED25519 Key |

## 🌐 Network Configuration

| Interface | IP Address | Purpose |
|---|---|---|
| NAT (`enp0s3`) | `10.0.2.15/24` | Internet access |
| Host-only (`enp0s8`) | `192.168.56.103/24` | Connection between laptop and server |
| Windows Host-only Adapter | `192.168.56.1` | Laptop connection to the server |
| WordPress | `192.168.56.103:8080` | Website access |

**🌍 WordPress Website:**

`http://192.168.56.103:8080`

## 🐳 Docker Services

CloudNova runs two connected containers:

| Container | Image | Purpose |
|---|---|---|
| `cloudnova-wordpress` | `wordpress:latest` | Runs the website |
| `cloudnova-database` | `mariadb:11.4` | Stores website data |

Both containers communicate through the `cloudnova-network` Docker network.

**💾 Stored Data:**

- `wordpress_data` – keeps WordPress files.
- `mariadb_data` – keeps MariaDB database files.

The MariaDB database port is not directly exposed to the host network.

## 🔒 Security Features

The following security settings were applied:

- UFW is enabled with a default rule that blocks incoming connections.
- Outgoing connections are allowed.
- SSH access is restricted to the Host-only network.
- SSH password login is disabled.
- Root login through SSH is disabled.
- SSH public-key authentication is enabled.
- Docker firewall rules restrict website access to the Windows host.
- MariaDB is only accessible through the internal Docker network.
- Database passwords are stored in a protected `.env` file and are not included in the GitHub repository.

## ⚙️ Backup Automation

CloudNova uses a custom Bash script to create automatic MariaDB backups.

**Script:** `automation-script.sh`

**Backup Location:** `/opt/cloudnova/backups/`

**Schedule:** Every day at 2:00 AM UTC (10:00 AM Philippine Time).

The script performs the following tasks:

- Creates a copy of the MariaDB database.
- Compresses the backup using Gzip.
- Adds a date and time to each backup filename.
- Checks whether the backup file is valid.
- Keeps backups for seven days.
- Records backup results in a log file.

## 📂 GitHub Repository Structure

```text
Laboratory-10-Enterprise-Cloud-Architect/
├── README.md
├── architecture-diagram.png
├── docker-compose.yml
├── automation-script.sh
├── operational-manual.md
└── final-reflection.md
```
Ready to spin up CloudNova? Follow these quick steps on your Ubuntu Server:

| Step | Action | Command / URL |
| :--- | :--- | :--- |
| **1. Navigate** | Open the project directory | `cd /opt/cloudnova` |
| **2. Launch** | Start the containers in detached mode | `sudo docker compose up -d` |
| **3. Verify** | Check that the containers are running | `sudo docker ps` |
| **4. Monitor** | View real-time application logs | `sudo docker compose logs` |

🌐 **Access the Website:** Open your browser and go to `http://192.168.56.103:8080`

> 💡 **Need more details?** For full setup, security, backup, and maintenance instructions, please refer to the **[Operational Manual](operational-manual.md)**.

---

## 📦 Project Deliverables

Here is what you will find inside this repository:

- [ ] 🖼️ **`architecture-diagram.png`** — A visual map of the server setup and network connections.
- [ ] 🐳 **`docker-compose.yml`** — The configuration file for deploying WordPress and MariaDB.
- [ ] 🤖 **`automation-script.sh`** — The Bash script used to create automated database backups.
- [ ] 📖 **`operational-manual.md`** — The complete guide for managing and maintaining the system.
- [ ] 📝 **`final-reflection.md`** — A written summary of the lessons learned throughout CCM101.

---

## 📝 Conclusion

**CloudNova** proves that complex infrastructure can be managed efficiently. By combining virtualization, Docker, secure networking, persistent storage, and automated backups, this project delivers a fully functional, secure, and resilient web application environment.
