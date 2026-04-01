# Day 17 – Shell Scripting: Loops, Arguments & Error Handling

Today’s focus was on writing and understanding shell scripts that use loops, handle command-line arguments, and include basic error handling. These are essential skills for automating DevOps workflows and writing reliable scripts that can run in various environments.

---

## Scripts and Outputs

### 1. for_loop.sh

**Code:**
```bash
#!/bin/bash
for i in mango apple bananna orange pineapple
do
    echo "$i"

done
```

2. count.sh

Code:
```bash
#!/bin/bash
for i in {1..10};
do
  echo "$i"
done
```



3. countdown.sh

Code:
```bash         
#!/bin/bash
read -p "Enter a number to start countdown " num

while [ $num -ge 0 ];
do
  echo "$num"
  ((num--))
done

echo "Done!"

```


4. greet.sh
```bash
Code:

#!/bin/bash

if [ $# -eq 0 ]; then
  echo "Usage: ./greet.sh <name>"
else
  echo "Hello, $1!"
fi

```

5. args_demo.sh
```bash
Code:

#!/bin/bash

echo "Total arguments: $#"
echo "All arguments: $@"
echo "Script name: $0"

```


6. install_packages.sh
```bash
Code:

#!/bin/bash

if [ "$EUID" -ne 0 ]; then
  echo "switch to root user"
  exit 1
fi

packages=("nginx" "curl" "wget")

echo "updating package list ..."
apt update -y
for pkg in "${package[@]}"; do
      echo "checking $pkg"
      if dpkg -s $pkg &> /dev/null; then
          echo "$pkg is already installed"
      else
           echo "installing $pkg ,,"
            apt install -y "$pkg"
            echo "package installed"
        fi

```


7. safe_script.sh
```bash
Code:

#!/bin/bash

set -e

mkdir /tmp/devops-test || echo "Directory already exists"
cd /tmp/devops-test || echo "Cannot change directory"
touch hello.txt || echo "Failed to create file"

echo "Done"

```
