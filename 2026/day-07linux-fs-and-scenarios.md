# 📂 Day 07 – Linux File System & Scenarios

---

##  Goal

- Understand where things are stored in Linux  
- Practice basic troubleshooting thinking  

---

# 📁 Part 1 – File System (Important Directories)

## 🔹 Core Directories

### `/` (root)
- Starting point of the system  
👉 Use: To understand overall structure  

---

### `/home`
- User files and folders  
👉 Use: To check user data or configs  

---

### `/root`
- Root (admin) user home  
👉 Use: When working as admin  

---

### `/etc`
- Configuration files  
👉 Use: To change or troubleshoot services  

---

### `/var/log`
- System and service logs  
👉 Use: To debug issues  

---

### `/tmp`
- Temporary files  
👉 Use: For short-term storage  

---

## 🔹 Additional Directories

### `/bin`
- Basic system commands  
👉 Use: Essential commands  

---

### `/usr/bin`
- Most installed commands  
👉 Use: Regular tools and programs  

---

### `/opt`
- Third-party software  
👉 Use: Custom/manual installations  

---

# Scenario Practice



---

## Scenario 


```bash

1. Service Not Starting

systemctl status ngnix
journalctl -u ngnix -n 50
ngnix -t
systemctl restart nginx

2. Website Not Loading

ss -tulnp | grep nginx
curl localhost
tail -n 20 /var/log/nginx/error.log


