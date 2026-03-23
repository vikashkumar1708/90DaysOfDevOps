# Linux Architecture – Day 02 Notes

---

## 🔹 Core Components

### Kernel
- Core of Linux (controls CPU, memory, devices)
- Manages processes
- Talks to hardware

### User Space
- Where users & apps run
- Includes shell, commands, tools

### systemd
- First process (PID 1)
- Starts & manages services
- Handles logs

---

## 🔹 Process Basics
- Process = running program
- Created when a command runs
- Has PID, owner, resources, state

---

## 🔹 Process States
- **R** – Running  
- **S** – Sleeping  
- **T** – Stopped  
- **Z** – Zombie  
- **I** – Idle  

👉 Zombie = no memory use, but holds PID

---

## 🔹 Daily Linux Commands

- `pwd` → Show current directory  
- `ls -l` → List files with details  
- `ps aux` → View running processes  
- `systemctl status <service>` → Check service status  
- `cd /path` → Change directory
