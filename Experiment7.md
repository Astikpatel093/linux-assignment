## Experiment [7]: [Shell programming]
### Name: Astik Patel, Roll No.: 590029070 Date: 2025-09-04

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
1.
Enter filename:
go
File does not exist.
Do You want to create it? (y/n)
y
File go created.
2.
Enter filename:
go
File exists.contents are:


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
1
2
3
4
5
6
7
8
9
10
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
./count.sh filecheck.sh
Lines: 17
Words: 49
characters: 274
2.
$ ./count.sh
Usage: ./count.sh filename

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
Factorial of 5 is: 120
Factorial of 7 is: 5040
Factorial of 10 is: 3628800

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
Enter the PID: 383
Process ID   : 383
Process ID   : 383
State        : S
Parent PID   : 378
Memory Usage : 4992 kB

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
$ ./as1.sh
* * * * * /bin/date >> /home/astik/date_log.log
Cron job added: every minute append date/time to /home/astik/date_log.log
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ cat ~/date_log.log
Wed Oct  1 11:32:55 IST 2025
Wed Oct  1 11:35:50 IST 2025
Wed Oct  1 13:40:04 IST 2025
Wed Oct  1 13:41:04 IST 2025
Wed Oct  1 13:42:05 IST 2025
Wed Oct  1 13:43:04 IST 2025
Wed Oct  1 13:44:03 IST 2025
Wed Oct  1 13:45:04 IST 2025
Wed Oct  1 13:46:05 IST 2025
Wed Oct  1 13:47:04 IST 2025
Wed Oct  1 13:48:03 IST 2025


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

astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./as1.sh
Enter a number: -1
there is a error there is no factorial of negative numbers
factorial of -1 is 1

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
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./as3.sh 41.sh
Number of lines starting with a vowel: 2
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ cat 41.sh
#!/bin/bash
echo "Enter the name."
read name  #'read'takes user input
echo "Hello, $name! Welcome to shell scrip

 ## Result
 * The exercise were successfully completed for basic and looping,conditional 
 statements and funtion in shell scripting.