#  Shell Scripting Cheat Sheet

A quick, clean reference for shell scripting fundamentals. Designed for fast revision while working on real scripts.

---

# Task 1: Basics

## Shebang

```bash
#!/bin/bash
```

Tells Linux to execute the script using Bash.

---

## Running a Script

```bash
chmod +x script.sh
./script.sh
bash script.sh
```

Make executable → Run directly or via bash.

---

## Comments

```bash
# This is a comment
echo "Hello"  # inline comment
```

Used for documentation and clarity.

---

## Variables

```bash
NAME="server"
echo $NAME
```

Store and reuse values in scripts.

---

## Reading Input

```bash
read -p "Enter name: " NAME
echo $NAME
```

Takes user input dynamically.

---

## Arguments

```bash
echo $0   # script name
echo $1   # first argument
echo $#   # total arguments
echo $?   # last command status
```

Helps pass values into scripts.

---

# Task 2: Operators & Conditionals

## String Comparison

```bash
[ "$a" = "$b" ]
[ -z "$a" ]
```

Compare strings or check empty values.

---

## Integer Comparison

```bash
[ $a -lt $b ]
[ $a -gt $b ]
[ $a -eq $b ]
```

Used for numeric operations.

---

## File Checks

```bash
[ -f file.txt ]
[ -d folder ]
```

Verify file or directory existence.

---

## If-Else

```bash
if [ -f file.txt ]; then
  echo "Exists"
else
  echo "Not found"
fi
```

 Basic decision making.

---

## Logical Operators

```bash
[ condition ] && echo "OK"
[ condition ] || echo "Fail"
```

Short and efficient conditions.

---

## Case Statement

```bash
case $1 in
  start) echo "start";;
  stop) echo "stop";;
  *) echo "invalid";;
esac
```

Cleaner alternative to multiple if-else.

---

# Task 3: Loops

## For Loop

```bash
for i in 1 2 3
do
  echo $i
done
```

Iterate over a list.

---

## While Loop

```bash
i=1
while [ $i -le 3 ]
do
  echo $i
  ((i++))
done
```

Runs while condition is true.

---

## Until Loop

```bash
i=1
until [ $i -gt 3 ]
do
  echo $i
  ((i++))
done
```

Runs until condition becomes true.

---

## Loop Through Files

```bash
for file in *.log
do
  echo $file
done
```

 Useful for log/file automation.

---

#  Task 4: Functions

## Define Function

```bash
greet() {
  echo "hello"
}
```

## Call Function

```bash
greet
```

## Function with Arguments

```bash
sum() {
  echo $(($1 + $2))
}
sum 2 3
```

 Enables reusable code blocks.

---

# Task 5: Text Processing

## Grep

```bash
grep error app.log
```

Search logs quickly.

## Awk

```bash
awk '{print $1}' file.txt
```

Extract columns.



## Tail Logs

```bash
tail -f app.log
```

 Monitor logs in real-time.

---

#  Task 6: Useful One-Liners



## Check Service

```bash
systemctl status nginx
```

## Monitor Errors

```bash
tail -f app.log | grep ERROR
```

## Disk Usage

```bash
df -h
```

---

# Task 7: Debugging

## Exit Code

```bash
echo $?
```

Shows last command status (0 = success).

## Exit on Error

```bash
set -e
```

Stops script if any command fails.

## Debug Mode

```bash
set -x
```


