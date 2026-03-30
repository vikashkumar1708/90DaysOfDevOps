# Day 14 – Networking Fundamentals


Today I practiced **basic networking concepts and troubleshooting commands** used in real scenarios.

---

##   

- **OSI vs TCP/IP**
  - OSI → 7 layers  
  - TCP/IP → 4 layers  

- **Protocol Mapping**
  - IP → Internet layer  
  - TCP → Transport layer  
  - HTTP/DNS → Application layer  

- **Example**
```bash
curl https://example.com

hostname -I
```
IP: 172.16.159.134

```bash
ping google.com
```
- Avg latency ~333ms
- ~4% packet loss

```bash
ss -tulpn
```
- Found services on ports 53 , 631

```bash
dig google.com
```
-Resolved IP : 172.217.215.138

```bash
curl -I https://google.com
```
```bash
sudo apt get install ssh
systemctl start ssh
systemctl enable ssh
nc -zv localhost 22
```
- SSH reachable
```bash
curl https://example.com
```
