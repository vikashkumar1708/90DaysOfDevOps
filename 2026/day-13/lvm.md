# Day 13 – Linux Volume Management (LVM)

##  Objective
Learn how to manage storage using LVM:
- Create Physical Volume (PV)
- Create Volume Group (VG)
- Create Logical Volume (LV)
- Format, mount, and extend storage

---

## Environment Setup

Switched to root user:

```bash
sudo su
```
Created a virtual disk (since no spare disk available):
```bash
dd if=/dev/zero of=/tmp/disk1.img bs=1M count=1024
losetup -fP /tmp/disk1.img
losetup -a
```
##Task 1: Check Current Storage
```bash
lsblk
pvs
vgs
lvs
df -h
```
##Task 2: Create Physical Volume
```bash
pvcreate /dev/loop0
pvs
```
##Task 3: Create Volume Group
```bash
vgcreate devops-vg /dev/loop0
vgs
```
##Task 4: Create Logical Volume
```bash
lvcreate -L 500M -n app-data devops-vg
lvs
```
##Task 5: Format and Mount
```bash
mkfs.ext4 /dev/mapper/devops--vg-app--data
mkdir /app-data
mount /dev/mapper/devops--vg-a
pp--data /app-data
verify: df -h
```
##Task 6: Extend the Volume
```bash
lvextend -L +200M /dev/mapper/devops--vg-app--data
resize2fs /dev/mapper/devops--vg-app--data
verify: df -h
