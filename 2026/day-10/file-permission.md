```bash

# Create files
touch devops.txt
cat > notes.txt
vim script.sh

# Read files
cat notes.txt
vim -R script.sh
head -n 5 /etc/passwd
tail -n 5 /etc/passwd

# Check permissions
ls -l

# Modify permissions
chmod 770 script.sh
chmod 444 devops.txt
chmod 640 notes.txt

# Create directory with permissions
mkdir project
chmod 755 project

# Verify changes
ls -l
