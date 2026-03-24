# 📄 Day 06 – Linux File Operations 

---

## 🎯 Goal

Practice basic file operations using fundamental Linux commands:

- Create a file  
- Write text to a file  
- Append new lines  
- Read file content  

---
 📁 Steps
```bash
touch notes.txt
echo "my name is vikash" > notes.txt
echo "#90DaysOfDevOps" > notes.txt
echo "I am studying DevOps" >> notes.txt
cat notes.txt
head -n 2 notes.txt
tail -n 2 notes.txt
