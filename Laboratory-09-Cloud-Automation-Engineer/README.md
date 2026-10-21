# ☁️ Laboratory-09-Cloud-Automation-Engineer

## 📖 Mission Overview
Congratulations! Your ability to secure cloud environments has proven you are ready for the highest
level of operations. You have been promoted to the Cloud Automation and DevOps Team at CloudNova
Technologies.
Up until now, you have been acting as a traditional systems administrator typing commands manually
one by one. In large enterprise environments scaling to thousands of servers, manual administration is too slow
and highly prone to human error. To survive at scale, you must learn to automate. 

## 🎯 Objectives
- 🧠 Understand the fundamental syntax of a Bash shell script, including variables and basic commands.
- ✍️ Use a command-line text editor (`nano`) to write and save executable scripts.
- 🔒 Modify Linux file permissions using the `chmod` command.
- ⏰ Understand task scheduling and the syntax of a Linux crontab.
- 📝 Document automation code and Cron job configurations using Markdown.
- 🏆 Complete the final chapter of the GitHub Cloud Computing Portfolio.

## 💻 Commands Executed
    # Create dummy data
    mkdir app-data
    echo "This is critical client data." > app-data/data.txt

    # Create and edit the script
    nano backup.sh

    # Set permissions and execute
    chmod +x backup.sh
    ./backup.sh

    # Verify the backup
    ls -l backups/

    # Schedule the cron job
    env EDITOR=nano crontab -e
    crontab -l

## 🧠 Skills Learned
- ✍️ Bash Shell Scripting (Variables, Shebang, Commands).
- 🔒 Linux File Permissions (`chmod +x`).
- 📦 Data Compression and Archiving (`tar -czf`).
- ⏰ Task Automation and Scheduling with `cron`.
- 🤖 Eliminating human error through automation.
- 📝 Technical documentation of code and schedules.
