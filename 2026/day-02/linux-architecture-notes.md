# Linux Architecture – Day 02 Notes

---

## 🔹 Core components of linux 

### Kernel
- Controls CPU, memory, disk, network, and devices.
- Decides which process gets CPU time.
- Talks directly to hardware.

### User Space
- Where users and applications run.
- Includes shell, commands, browsers, servers, editors.
- Users interact with Linux from here.

### systemd (Init System)
- First process started by kernel (PID 1).
- Starts all services during boot.
- Restarts failed services automatically.
- Manages logs and service dependencies.

---

## 🔹 Process Basics

- A process = a running program.
- Created when we run a command from terminal.
- Every process has:
  - PID (process ID)
  - Owner
  - Memory and CPU usage
  - State

---

## 🔹 Process States

- **Running (R)** – Using CPU right now.
- **Sleeping (S)** – Waiting for input or resource.
- **Stopped (T)** – Paused manually or by signal.
- **Zombie (Z)** – Finished but parent has not cleaned it.
- **Idle (I)** – Waiting for CPU.

Zombie processes waste PID but not memory.

---


## 🔹 Daily Linux Commands

- `pwd` → Show current directory  
- `ls -l` → List files with details  
- `ps aux` → View running processes  
- `systemctl status <service>` → Check service status  
- `cd /path` → Change directory
