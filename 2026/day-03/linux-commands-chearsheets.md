# 🐧 Linux Commands Cheat Sheet (Beginner → Practical)

---

## 🔹 Process Management (Debug running apps)

- `whoami` – Check current user (useful in permission issues).
- `uptime` – Check system load & uptime.
- `ps aux` – View all running processes.
- `ps -ef` – Detailed process list (parent-child relation).
- `pgrep <name>` – Get PID of a process (quick lookup).
- `pkill <name>` – Kill process by name.
- `kill <PID>` – Gracefully stop a process.
- `kill -9 <PID>` – Force kill (when stuck).
- `top` – Live CPU & memory usage.
- `htop` – Better interactive process monitor.
- `nice -n 10 <cmd>` – Start low-priority process.
- `renice -n 5 <PID>` – Change running process priority.
- `uname -a` – System/kernel details.

💡 Tip: Use `top` + `kill` together to quickly fix high CPU issues.

---

## 🔹 File System (Navigate & manage files)

- `pwd` – Show current directory.
- `ls -lh` – List files with size (most used).
- `ls -a` – Show hidden files.
- `tree` – Visualize folder structure.
- `cd <dir>` – Change directory.
- `mkdir <dir>` – Create directory.
- `rm <file>` – Delete file.
- `rm -rf <dir>` – Delete directory forcefully 
- `cp <src> <dest>` – Copy files.
- `mv <src> <dest>` – Move/rename files.
- `touch <file>` – Create empty file.

---

## 🔹 File Viewing & Logs (Most used in DevOps)

- `cat <file>` – Print file content.
- `less <file>` – Scroll through large files.
- `head <file>` – First 10 lines (quick preview).
- `tail <file>` – Last 10 lines.
- `tail -f <file>` – Live log monitoring 
- `wc <file>` – Count lines/words.
- `stat <file>` – File metadata.

---

## 🔹 Disk & Permissions

- `df -h` – Check disk space 
- `du -sh *` – Folder size breakdown.
- `chmod 755 <file>` – Change permissions.
- `chown user:group <file>` – Change ownership.

---

## 🔹 Networking Troubleshooting (Critical)

- `ping google.com` – Check internet connectivity.
- `ip addr` – View IP address.
- `curl http://example.com` – Test API/website response.
- `wget <url>` – Download files.
- `dig example.com` – DNS lookup.
- `nslookup example.com` – DNS query.
- `ss -tulnp` – Check open ports 
- `netstat -tulnp` – Older port check tool.
- `traceroute google.com` – Track network path.

## 🔹 some very usefull commands

- `history` – Show command history.
- `clear` – Clean terminal.
- `man <cmd>` – Open manual.
- `exit` – Exit terminal/session.

---
