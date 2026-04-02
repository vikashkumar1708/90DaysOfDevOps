# Day 19 – Shell Scripting Project: Log Rotation, Backup & Crontab

##  Objective
Apply shell scripting concepts in real-world scenarios:
- Log rotation
- Automated backups
- Scheduling using cron
- Combining everything into one maintenance script

---

## Task 1: Log Rotation Script

### Script: `log_rotate.sh`

```bash
#!/bin/bash
set -euo pipefail

# Check arguments
if [ $# -eq 0 ]; then
    echo "Usage: $0 <path of directory>"
    exit 1
fi

# Check directory exists
if [ ! -d "$1" ]; then
    echo "Error: Directory $1 not available"
    exit 1
fi

LOG_DIR="$1"

compress_log_file() {
    count=$(find "$LOG_DIR" -type f -name "*.log" -mtime +7 | wc -l)

    if [ "$count" -eq 0 ]; then
        echo "No .log files older than 7 days found."
    else
        find "$LOG_DIR" -type f -name "*.log" -mtime +7 -exec gzip {} \;
        echo "$count file(s) compressed."
    fi
}

delete_file() {
    count=$(find "$LOG_DIR" -type f -name "*.gz" -mtime +30 | wc -l)

    if [ "$count" -eq 0 ]; then
        echo "No .gz files older than 30 days found."
    else
        find "$LOG_DIR" -type f -name "*.gz" -mtime +30 -exec rm -f {} \;
        echo "$count .gz file(s) deleted."
    fi
}

compress_log_file
delete_file'
```
## Task 2: Server Backup Script
### Script: 'backup.sh'
```bash
#!/bin/bash
set -euo pipefail

display_usage() {
    echo "Usage: ./backup.sh <source_path> <backup_path>"
}

if [ $# -eq 0 ]; then
    display_usage
    exit 1
fi

source_path=$1
backup_path=$2
timestamp=$(date +%Y-%m-%d_%H-%M-%S)

# Validate source
if [ ! -d "$source_path" ]; then
    echo "Error: Source directory does not exist!"
    exit 1
fi

create_backup() {
    tar -czf "${backup_path}/backup-${timestamp}.tar.gz" "$source_path"
    echo "Backup created successfully"
}

size_name_backupfile() {
    backup_file="${backup_path}/backup-${timestamp}.tar.gz"

    if [ -f "$backup_file" ]; then
        echo "Backup file name: $(basename "$backup_file")"
        echo "Backup file size: $(du -h "$backup_file" | cut -f1)"
    fi
}

delete_14dayafter() {
    count=$(find "$backup_path" -type f -name "*.tar.gz" -mtime +14 | wc -l)

    if [ "$count" -eq 0 ]; then
        echo "No backups older than 14 days"
    else
        find "$backup_path" -type f -name "*.tar.gz" -mtime +14 -exec rm -f {} \;
        echo "$count old backup(s) deleted"
    fi
}

create_backup
size_name_backupfile
delete_14dayafter
```
## Task 3: Crontab Entries
# Run log rotation daily at 2 AM
0 2 * * * /path/to/log_rotate.sh /var/log/myapp

# Run backup every Sunday at 3 AM
0 3 * * 0 /path/to/backup.sh /source /backup

# Run health check every 5 minutes
*/5 * * * * /path/to/health_check.sh

## Task 4: Maintenance Script
### Script: 'maintenance.sh'
```bash
#!/bin/bash
set -euo pipefail

LOG_FILE="/home/ubuntu/day19/maintenance.log"
SOURCE_DIR="/home/ubuntu/day19/source_dir"
BACKUP_DIR="/home/ubuntu/day19/backup_dir"
DAY19_DIR="/home/ubuntu/day19"

log_message() {
    echo "$(date '+%Y-%m-%d %H:%M:%S') - $1"
}

{
    echo "===== Maintenance Started ====="

    log_message "Running log rotation..."
    ./log_rotate.sh "$DAY19_DIR"

    log_message "Running backup..."
    ./backup.sh "$SOURCE_DIR" "$BACKUP_DIR"

    echo "===== Maintenance Completed ====="
} >> "$LOG_FILE" 2>&1
```



