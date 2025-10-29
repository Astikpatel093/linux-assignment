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
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./2.sh
Enter directory path: loop
 Largest file in 'loop': 0    loop/experiment

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
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./2.sh
Number of .sh files in '/home/astik': 16

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
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./2.sh
2025-10-02 04:53:15, 0.40
2025-10-02 04:53:27, 100.00
2025-10-02 04:53:38, 0.40
2025-10-02 04:53:48, 0.40
2025-10-02 04:54:00, 100.00
2025-10-02 04:54:10, 100.00
2025-10-02 04:54:20, 0.40
2025-10-02 04:54:33, 0.40
2025-10-02 04:54:43, 0.40
2025-10-02 04:54:53, 0.40

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
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./2.sh
Enter new username: patel
New password: 
Retype new password:
passwd: password updated successfully
 User 'patel' created with home directory /
home/patel
   Permissions set to 700 (owner only) 

 ## Result
 * The exercise were successfully completed for basic and looping,conditional statements and funtion in shell scripting.
