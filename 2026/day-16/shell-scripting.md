# Shell Scripting Basics

## Task 1: First Script

`vim hello.sh`

```bash
#!/bin/bash
echo "Hello, DevOps!"
```


What happens if we remove the shebang line?<br>
If we remove the shebang `#!/bin/bash`, the script may still run if we explicitly call it with bash `hello.sh`. But if we run `./hello.sh`, the system uses the default shell (often `/bin/sh`), which might not support all Bash features.

## Task 2: Variables
`vim variables.sh`

```bash
#!/bin/bash

NAME="vikash"
ROLE="DevOps Engineer"

echo "Hello, I am $NAME and I am $ROLE"
echo 'Hello, I am $NAME and I am $ROLE'
```



- Double quotes expand variables.

- Single quotes treat everything literally.

## Task 3: User Input with read
`vim greet.sh`

```bash
#!/bin/bash

read -p "Enter your name: " NAME
read -p "Enter your favourite tool: " TOOL

echo "Hello $NAME, your favourite tool is $TOOL"
```


## Task 4: If-Else Conditions
`vim check_number.sh`

```bash
#!/bin/bash

read -p "Enter the number: " NUM

if [ $NUM -gt 0 ]; then
    echo "number is positive"
elif [ $NUM -lt 0 ]; then
    echo "number is negative"
else
    echo "number is zero"
fi
```

`vim file_check.sh`

```bash
#!/bin/bash

read -p "Enter file name: " FILE

if [ -f "$FILE" ]; then
    echo "file exists"
else
    echo "file doesn't exists"
fi
```

## Task 5: Combine It All
`vim server_check.sh`

```bash
#!/bin/bash


SERVICE="nginx"

read -p "Do you want to check the status? (y/n): " ANSWER

if [ "$ANSWER" = "y" ]; then
    systemctl status "$SERVICE" > /dev/null 2>&1

    if [ $? -eq 0 ]; then
        echo "$SERVICE is active"
    else
        echo "$SERVICE is not active"
    fi
else
    echo "Skipped"
fi
```
