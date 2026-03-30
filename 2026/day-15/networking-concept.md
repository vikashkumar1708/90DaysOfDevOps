# Day 15 – Networking Concepts: DNS, IP, Subnets & Ports  
 

 DNS, IP addressing, subnetting, and ports.

---

## Task 1: DNS – How Names Become IPs  

When we type `google.com`:
- DNS resolver finds the IP address  
- Queries go: root → TLD → authoritative server  
- IP is returned  
- Browser connects using HTTP/HTTPS  

### DNS Record Types  
- A → IPv4 address  
- AAAA → IPv6 address  
- CNAME → Alias  
- MX → Mail server  
- NS → Name server  

```bash
dig google.com
```
- A record : 142.250.193.142
- TTL 5

## Task 2: IP ADDRESSING

IPv4
 - 32-bit address → 192.168.1.10
 - 4 octets (0–255)
Public vs Private
 - Public → 8.8.8.8
 - Private → 172.16.159.134
Private Ranges
 - 10.0.0.0/8
 - 172.16.0.0 – 172.31.255.255
 - 192.168.0.0/16
```bash
ip addr show
```
- My IP: 172.16.159.134 → Private

## Task 3: CIDR & Subnetting

- /24 → 24 bits network, 8 bits host
Why subnet?
 - Better network management
 - Efficient IP usage
##  CIDR Table

| CIDR | Subnet Mask       | Total IPs | Usable Hosts |
|------|------------------|-----------|--------------|
| /24  | 255.255.255.0    | 256       | 254          |
| /16  | 255.255.0.0      | 65536     | 65534        |
| /28  | 255.255.255.240  | 16        | 14           |

## Task 4: Ports
- Ports identify services running on a system

##   Ports & Services

| Port | Service |
|------|---------|
| 22   | SSH     |
| 80   | HTTP    |
| 443  | HTTPS   |
| 53   | DNS     |
| 3306 | MySQL   |
| 6379 | Redis   |
| 27017| MongoDB |
```bash
ss -tulnp
```
- port22 ssh
- port53 dns


