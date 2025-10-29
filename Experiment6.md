## Experiment [6]: [Shell Loops]
### Name: Astik Patel, Roll No: 590029070 Date: 2025-09-04

### AIM:
* [To learn looping of Bash Scripting]

### Requirements:
* [Any Linux Distro, any kind of text editor (vs code, vim, notepad, nano, etc)]

### Theory:
* [learning the looping in bash scripting.]

## procedure & observations

## Exercise 1: [lcd gcd script]

## task statement: 
* [basic usage of shell script]

## Explanation:  
* [writing intermediate level shell script]

## command(s):
```#!/bin/bash
echo "Enter two numbers: "
read a b

x=$a
y=$b
while [ $y -ne 0 ]
do
   temp=$y
   y=$((x % y))
   x=$temp
   done
   gcd = $x

   lcm=$((  (a * b / gcd )))

   echo "GCD: $gcd"
   echo "LCM: $lcm"

## output:
Enter two numbers: 
3 4
GCD: 1
LCM: 12


## Exercise 2: [Number difference script]

## task statement: 
* [basic usage of shell script]

## Explanation:  
* [writing intermediate level shell script]

## command(s):
```
#!/bin/bash
echo "Enter a number: "
read num
if ! [[ "$num" =~ ^[0-9]+$ ]]; then
    echo "Error: Please enter a valid positive integer."
    exit 1
fi

rev=0
temp=$num
     while (( temp > 0 ))
     do
       digit=$(( temp% 10 ))
        rev=$((rev * 10 + digit))
         temp=$((temp/10))
      done 

      if [ "$num" -eq "$rev" ]
      then 
          echo "$num is a palindrome. "
          else
          echo "$num is not a palindrome."
          fi 

## output:
Enter a number: 
121
121 is a palindrome. 
## Exercise 3: [Arithmetic operations in shell scripts]

## task statement: 
* [basic usage of shell script]

## Explanation:  
* [writing intermediate level shell script]

## command(s):
```#!/bin/bash
echo "Enter numbers separated by space: "
read -a arr

echo "Ascending Order: "
printf "%s\n" "${arr[@]}" | sort -n

echo "Descending Order: "
printf "%s\n" "${arr[@]}" | sort -nr

## output:
Enter numbers separated by space: 
1 2 3 4 5 6 7 8 
Ascending Order: 
1
2
3
4
5
6
7
8
Descending Order: 
8
7
6
5
4
3
2
1
## Assignment1:[funtion in shell scripts]

## task statement: 
* [calculate the factorial shell script]

## Explanation:  
* [A function to calculate the factorial of a number using a loop.]

## command(s):
#!/bin/bash

factorial() {
    n=$1

    # Check for negative input
    if [ "$n" -lt 0 ]; then
        echo "Error: Factorial is not defined for negative numbers."
        return 1
    fi

    result=1
    for (( i=2; i<=n; i++ )); do
        result=$((result * i))
    done

    echo "$result"
}

# Example usage:
read -p "Enter a number: " num
fact=$(factorial $num)
if [ "$num" -ge 0 ]; then
    echo "Factorial of $num is $fact"
fi
## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./as1.sh
Enter a number: 5
Factorial of 5 is 120



## Assignment2: [filename]

## task statement: 
* [count]

## Explanation:  
* [Write a script that reads a filename and counts how many times a given word appears in it.]

## command(s):
#!/bin/bash

# Ask user for the filename
read -p "Enter filename: " filename

# Check if the file exists
if [ ! -f "$filename" ]; then
    echo "Error: File '$filename' does not exist."
    exit 1
fi

# Ask user for the word
read -p "Enter word to search: " word

# Count occurrences of the word (case-sensitive)
count=$(grep -o -w "$word" "$filename" | wc -l)

echo "The word '$word' appears $count times in '$filename'."

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/li./as1.sh 
Enter filename: 41.sh
Enter word to search: Hello
The word 'Hello' appears 1 times in '41.sh'.
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ cat 41.sh
#!/bin/bash
echo "Enter the name."
read name  #'read'takes user input
echo "Hello, $name! Welcome to shell scripting.

## Assignment3:[Fibonacci Numbers]

## task statement: 
* [Generates first N fibonacci Numbers]

## Explanation:  
* [Write a script that generates the first N Fibonacci numbers using a while loop.]

## command(s):
#!/bin/bash

# Read how many terms to generate
read -p "Enter the value of N: " N

# Check if input is valid
if [ "$N" -le 0 ]; then
    echo "Error: Please enter a positive integer."
    exit 1
fi

# Initialize first two terms
a=0
b=1
count=1

echo "The first $N Fibonacci numbers are:"

while [ $count -le $N ]
do
    echo -n "$a "
    fn=$((a + b))  # Next term
    a=$b
    b=$fn
    count=$((count + 1))
done

echo    # new line

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/li./as1.sh
Enter the value of N: 10
The first 10 Fibonacci numbers are:
0 1 1 2 3 5 8 13 21 34

## Assignment4:[email address]

## task statement: 
* [checking whether given email is right or wrong.]

## Explanation:  
* [A script that validates whether the entered string is a proper email address using a regular expression]

## command(s):
#!/bin/bash

read -p "Enter an email address: " email

# Regex for basic email validation
regex="^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}$"

if [[ $email =~ $regex ]]; then
    echo "Valid email address ✅"
else
    echo "Invalid email address ❌"
fi
## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./as1.sh 
Enter the value of N: 5
Enter an email address: Astik.29070stu@upes.ac  
Valid email address ✅


## Assignment5:[error]

## task statement: 
* [write script with intentional error]

## Explanation:  
* [A script with an intentional error, run it with bash -x, and explain the debug output.]

## command(s):
#!/bin/bash

echo "Start of script"

FILE="does_not_exist.txt"
echo "Attempting to cat $FILE"

# Intentional error: this file does not exist
cat "$FILE"

# Show the exit status of the previous command
echo "After cat, exit status: $?"

echo "End of script"

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ bash -x as1.sh
+ read -p 'Enter the value of N: ' N
Enter the value of N: 2
+ echo 'Start of script'
Start of script
+ FILE=does_not_exist.txt
+ echo 'Attempting to cat does_not_exist.txt'
Attempting to cat does_not_exist.txt       
+ cat does_not_exist.txt
cat: does_not_exist.txt: No such file or directory
+ echo 'After cat, exit status: 1'
After cat, exit status: 1
+ echo 'End of script'
End of script

# Result
* The exercise were successfully completed for looping in shell scripting.
