# 🔬 Automation Research


## 1. 💻 Bash Script
A Bash script is a plain text file containing a series of commands that the Linux shell executes sequentially. The `#!/bin/bash` line at the top (called the "shebang") tells the operating system exactly which interpreter to use to run the file, ensuring the script runs properly in the Bash environment rather than another shell.

## 2. 📦 Variables
Programmers use variables (like `$BACKUP_DIR`) to store data that might change, making scripts dynamic and reusable. Instead of typing the exact folder path over and over (which is prone to typos and hard to update), you define it once in a variable. If the path ever changes, you only have to update it in one place.

## 3. ⏰ Cron Job
A cron job is a time-based job scheduler in Linux that runs commands or scripts automatically at specified intervals. It is essential for cloud operations because it eliminates the need for human intervention, allowing system administrators to automate repetitive tasks like backups, log rotations, and system updates reliably 24/7.
