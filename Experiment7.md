## Experiment [7]: [Shell Programming, Process and Schedule]
### Name: Astik Patel, Roll No: 590029070 Date: 2025-09-04

### AIM:
* [To learn Basics of Shell programming]
* [To understand how to check if file Exists,basic looping,countlines,words and characters,finding factorial using funtion]

### Requirement:
* [Any linux distro, any kind of text editor (vs code, vim, notepad, nano,etc)]

### Theory:
* [learning the command line ,looping ,funtion and conditional statements.]

## procedure & observations

## Exercise 1:
* [check if file exist]

## task statement: 
* [basic usage of conditional statement in shell programming]

## Explanation:  
* [writing Begginer level shell scripts]

## command(s):
#!/bin/bash
echo "Enter filename: "
read file

if [ -e "$file" ]
then
    echo "File exists. Contents are:"
    cat "$file"
else
    echo "File does not exist."
    echo "Do you want to create it? (y/n)"
    read choice
    if [ "$choice" = "y" ]; then
        touch "$file"
        echo "File $file created."
    fi
fi




#### output:
<img width="960" height="540" alt="2025-11-15 (10)" src="https://github.com/user-attachments/assets/56ddd535-0f64-467c-a710-8563206eacd6" />



# Exercise 2: [print Numbers from 1 to 10]

## Task statement:
* [Basic Shell script to print the  numbers from 1 to 10.]

## Explanation:
* [This shell sricpt uses for loop to print numbers from 1 to 10 ]
## command(s):
for i in {1..10}
do
   echo $i
done
## output:
<img width="960" height="540" alt="2025-11-15 (11)" src="https://github.com/user-attachments/assets/5d337d11-a38b-4013-a3ff-b1dcafb1acd6" />

## Exercise 3: [count Lines, Words and Characters]

## Task Statement:
* [using conditional statement]

## Explanation:
* [This shell sricpt ask for saved file with some content or without content give count of lines,words,charater and uses if-then-else which will give output the stored value and print statement after checking whether you are right or not.]


## command(s):
#!/bin/bash
if [ $# -eq 0 ]
then 
echo "Usage: $0 filename"
exit 1
fi
file=$1

if [ -e "$file" ]
then
echo "Lines: $(wc -l < $file)"
echo "Words: $(wc -w < $file)"
echo "characters: $(wc -m < $file)"

else
  echo "File not found!"
  fi


## output:
<img width="960" height="540" alt="2025-11-15 (12)" src="https://github.com/user-attachments/assets/1b9a95ce-3c3b-4ea8-aa9c-4b264db22aa7" />


## Exercise 3: [factorial]

## Task Statement:
* [using funtion]

## Explanation:
* [This shell sricpt uses while loop then print the factorial
with some good logic using product of numbers]


## command(s):
#!/bin/bash
factorial() {
    num=$1
    fact=1
    while [ $num -gt 1 ]
    do
        fact=$((fact * num))
        num=$((num - 1))
    done
    echo $fact
}

echo "Factorial of 5 is: $(factorial 5)"
echo "Factorial of 7 is: $(factorial 7)"
echo "Factorial of 10 is: $(factorial 10)"

## output
<img width="960" height="540" alt="2025-11-15 (13)" src="https://github.com/user-attachments/assets/44fd3b3a-295b-4bc6-8433-775ca952410b" />

## Assigment 1: [processes]

## Task Statement:
* [conditional statement]

## Explanation:
* [A script that monitors the top 5 processes consuming the most CPU and logs them into a file every 10 seconds.]


## command(s):
#!/bin/bash

LOGFILE="cpu_monitor.log"

echo "CPU Monitoring started at $(date)" > "$LOGFILE"
echo "--------------------------------------------------" >> "$LOGFILE"

while true
do
    # Log the date and time
    echo "Timestamp: $(date)" >> "$LOGFILE"
    
    # Get top 5 CPU-consuming processes (skip header line from ps)
    ps -eo pid,comm,%cpu,%mem --sort=-%cpu | head -n 6 >> "$LOGFILE"
    
    echo "--------------------------------------------------" >> "$LOGFILE"
    
    # Wait 1 second before repeating
    sleep 1
done
## output
<img width="960" height="540" alt="2025-11-15 (14)" src="https://github.com/user-attachments/assets/419bd0a9-56b4-453d-8e6d-e93d7871bba8" />
## Assigment 2: [PID]

## Task Statement:
* [conditional statement]

## Explanation:
* [A script that accepts a PID from the user and displays its details (state, parent process, memory usage)]

## command(s):
#!/bin/bash

read -p "Enter the PID: " pid


if [ ! -d "/proc/$pid" ]; then
    echo "Process with PID $pid does not exist."
    exit 1
fi

state=$(awk '/State:/ {print $2}' /proc/$pid/status)
ppid=$(awk '/PPid:/ {print $2}' /proc/$pid/status)
memory=$(awk '/VmRSS:/ {print $2 " " $3}' /proc/$pid/status)

echo "Process ID   : $pid"
echo "State        : $state"
echo "Parent PID   : $ppid"
echo "Memory Usage : ${memory:-Not available}"
## output:
<img width="960" height="540" alt="2025-11-15 (15)" src="https://github.com/user-attachments/assets/1dd264e0-7c5e-4a71-b321-b6c0857b5a46" />


## Assigment 3: [append]

## Task Statement:
* [conditional statement]

## Explanation:
* [Create a script that schedules a task to append the current date and time to a log file every minute using cron.]
## command(s):
#!/bin/bash

# Log file where the date/time will be appended
LOGFILE="$HOME/date_log.log"

# Cron command to append date/time every minute
CRON_CMD="* * * * * /bin/date >> $LOGFILE"

# Add the cron job if it doesn't already exist
(crontab -l 2>/dev/null | grep -F "$CRON_CMD") || (crontab -l 2>/dev/null; echo "$CRON_CMD") | crontab -

echo "Cron job added: every minute append date/time to $LOGFILE"

## output
<img width="960" height="540" alt="2025-11-15 (16)" src="https://github.com/user-attachments/assets/f19d7caa-54d3-4529-b65a-0611eb3ce4c1" />

# Assigment 4: [error]

## Task Statement:
* [conditional statement,loop statement]

## Explanation:
* [Modify the factorial function to check if input is negative. If yes, display an error message.]
## command(s):
#!/bin/bash
factorial() {
n=$1
fact=1
if (( $n < 0 ));then
echo "there is a error there is no factorial of negative numbers"
fi
for (( i=2;i<=n;i++ ))
do
fact=$(( fact*i ))
done
echo "factorial of $n is $fact"
}

read -p "Enter a number: " num
factorial $num

## output

<img width="960" height="540" alt="2025-11-15 (17)" src="https://github.com/user-attachments/assets/92c8aaae-26dc-4185-806c-6b7ba3c00ddb" />


# Assigment 5: [vowel]

## Task Statement:
* [conditional statement]

## Explanation:
* [Write a script that accepts a filename as an argument. If the file exists, display the number of lines starting with a vowel.]
## command(s):
#!/bin/bash

# Check if filename is provided
if [ $# -eq 0 ]; then
    echo "Usage: $0 filename"
    exit 1
fi

FILE="$1"

# Check if the file exists
if [ ! -f "$FILE" ]; then
    echo "Error: File '$FILE' does not exist."
    exit 1
fi

# Count lines starting with a vowel (case-insensitive)
count=$(grep -i -E '^[aeiou]' "$FILE" | wc -l)

echo "Number of lines starting with a vowel: $count"
 
## output:
<img width="960" height="540" alt="2025-11-15 (18)" src="https://github.com/user-attachments/assets/ed0a2cdd-877a-42da-916f-4b86a6264201" />


 ## Result
 * The exercise were successfully completed for basic and looping,conditional 
 statements and funtion in shell scripting.
