# Day 11 – File Ownership


---

##  Task Overview  
Today I practiced Linux file ownership:
- Understanding owner and group  
- Changing ownership using `chown`  
- Changing group using `chgrp`  
- Applying recursive ownership  

---

##  Files & Directories Created  

- devops-file.txt  
- team-notes.txt  
- project-config.yaml  
- app-logs/  
- heist-project/ (with subdirectories and files)  
- bank-heist/ (with multiple files)  

---


## Commands Used  

```bash
# Check ownership
ls -l

# Create files
touch devops-file.txt
touch team-notes.txt
touch project-config.yaml

# Create directory
mkdir app-logs

# Create users
sudo useradd tokyo
sudo useradd berlin
sudo useradd nairobi

# Create groups
sudo groupadd heist-team
sudo groupadd planners
sudo groupadd vault-team
sudo groupadd tech-team

# Change owner
sudo chown tokyo devops-file.txt
sudo chown berlin devops-file.txt

# Change group
sudo chgrp heist-team team-notes.txt

# Change owner + group
sudo chown professor:heist-team project-config.yaml
sudo chown berlin:heist-team app-logs

# Recursive ownership
mkdir -p heist-project/vault
mkdir -p heist-project/plans
touch heist-project/vault/gold.txt
touch heist-project/plans/strategy.conf

sudo chown professor:planners heist-project/

# Practice challenge
mkdir bank-heist
touch bank-heist/access-codes.txt
touch bank-heist/blueprints.pdf
touch bank-heist/escape-plan.txt

sudo chown tokyo:vault-team bank-heist/access-codes.txt
sudo chown berlin:tech-team bank-heist/blueprints.pdf
sudo chown nairobi:vault-team bank-heist/escape-plan.txt

# Verify
ls -l
ls -lR heist-project/
ls -l bank-heist/
