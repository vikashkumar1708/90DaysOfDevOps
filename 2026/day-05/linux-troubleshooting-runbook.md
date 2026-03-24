# 🔐 Day 05 – SSH Troubleshooting 


---

## Goal

Run a focused troubleshooting drill on the SSH service by:

- Checking system health
- Verifying SSH process & service
- Analyzing logs
- Creating a repeatable troubleshooting runbook

---

## 🔍 Step 1: Check SSH Service

```bash
systemctl status ssh

# CPU & Memory
top

# Memory usage
free -h

# Disk usage
df -h
