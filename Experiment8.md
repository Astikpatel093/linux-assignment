## Experiment [8]: [ Shell Programming continued]
### Name: Astik Patel, Roll No.: 590029070 Date: 2025-09-04

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
sleep 60 &        # start job in background
job_pid=$!

echo "Listing jobs:"
jobs               # show running jobs

echo "Bringing job to foreground..."
fg %1              # bring job number 1 to foreground

echo "Now terminating the job..."
kill -9 $job_pid   # force kill using PID
echo "Job with PID $job_pid terminated."

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ bash -i ./41.sh
Starting background job: sleep 60
Listing jobs:
[1]+  Running                 sleep 60 &    
Bringing job to foreground...
sleep 60
Now terminating the job...
bash: kill: (10857) - No such process
Job with PID 10857 terminated.

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
    echo "✅ The files '$file1' and '$file2' are identical."
else
    echo "❌ The files '$file1' and '$file2' are different."
fi

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./42.sh arm.sh as1.sh
❌ The files 'arm.sh' and 'as1.sh' are differ
ent.
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./42.sh arm.sh arm.sh
✅ The files 'arm.sh' and 'arm.sh' are identi
cal.

## Exercise 4: [counts]

## Task Statement:
* [count the number]

## Explanation:
* [A script that counts the number of processes currently being run by your user.]


## command(s):
#!/bin/bash

user=$(whoami)


count=$(ps -u $user --no-headers | wc -l)

echo "👤 User: $user"
echo "📊 Number of processes running: $count"

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./2.sh
👤 User: astik
📊 Number of processes running: 9

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
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./2.sh
2025-10-02 04:09:17,7592,420,6847
2025-10-02 04:09:22,7592,420,6847
2025-10-02 04:09:27,7592,420,6847
2025-10-02 04:09:32,7592,420,6847
2025-10-02 04:09:37,7592,420,6847
2025-10-02 04:09:42,7592,420,6847
2025-10-02 04:09:47,7592,419,6848
2025-10-02 04:09:55,7592,418,6849
2025-10-02 04:10:00,7592,418,6849
2025-10-02 04:10:05,7592,418,6849
2025-10-02 04:10:10,7592,420,6847
2025-10-02 04:10:15,7592,419,6847


## Exercise 4: [promp,search,display]

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

echo "🔎 Number of lines matching '$pattern' in '$filename': $count"

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./2.sh
Enter filename: loop.sh
Enter search pattern: if
🔎 Number of lines matching 'if' in 'loop.sh': 2

 ## Result
 * The exercise were successfully completed for basic and looping,conditional statements and funtion in shell scripting.
