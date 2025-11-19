## Experiment [10]: [Shell programming]
### Name: Astik Patel, Roll No: 590029070 Date: 2025-11-17

### AIM:
* [To learn Basics of Shell programming]
* [To understand how to check if file Exists]

### Requirement:
* [Any linux distro, any kind of text editor (vs code, vim, notepad, nano,etc)]

### Theory:
* [learning the command line ,looping ,funtion and conditional statements.]

## procedure & observations

## Exercise:
# 1.
* [length of string]

## task statement: 
* [write script in shell programming]

## Explanation:
```bash  
* ${#str} is a bash parameter expansion that returns the length of the variable Much faster than echo $str | wc -c (which creates subshells and pipes).
```

## command(s):
```bash
#!/bin/bash
echo "Enter a string:"
read str
echo "Length: ${#str}"
```

## output:
![alt text](<2025-11-19 (6).png>)

# 2.
## Task statement:
* [reverse the given string]

## Explanation:
```bash
* ${str:$i:1} extracts 1 character from position $i (string slicing)
Loop runs from last character to first

Alternative: echo $str | rev (if rev command is available)
```
## command(s):
```bash
#!/bin/bash
echo "Enter a string:"
read str
rev=""
len=${#str}
for (( i=$len-1; i>=0; i-- ))
do
    rev="$rev${str:$i:1}"
done
echo "Reversed: $rev"

```
## output:
![alt text](<2025-11-19 (7).png>)
# 3.
## Task Statement:
* Concatenate Strings.

## Explanation:
* In bash, simple variable juxtaposition concatenates strings
No need for special operators or functions

## command(s):
```bash
#!/bin/bash
echo "Enter first string:"
read s1
echo "Enter second string:"
read s2
echo "Concatenated: $s1$s2"
```
## output:
![alt text](<2025-11-19 (8).png>)

### Assignment 
# 1.

## Task Statement:
* Factorial Funtion.

## Explanation:
* using funtion with math.sh and main_script.sh

## command(s):
```bash
#!/bin/bash
factorial() {
    local n=$1
    local result=1
    
    if [ $n -eq 0 ] || [ $n -eq 1 ]; then
        echo 1
        return
    fi
    
    for (( i=2; i<=n; i++ ))
    do
        result=$((result * i))
    done
    
    echo $result
}

echo "Enter a number:"
read num


result=$(factorial $num)
echo "Factorial of $num is: $result"

```
## output:
![alt text](<2025-11-19 (11).png>)

# 2.

## Task Statement:
* Fibonacci script.

## Explanation:
* using the funtions with main script and input validation.


## command(s):
```bash
#!/bin/bash
fibonacci() {
    local n=$1
    local a=0
    local b=1
    local temp
    
    echo "Fibonacci series up to $n terms:"
    
    for (( i=0; i<n; i++ ))
    do
        echo -n "$a "
        temp=$((a + b))
        a=$b
        b=$temp
    done
    echo
}


echo "Enter number of terms:"
read terms


if [[ ! $terms =~ ^[0-9]+$ ]] || [ $terms -lt 1 ]; then
    echo "Error: Please enter a positive integer"
    exit 1
fi


fibonacci $terms
```
## output:
![alt text](<2025-11-19 (9).png>)

# 3.

## Task Statement:
* length of filename.

## Explanation:
* using loops and conditional statement.


## command(s):
```bash
#!/bin/bash

echo "Enter directory path (press enter for current directory):"
read dirpath


if [ -z "$dirpath" ]; then
    dirpath="."
fi


if [ ! -d "$dirpath" ];then 
echo "Error: Directory '$dirpath' does not exist"
    exit 1
fi

echo "Filename lengths in '$dirpath':"
echo "--------------------------------"


for file in "$dirpath"/*
do
    if [ -e "$file" ]; then  
        filename=$(basename "$file")
        length=${#filename}
        printf "%-30s : %2d characters\n" "$filename" "$length"
    fi
done
```
## output:
![alt text](<2025-11-19 (10).png>)
 ## Result:
 * The exercise were successfully completed for funtions and looping,conditional statements in shell scripting.