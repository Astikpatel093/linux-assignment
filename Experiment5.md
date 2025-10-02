## Experiment [5]: [Shell programming]
### Name: Astik Patel, Roll No.: 590029070 Date: 2025-09-04

### AIM:
* [To learn Basics of Shell programming]
* [To understand how to find armstrong , primeno and  sum of two numbers through shell programming]

### Requirement:
* [Any linux distro, any kind of text editor (vs code, vim, notepad, nano,etc)]

### Theory:
* [learning the command line and conditional statements.]

## procedure & observations

## Exercise 1:
* [prime number check]

## task statement: 
* [basic usage of for loop in shell programming]

## Explanation:  
* [writing Begginer level shell scripts]

## command(s):
```
#!/bin/bash
echo "Enter a number:"
read num
flag=0

for (( i=2; i<num; i++ ))
do
    if [ $((num % i)) -eq 0 ]
    then
        flag=1
        break
    fi
done

if [ $flag -eq 1 ]
then
    echo "$num is not a prime number."
else
    echo "$num is a prime number."
fi

## output:
Enter a number:
3
3 is a prime number.


## Exercise 2: [sum of two numbers script]

## Task statement:
* [Basic Shell script to findout the sum funtion.]

## Explanation:
* [This shell sricpt take input from the user store it in a variable and then call the variable which will output the stored value.]

## command(s):
#!/bin/bash
echo "Enter the no"
read num
sum=0
while (( num > 0 ))
do 
digit=$((num % 10))
sum=$((sum + digit))
num=$((num / 10))
done

echo "sum of digits: $sum"

## output:
Enter the no
234
sum of digits: 9

## Exercise 3: [Armstrong number in shell scripts]

## Task Statement:
* [using the loop in shell programming]

## Explanation:
* [This shell sricpt take input from the user store it in a variable and then uses the while loop then call the variable nad uses the if-then-else which will give output the stored value and statement that whether you are right or not.]


## command(s):
```
#!/bin/bash
echo "Enter a number: "
read num
temp=$num
n=${#num}   
while [ $temp -gt 0]
do 
    digit=$((temp % 10))
    sum=$((sum + digit**n))
    temp=$((temp / 10))
    done

    if [ $sum -eq $num ]
    then
    echo "$num is a armstrong."
    else
    echo "$num is not a armstrong."
    fi
```

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./arm.sh
Enter a number: 
153
153 is a armstrong.
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./arm.sh
Enter a number: 
123
123 is not a armstrong.

## Exercise 4: 

## Task 1:
* [First Script]

## Explanation:
* [Write a script that prints Hello,World!]

## command(s):
#!/bin/bash
echo "Hello, World!"

## output:
  Hello, World!
  
## Task 2:
* [Personalized Greeting]

## Explanation:
* [Ask the user's name and greet them.]

## command(s):
#!/bin/bash
 echo "Enter your name:" $variable
 read variable
 echo "Hello, $variable! Welcome to shell scripting."

## output:
  Enter your name: Rahul
  Hello, Rahul! Welcome to Shell Scripting.
  
## Task 3:
* [Arithmetic operations]

## Explanation:
* [Take 2 numbers as input and print sum, difference, product, and quotient.]


## command(s):
#!/bin/bash
read -p "Enter first number: " num1
read -p "Enter second number: " num2

# Arithmetic operations using $(())
add=$((num1 + num2))
sub=$((num1 - num2))
mul=$((num1 * num2))
div=$((num1 / num2))   # Integer division

# Output results
echo "Addition: $add"
echo "Subtraction: $sub"
echo "Multiplication: $mul"
echo "Division: $div"

## output:
  Addition: 16
  Subtraction: 8
  Multiplication: 48
  Division: 3
  
## Task 4:
* [voting Eligibility]

## Explanation:
* [Input age - check if eligible to vote]


## command(s):
#!/bin/bash
echo "Enter your age: "
read age

if (( age >= 18 ))
then
    echo "You are eligible to vote."
else 
    echo "Sorry, you are not eligible to vote."
fi

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./42.sh
Enter your age: 
20
You are eligible to vote.
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./42.sh
Enter your age: 
15
Sorry, you are not eligible to vote.




## Experiment 5

## Task 5: Prime Number check
## Explanation:
* [Input Number - check if prime.]


## command(s):
#!/bin/bash


read -p "Enter a number: " num


is_prime=1


if (( num < 2 )); then
    is_prime=0
else
    
    for ((i=2; i<=num/2; i++))
    do
        if (( num % i == 0 )); then
            is_prime=0
            break
        fi
    done
fi


if (( is_prime == 1 )); then
    echo "$num is Prime"
else
    echo "$num is Not Prime"
fi

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./1.sh
Enter a number: 2
2 is Prime

## Task 6:
* [sum of digits]

## Explanation:
* [Input a number , calculate sum of digits.]


## command(s):
#!/bin/bash
echo "Enter the no"
read num
sum=0
while (( num > 0 ))
do 
digit=$((num % 10))
sum=$((sum + digit))
num=$((num / 10))
done

echo "sum of digits: $sum"

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./2.sh
Enter the no
1234
sum of digits: 10

## Task 7:
* [Armstrong Number check]

## Explanation:
* [check if number is Armstrong]


## command(s):
#!/bin/bash
echo "Enter a number: "
read num
temp=$num
n=${#num}   
while [ $temp -gt 0 ]
do 
    digit=$((temp % 10))
    sum=$((sum + digit**n))
    temp=$((temp / 10))
    done

    if [ $sum -eq $num ]
    then
    echo "$num is a armstrong."
    else
    echo "$num is not a armstrong."
    fi

## output:
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$ ./arm.sh
Enter a number: 
153
153 is a armstrong.
astik@DESKTOP-E06876A:/mnt/c/Users/HP/linux$
 ./arm.sh
Enter a number: 
123
123 is not a armstrong.

 ## Result
 * The exercise were successfully completed for basic and looping in shell scripting.