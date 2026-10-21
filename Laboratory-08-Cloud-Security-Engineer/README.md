# ☁️ Laboratory-08-Cloud-Security-Engineer

## 📖 Mission Overview
Congratulations! Your proactive approach to system monitoring has earned you a spot on the elite
Cloud Security Team at CloudNova Technologies.
In the cloud, leaving a server unsecured for even a few minutes can lead to automated brute-force
attacks and data breaches. Your mission today applies the security concepts you learned in Chapter 8. You will
implement the principle of defense in depth by locking down a live server using a host-based firewall. 

## 🎯 Objectives
- 🧠 Understand the Attack Surface and the Principle of Least Privilege (PoLP).
- 🔍 Perform a basic security audit of active network ports on a Linux server.
- 🛡️ Configure UFW with a Default Deny policy.
- 🔑 Implement granular port management for SSH and HTTP/8080.
- 📝 Document firewall rules and security best practices in Markdown.


## 💻 Commands Executed
    # Deploy the vulnerable web app
    docker run -d --name secure-web-app -p 8080:80 nginx
    curl http://localhost:8080

    # Configure UFW
    sudo ufw allow ssh
    sudo ufw default deny incoming
    sudo ufw default allow outgoing
    sudo ufw enable

    # Add the web app rule and verify
    sudo ufw allow 8080/tcp
    sudo ufw status verbose
    sudo ufw status numbered

    # Re-verify the app is reachable
    curl http://localhost:8080

## 🧠 Skills Learned
- 🛡️ Host-based firewall configuration with UFW on Ubuntu.
- 🚫 Applying the Default Deny security principle.
- 🔒 Enforcing the Principle of Least Privilege at the network layer.
- ⚠️ Safe order-of-operations when enabling a firewall (SSH-first).
- 📝 Security documentation and evidence collection.
- 📉 Reducing a server's attack surface through granular port control.
