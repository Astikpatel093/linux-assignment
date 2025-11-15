## Experiment [8]: [ Shell Programming continued]
### Name: Astik Patel, Roll No: 590029070 Date: 2025-09-04

### AIM:
* [To learn Basics of Shell programming]
* [To understand how to check if file Exists]

### Requirement:
* [Any linux distro, any kind of text editor (vs code, vim, notepad, nano,etc)]

### Theory:
* [learning the command line ,looping ,funtion and conditional statements.]

## procedure & observations

## Exercise 1:
* [list all jobs]

## task statement: 
* [write script in shell programming]

## Explanation:  
* [Write a script that starts a background job (e.g., sleep 60), lists all jobs, brings the job to the foreground, and then terminates it.]

## command(s):
#!/bin/bash

echo "Starting background job: sleep 60"
sleep 60 &        
job_pid=$!

echo "Listing jobs:"
jobs               

echo "Bringing job to foreground..."
fg %1             

echo "Now terminating the job..."
kill -9 $job_pid   # force kill using PID
echo "Job with PID $job_pid terminated."

## output:
<img width="960" height="540" alt="2025-11-15 (6)" src="https://github.com/user-attachments/assets/2089996d-d0cc-4327-a66b-b6001ae8345b" />

# Exercise 2: [comparison]

## Task statement:
* [compare two files]

## Explanation:
* [Create a script that compares two files and displays whether their contents are identical or different.]
## command(s):
if [ $# -ne 2 ]; then
    echo "Usage: $0 file1 file2"
    exit 1
fi

file1=$1
file2=$2


if [ ! -f "$file1" ] || [ ! -f "$file2" ]; then
    echo "Error: One or both files do not exist."
    exit 1
fi


if cmp -s "$file1" "$file2"; then
    echo "The files '$file1' and '$file2' are identical."
else
    echo " The files '$file1' and '$file2' are different."
fi

## output:
<img width="960" height="540" alt="2025-11-15 (20)" src="https://github.com/user-attachments/assets/4942ddad-c93a-4f66-8bc8-c45362edd100" />

## Exercise 3: [counts]

## Task Statement:
* [count the number]

## Explanation:
* [A script that counts the number of processes currently being run by your user.]


## command(s):
#!/bin/bash

user=$(whoami)


count=$(ps -u $user --no-headers | wc -l)

echo " User: $user"
echo " Number of processes running: $count"

## output:
<img width="960" height="540" alt="2025-11-15 (7)" src="https://github.com/user-attachments/assets/af431fbd-a2c7-45fc-b0ef-125209fff2cb" />

## Exercise 4: [monitoring]

## Task Statement:
* [develop a script]

## Explanation:
* [Develop a script that monitors memory usage every 5 seconds and logs it into a file.]


## command(s):
#!/bin/bash
LOGFILE="memory_usage.log"


echo "Timestamp,Total(MB),Used(MB),Free(MB)" > "$LOGFILE"

while true; do
    
    mem=$(free -m | awk 'NR==2 {printf "%s,%s,%s\n", $2, $3, $4}')
    
    
    timestamp=$(date +"%Y-%m-%d %H:%M:%S")
    
    
    echo "$timestamp,$mem"
    
   
    echo "$timestamp,$mem" >> "$LOGFILE"
    
    
    sleep 5
done

## output:
<img width="960" height="540" alt="2025-11-15 (3)" src="https://github.com/user-attachments/assets/5ff9d1ab-8d22-47ca-bcea-e3364ce1c5c6" />
## Exercise 5: [promp,search,display]

## Task Statement:
* [prompt filename search pattern displays count]

## Explanation:
* [Write a script that prompts for a filename and a search pattern, then displays the count of matching lines.]


## command(s):
#!/bin/bash



read -p "Enter filename: " filename


if [ ! -f "$filename" ]; then
    echo "Error: File '$filename' does not exist."
    exit 1
fi


read -p "Enter search pattern: " pattern


count=$(grep -c "$pattern" "$filename")

echo "Number of lines matching '$pattern' in '$filename': $count"

## output:
<img width="960" height="540" alt="2025-11-15 (9)" src="https://github.com/user-attachments/assets/ec22c372-dc1e-4ec8-9cc5-67a428f2d20c" />


 ## Result
 * The exercise were successfully completed for basic and looping,conditional statements and funtion in shell scripting.
