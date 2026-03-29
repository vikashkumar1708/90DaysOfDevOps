# Day 12 – Breather & Revision (Days 01–11)


## What I Reviewed

### Mindset
- Revisited Day 01 plan
- Continuing focus on Linux fundamentals

---

### Processes & Services
Commands:
- ps aux
- systemctl status ssh
- journalctl -u ssh

Observation:
- Process visibility, service health, and logs are key for troubleshooting

---

### File
Commands practiced:
- echo "DevOps" >> notes.txt
- chmod +x script.sh
- chown tokyo:vault-team devops-file.txt
- ls -l
- mkdir test-dir

---

### Cheat Sheet (Top Commands)
- ls -l
- ps aux
- chmod
- chown
- systemctl status

---

### User & Group Practice
- sudo useradd testuser
- sudo groupadd testgroup
- sudo chown testuser:testgroup devops-file.txt
- id testuser
- ls -l devops-file.txt

---

## Self-Check

1) Most useful commands:
- ls -l → quick info
- ps aux → process check
- systemctl status → service check

2) Service health check:
- systemctl status <service>
- journalctl -u <service>
- ps aux | grep <service>

3) Safe ownership & permission:
- sudo chown user:group file
- chmod 640 file

4) Next focus:
- Better troubleshooting
- More hands-on practice
- Faster command usage

---

