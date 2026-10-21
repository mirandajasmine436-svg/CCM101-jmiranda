# 🛠️ Backup Script Guide


## 📜 The `backup.sh` Script Code
    #!/bin/bash
    # Automated Backup Script for CloudNova Technologies

    SOURCE_DIR="app-data"
    BACKUP_DIR="backups"
    TIMESTAMP=$(date +%Y%m%d_%H%M%S)

    echo "Initiating automated backup..."

    # Create the backup directory if it does not exist
    mkdir -p $BACKUP_DIR

    # Compress the source directory into a tarball (.tar.gz)
    tar -czf $BACKUP_DIR/backup_$TIMESTAMP.tar.gz $SOURCE_DIR

    echo "Backup completed successfully at $TIMESTAMP!"

## 🔑 Permissions: What did `chmod +x` do?
The `chmod +x backup.sh` command tells the Linux operating system to make the script executable. By default, Linux prevents text files from running as programs for security reasons. The `+x` flag adds the "execute" permission, allowing the user to run the file using `./backup.sh`.

## ⏰ Cron Expression Breakdown
The cron expression used is: `0 2 * * * /root/backup.sh`

Here is what each of the five time fields means:
1. **Minute (0):** Run at the 0th minute.
2. **Hour (2):** Run at the 2nd hour (2:00 AM).
3. **Day of Month (*):** Run every day of the month.
4. **Month (*):** Run every month.
5. **Day of Week (*):** Run every day of the week.

*(Result: This tells the system to run the backup script every single night at exactly 2:00 AM).*
