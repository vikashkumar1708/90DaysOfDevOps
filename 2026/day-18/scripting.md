# Day 18 – Shell Scripting: Functions & Intermediate Concepts

##  Objective
Write cleaner and reusable shell scripts using:
- Functions
- Strict mode (`set -euo pipefail`)
- Local variables
- Real-world scripting patterns

---

##  Task 1: Basic Functions

### Script: `functions.sh`

```bash
#!/bin/bash

greet() {
    echo "Hello, $1"
}

add() {
    sum=$(($1 + $2))
    echo "SUM: $sum"
}

greet "vikash"
add 5 7
```
##  Task 2: Disk and memory check
### Script: `disk_check.sh`
```bash
#!/bin/bash

check_disk() {
    df -h
}

check_memory() {
    free -h
}

check_disk
check_memory
```

##  Task 3:Strict mode
### Script: 'strict_mode.sh'
```bash
#!/bin/bash
set -euo pipefail

echo "script completed successfully"
```
##  Task 4: Local Variables
### Script: 'local_demo.sh'
```bash
#!/bin/bash

local_func() {
    local name="LocalUser"
    echo "inside local_func: name = $name"
}

global_func() {
    name="GlobalUser"
    echo "inside global_func: name = $name"
}

local_func
echo "outside after local_func: name = ${name:-not defined}"

global_func
echo "outside after global_func: name = $name"
```
##  Task 5: System Info Reporter
### Script: 'system_info.sh'
```bash
#!/bin/bash
set -euo pipefail

print_system_info() {
    echo "===== system info ====="
    hostnamectl
}

print_uptime() {
    echo "===== uptime ====="
    uptime
}

print_disk_usage() {
    echo "===== Top 5 disk usage ====="
    df -h | sort -k3 -r | head -n 5
}

print_memory_usage() {
    echo "===== memory usage ====="
    free -h
}

print_top_cpu() {
    echo "===== top 5 cpu processes ====="
    ps -eo pid,comm,%cpu --sort=-%cpu | head -n 6
}

main() {
    print_system_info
    print_uptime
    print_disk_usage
    print_memory_usage
    print_top_cpu
}

main
```



