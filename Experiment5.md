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
<img width="960" height="540" alt="2025-11-15 (50)" src="https://github.com/user-attachments/assets/77986577-74d5-4afb-a72e-ccc8e3ae3b4a" />

## Exercise 4: 

## Task 1:
* [First Script]

## Explanation:
* [Write a script that prints Hello,World!]

## command(s):
#!/bin/bash
echo "Hello, World!"

## output:
  <img width="960" height="540" alt="2025-11-15 (51)" src="https://github.com/user-attachments/assets/9971e6d9-e683-4605-8149-aab8060fd75c" />

  
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
<img width="960" height="540" alt="2025-11-15 (52)" src="https://github.com/user-attachments/assets/6aa21525-b21c-424a-93fe-27dfefd8c07c" />

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
 <img width="960" height="540" alt="2025-11-15 (53)" src="https://github.com/user-attachments/assets/e25944c8-0fea-4ea3-aaf8-3d035a81135c" />

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
<img width="960" height="540" alt="2025-11-15 (54)" src="https://github.com/user-attachments/assets/8af87fac-7fc8-4b7f-939c-e8b30f3e8b6b" />




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
<img width="960" height="540" alt="2025-11-15 (55)" src="https://github.com/user-attachments/assets/456ba4e9-d42e-4dce-9c35-9fcf29f43e15" />

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
<img width="960" height="540" alt="2025-11-15 (56)" src="https://github.com/user-attachments/assets/59ff43ad-33ee-4d33-b18b-be6b0172d595" />


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
<img width="960" height="540" alt="2025-11-15 (50)" src="https://github.com/user-attachments/assets/5b941a1b-9f0e-4e54-994a-841090fefbe4" />


 ## Result
 * The exercise were successfully completed for basic and looping in shell scripting.
