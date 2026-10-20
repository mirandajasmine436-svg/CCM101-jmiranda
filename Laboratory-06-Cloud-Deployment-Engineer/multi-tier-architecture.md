# 🏗️ Multi-Tier Architecture

## 📖 Overview
A multi-tier architecture is a software design pattern that separates an application into logical layers (or "tiers"). Each tier has a distinct responsibility and runs independently, communicating with the others over a network. In this mission, we deployed a **Two-Tier Architecture** consisting of a Web/Application Tier and a Database Tier.

---

## 🌐 1. The Web/Application Tier

| 🏷️ Property | 📋 Description |
|---|---|
| **Role** | The frontend layer that users interact with directly. It serves the user interface, handles HTTP requests from the browser, and processes the core application logic. |
| **In Our Deployment** | The **Nextcloud** container |
| **Key Responsibilities** | Rendering the web UI, managing user sessions, handling file uploads/downloads, and communicating with the database to fetch or store data. |

---

## 🗄️ 2. The Database Tier

| 🏷️ Property | 📋 Description |
|---|---|
| **Role** | The backend layer responsible for storing and managing persistent data. It holds user credentials, application configurations, and file metadata securely. |
| **In Our Deployment** | The **MariaDB** container |
| **Key Responsibilities** | Storing user accounts, passwords, file metadata, sharing permissions, and any other data that must survive a container restart. |

---

## ❓ 3. Why Separate Them?

Separating the web server and the database into two different containers is a best practice because it provides better **security, scalability, and maintenance**. If an attacker somehow compromises the Nextcloud web container, the MariaDB database container remains isolated and protected, keeping sensitive user data safe. From a scalability standpoint, separating them means the web tier can be scaled up or down independently of the database tier, depending on how much traffic the app is receiving. Finally, maintenance becomes much easier because the application can be updated, restarted, or replaced entirely without ever touching the database, which significantly reduces the risk of downtime or data loss.

---

## 🔗 4. How They Communicate

In our Docker Compose deployment, the two tiers communicate over a private Docker network automatically created by Compose.

- The Nextcloud container is configured with `MYSQL_HOST=database`
- Docker's built-in DNS resolves the hostname `database` to the MariaDB container's IP address
- Nextcloud then connects to MariaDB using the credentials defined in the environment variables

This means the two containers can talk to each other **without ever being exposed to the public internet** — only port 8080 (the web UI) is accessible from the outside.

---

## 🎯 5. Summary

| Tier | Container | Exposed Port | Publicly Accessible? |
|---|---|:---:|:---:|
| 🌐 Web/Application | Nextcloud | 8080 | ✅ Yes |
| 🗄️ Database | MariaDB | (none) | ❌ No |

The separation of tiers ensures that even if the web-facing application is compromised, the sensitive database layer remains protected.
