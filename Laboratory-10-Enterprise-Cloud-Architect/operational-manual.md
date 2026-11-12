# 📘 CloudNova – Operational Manual

## 📌 1. Introduction

This manual explains how to set up, run, secure, and maintain CloudNova.

CloudNova is a website hosted on Ubuntu Server inside Oracle VirtualBox. It uses Docker to run WordPress and MariaDB.

This guide contains the commands and instructions needed to manage the server, check the application, protect access, and create database backups.

## 💻 2. System Requirements

### 🖥️ Host Machine

- Windows 11
- Oracle VirtualBox
- SSH client
- Web browser
- Internet connection

### 🐧 Virtual Machine

- Ubuntu Server 26.04.1 LTS
- 35 GB dynamically allocated virtual disk
- Docker Engine
- Docker Compose
- UFW Firewall
- OpenSSH Server

### 🧰 Application Components

- WordPress
- MariaDB 11.4
- Docker network
- Docker storage volumes

## 🏗️ 3. Server and Network Setup

### 3.1 Virtual Machine Information

The Ubuntu Server runs inside Oracle VirtualBox.

| Configuration | Value |
|---|---|
| Server Name | `cloudnova-server` |
| Linux User | `cloudnova` |
| Operating System | Ubuntu Server 26.04.1 LTS |
| Virtualization Software | Oracle VirtualBox |
| Virtual Disk | 35 GB |

### 3.2 Network Configuration

The server uses two network connections.

| Interface | IP Address | Purpose |
|---|---|---|
| `enp0s3` | `10.0.2.15` | Internet access |
| `enp0s8` | `192.168.56.103` | Laptop-to-server connection |

The Windows laptop uses `192.168.56.1` for its Host-only network connection.

### 3.3 Connecting to the Server

Open Windows PowerShell and run:

```powershell
ssh -i "$env:USERPROFILE\.ssh\cloudnova_ed25519" cloudnova@192.168.56.103
```

Enter your SSH key passphrase if requested.

To open the WordPress website, enter this address in your browser:

```text
http://192.168.56.103:8080
```

## 🐳 4. Running the Docker Application

### 4.1 Checking Docker Installation

Check the Docker version:

```bash
sudo docker --version
```

Check the Docker Compose version:

```bash
sudo docker compose version
```

### 4.2 Project Location

The CloudNova project is stored in:

```text
/opt/cloudnova/
```

The deployed configuration file is named `compose.yaml`. Its GitHub copy is named `docker-compose.yml`.

### 4.3 Application Containers

CloudNova has two main containers.

**WordPress**

- Container name: `cloudnova-wordpress`
- Image: `wordpress:latest`
- Website address: `192.168.56.103:8080`
- Storage: `wordpress_data`

**MariaDB**

- Container name: `cloudnova-database`
- Image: `mariadb:11.4`
- Database settings: stored in `.env`
- Storage: `mariadb_data`
- Access: Internal Docker network only

### 4.4 Starting the Application

Connect to Ubuntu Server and run:

```bash
cd /opt/cloudnova
sudo docker compose up -d
```

Check whether the containers are running:

```bash
sudo docker ps
```

Check the application services:

```bash
sudo docker compose ps
```

### 4.5 Stopping and Restarting the Application

Stop the application:

```bash
cd /opt/cloudnova
sudo docker compose stop
```

Start the application again:

```bash
sudo docker compose start
```

Restart the containers:

```bash
sudo docker compose restart
```

Remove the containers and network without deleting the stored data:

```bash
sudo docker compose down
```

**⚠️ Important:** Avoid using `docker compose down -v` unless you intentionally want to delete the stored data inside the Docker volumes.

### 4.6 Checking Application Logs

WordPress logs:

```bash
sudo docker logs cloudnova-wordpress
```

MariaDB logs:

```bash
sudo docker logs cloudnova-database
```

View the logs continuously:

```bash
sudo docker compose logs -f
```

## 💾 5. Data Storage

CloudNova uses Docker volumes to keep website and database files even when containers are restarted or recreated.

| Volume | Storage Location | Purpose |
|---|---|---|
| `wordpress_data` | `/var/www/html` | Stores WordPress files |
| `mariadb_data` | `/var/lib/mysql` | Stores database files |

List the available volumes:

```bash
sudo docker volume ls
```

Check the MariaDB volume:

```bash
sudo docker volume inspect mariadb_data
```

These volumes help prevent data loss when containers are stopped or recreated. However, they are not a replacement for separate database backups.

## 🔒 6. Security Configuration

### 6.1 UFW Firewall

The Ubuntu firewall blocks incoming connections by default.

Set the firewall rules:

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

Allow SSH access from the Host-only network:

```bash
sudo ufw allow from 192.168.56.0/24 to any port 22 proto tcp
```

Enable the firewall:

```bash
sudo ufw enable
```

Check the firewall:

```bash
sudo ufw status verbose
```

The WordPress port is controlled separately using Docker firewall rules because Docker-published ports can bypass normal UFW filtering.

### 6.2 SSH Security

SSH is configured to use a private and public key pair instead of password login.

The server security settings include:

```text
PermitRootLogin no
PubkeyAuthentication yes
PasswordAuthentication no
KbdInteractiveAuthentication no
MaxAuthTries 3
X11Forwarding no
AllowUsers cloudnova
```

Configuration file:

```text
/etc/ssh/sshd_config.d/99-security.conf
```

Check whether the SSH configuration is valid:

```bash
sudo sshd -t
```

View the active SSH settings:

```bash
sudo sshd -T
```

Reload SSH after making configuration changes:

```bash
sudo systemctl reload ssh
```

**⚠️ Important:** Keep your current SSH session open while testing new SSH settings. This helps prevent losing access to the server if a configuration is incorrect.

### 6.3 Docker Firewall Rules

Docker has its own firewall rules to control access to the WordPress website.

The current configuration:

1. Allows existing connections to continue.
2. Allows the Windows host (`192.168.56.1`) to access WordPress through the Host-only interface.
3. Blocks other traffic targeting the published WordPress port.

Check the rules:

```bash
sudo iptables -S DOCKER-USER
```

The firewall script is located at:

```text
/usr/local/sbin/cloudnova-docker-firewall.sh
```

The service configuration is located at:

```text
/etc/systemd/system/cloudnova-docker-firewall.service
```

Check the service:

```bash
sudo systemctl status cloudnova-docker-firewall
```

### 6.4 Protecting Database Passwords

Database credentials are stored in:

```text
/opt/cloudnova/.env
```

Check the file permissions:

```bash
sudo ls -l /opt/cloudnova/.env
```

**⚠️ Security reminders:**

- Never upload `.env` to GitHub.
- Never share database passwords publicly.
- Do not expose MariaDB port 3306 to the host network.
- Keep the `.env` file protected.

WordPress connects to MariaDB through the internal Docker network using the service name `database`.

## ⚙️ 7. Automatic Database Backup

### 7.1 Backup Script

The backup script is stored on the server at:

```text
/usr/local/sbin/cloudnova-db-backup.sh
```

The copy uploaded to GitHub is:

```text
automation-script.sh
```

The script performs these tasks:

1. Reads the database settings from `.env`.
2. Checks whether MariaDB is running.
3. Creates a database backup.
4. Compresses the backup using Gzip.
5. Checks whether the backup file is valid.
6. Saves the backup with a date and time in its filename.
7. Deletes backup files older than seven days.

### 7.2 Backup Location

All backup files are stored in:

```text
/opt/cloudnova/backups/
```

Check the backup files:

```bash
sudo ls -lh /opt/cloudnova/backups/
```

### 7.3 Creating a Manual Backup

Run:

```bash
sudo /usr/local/sbin/cloudnova-db-backup.sh
```

A successful backup displays:

```text
SUCCESS: Database backup created.
File: /opt/cloudnova/backups/...
Size: ...
```

### 7.4 Checking Backup Files

Run:

```bash
sudo bash -c 'gzip -t "$(ls -t /opt/cloudnova/backups/*.sql.gz | head -n 1)" && echo "Backup archive is valid."'
```

If the message says `Backup archive is valid.`, the compressed file passed the integrity check.

### 7.5 Automatic Backup Schedule

The backup runs every day at 2:00 AM UTC, equivalent to 10:00 AM Philippine Time.

The schedule is configured through the root user's Cron settings.

Open the Cron configuration:

```bash
sudo crontab -e
```

The scheduled command is:

```cron
0 2 * * * /usr/local/sbin/cloudnova-db-backup.sh >> /var/log/cloudnova-backup.log 2>&1
```

### 7.6 Checking the Scheduled Task

Display the scheduled task:

```bash
sudo crontab -l
```

Check whether Cron is running:

```bash
sudo systemctl status cron
```

### 7.7 Checking Backup Logs

The backup log is stored at:

```text
/var/log/cloudnova-backup.log
```

View the log:

```bash
sudo cat /var/log/cloudnova-backup.log
```

View the latest log entries:

```bash
sudo tail -n 50 /var/log/cloudnova-backup.log
```

## ♻️ 8. Restoring a Database Backup

A compressed SQL backup can be used to restore the MariaDB database.

**⚠️ Warning:** Restoring a backup can replace current database contents. Make a separate copy of the current database before proceeding.

First, load the database settings:

```bash
cd /opt/cloudnova

set -a
source .env
set +a
```

Set the backup filename:

```bash
BACKUP_FILE="/opt/cloudnova/backups/your_backup_filename.sql.gz"
```

Replace `your_backup_filename.sql.gz` with the actual backup filename.

Restore the database:

```bash
sudo bash -c 'gunzip -c "$1" | docker exec -i -e MYSQL_PWD="$2" cloudnova-database mariadb -u root "$3"' _ "$BACKUP_FILE" "$DB_ROOT_PASSWORD" "$DB_NAME"
```

Check the MariaDB logs:

```bash
sudo docker logs --tail 50 cloudnova-database
```

## 🔧 9. Maintenance and Troubleshooting

The following commands can help check the server and fix common problems.

### 9.1 Check Running Containers

```bash
sudo docker ps -a
```

### 9.2 Restart Docker

```bash
sudo systemctl restart docker
```

### 9.3 Check Available Disk Space

```bash
df -h
```

### 9.4 Check Memory Usage

```bash
free -h
```

### 9.5 Check Network Settings

```bash
ip addr
ip route
```

### 9.6 Check Firewall Rules

```bash
sudo ufw status verbose
sudo iptables -S DOCKER-USER
```

### 9.7 Check Docker Firewall Service

```bash
sudo systemctl status cloudnova-docker-firewall
```

### 9.8 Check Backup Logs

```bash
sudo tail -n 50 /var/log/cloudnova-backup.log
```

### 9.9 Common Problems

| Problem | Possible Cause | Solution |
|---|---|---|
| WordPress cannot be accessed | Container is stopped or network is not working | Check container status and network settings |
| WordPress cannot connect to MariaDB | Database is not running or is not healthy | Check MariaDB status and logs |
| SSH connection is denied | Wrong key or incorrect SSH settings | Check the SSH key and server configuration |
| Backup script fails | Database is unavailable or settings are missing | Check MariaDB and `.env` |
| Server storage is full | Too many files or backups | Check disk usage and old backup files |
| Website cannot be accessed from Windows | Incorrect firewall rules or Host-only network settings | Check the Docker firewall rules and network interfaces |

## 📋 10. Important Maintenance Reminders

- Keep database passwords private.
- Never upload `.env` to GitHub.
- Keep MariaDB accessible only through the internal Docker network.
- Do not disable firewall rules without understanding their purpose.
- Check backup files regularly.
- Keep another copy of important backups outside the virtual machine.
- Avoid deleting Docker volumes without checking their contents.
- Check available disk space regularly.
- Review application updates before applying them.

## 📝 11. Conclusion

This manual contains the main instructions for managing CloudNova. Following these procedures helps keep the website running, protects server access, preserves important data, and ensures that database backups are created regularly.
