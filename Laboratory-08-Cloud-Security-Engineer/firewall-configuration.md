# 🛡️ Firewall Configuration


## 🎯 Objective
Secure an exposed Ubuntu server using UFW (Uncomplicated Firewall) by enforcing a Default Deny inbound policy while allowing only the services required by the client (SSH for administration and TCP/8080 for the web application).

## 💻 Commands Executed

### 1. 🔑 Allow SSH (do this FIRST)
    sudo ufw allow ssh

Permits inbound TCP/22 so administrators can continue to manage the server remotely.

### 2. 🚫 Set Default Deny Policy
    sudo ufw default deny incoming
    sudo ufw default allow outgoing

Blocks all unsolicited inbound traffic while allowing the server to initiate outbound connections (updates, DNS, API calls).

### 3. ⚡ Enable the Firewall
    sudo ufw enable

Activates the firewall and applies the rules immediately (pressing 'y' when prompted).

### 4. 🌐 Allow the Web Application Port
    sudo ufw allow 8080/tcp

Explicitly opens TCP/8080 so legitimate users can reach the Nginx web application.

### 5. 🔍 Verification
    sudo ufw status verbose
    sudo ufw status numbered

Checks the active rules and displays them in a numbered list to confirm the configuration.

## ⚠️ Critical Order-of-Operations Note

**What would happen if you ran `sudo ufw enable` before `sudo ufw allow ssh`?**

Enabling UFW with a Default Deny policy before permitting SSH would immediately block port 22, instantly severing your active remote SSH connection and locking you out of the server permanently, requiring out-of-band console access to fix.

## 📋 Final Rule Set

| Rule | Port | Protocol | Action | Purpose |
|------|------|----------|--------|---------|
| 1 | 22 | TCP | ALLOW IN | SSH administration |
| 2 | 8080 | TCP | ALLOW IN | Web application |
| — | * | * | DENY IN | Default (block all other traffic) |
| — | * | * | ALLOW OUT | Outbound (server-initiated) |
