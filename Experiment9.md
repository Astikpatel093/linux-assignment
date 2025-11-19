## Experiment [9]: [Shell Programming continued, System Performance Monitoring]
### Name: Astik Patel, Roll No: 590029070 Date: 2025-10-01

### AIM:
* [To learn Basics of Shell programming]

### Requirement:
* [Any linux distro, any kind of text editor (vs code, vim, notepad, nano,etc)]

### Theory:
* [learning the command line ,looping ,funtion and conditional statements.]

## procedure & observations

## Exercise 1:
* [largest file]

## task statement: 
* [write the script in shell programming]

## Explanation: 
* [Write a script to find the largest file in a given directory.]

## command(s):
#!/bin/bash


read -p "Enter directory path: " dir


if [ ! -d "$dir" ]; then
    echo "Error: Directory '$dir' does not exist."
    exit 1
fi


largest_file=$(find "$dir" -type f -exec du -h {} + | sort -hr | head -n 1)

if [ -z "$largest_file" ]; then
    echo "No files found in directory '$dir'."
else
    echo " Largest file in '$dir': $largest_file"
fi

## output:
<img width="960" height="540" alt="2025-11-15" src="https://github.com/user-attachments/assets/8f1b33a1-666f-4ec3-a017-76ecda91f42c" />


# Exercise 2: [count]

## Task statement:
* [count number of .sh files]

## Explanation:
* [Create a script that counts how many .sh files exist in /home/user.]

## command(s):
#!/bin/bash

dir="/home/astik"


if [ ! -d "$dir" ]; then
    echo "Error: Directory '$dir' does not exist."
    exit 1
fi


count=$(find "$dir" -maxdepth 1 -type f -name "*.sh" | wc -l)

echo "Number of .sh files in '$dir': $count"

## output:
<img width="960" height="540" alt="2025-11-15 (2)" src="https://github.com/user-attachments/assets/e730f779-dc39-4bcd-a898-f24610fd9479" />

## Exercise 3: [CPU]

## Task Statement:
* [writing a script]

## Explanation:
* [Write a script to monitor CPU usage every 10 seconds and log to a file.]


## command(s):
```
#!/bin/bash

LOGFILE="cpu_usage.log"


echo "Timestamp,CPU_Usage(%)" > "$LOGFILE"


while true; do
    
    cpu=$(top -bn1 | grep "Cpu(s)" | \
          awk '{usage=100-$8; printf "%.2f", usage}')  # idle = $8, usage = 100-idle
    
    
    timestamp=$(date +"%Y-%m-%d %H:%M:%S")
    
    
    echo "$timestamp, $cpu"
    
   
    echo "$timestamp,$cpu" >> "$LOGFILE"
    
   
    sleep 10
done
```
## output:
<img width="960" height="540" alt="2025-11-15 (3)" src="https://github.com/user-attachments/assets/62f39403-387b-4419-992d-88be06c1cbeb" />


## Exercise 4: [newuser]

## Task Statement:
* [create a script]

## Explanation:
* [Create a script that adds a new user and sets default permissions for their home directory.]

## command(s):
#!/bin/bash

read -p "Enter new username: " username


if id "$username" &>/dev/null; then
    echo "Error: User '$username' already exists."
    exit 1
fi


sudo useradd -m "$username"


sudo chmod 700 "/home/$username"


sudo passwd "$username"

echo " User '$username' created with home directory /home/$username"
echo "   Permissions set to 700 (owner only)"

## output:
<img width="960" height="540" alt="2025-11-15 (4)" src="https://github.com/user-attachments/assets/d42c24cc-d2ba-4b4f-b679-d45ae31e66df" />


 ## Result
 * The exercise were successfully completed for basic and looping,conditional statements and funtion in shell scripting.
