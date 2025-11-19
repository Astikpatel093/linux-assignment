## Experiment [4]: [BASH or SHELL scripting]
### Name: Astik Patel, Roll No: 590029070 Date: 2025-09-04

### AIM:
* [To learn Basics of Bash Scripting]

### Requirements:
* [Any Linux Distro, any kind of text editor (vs code, vim, notepad, nano, etc)]

### Theory:
* [learning the basics of bash scripting.]

## procedure & observations

## Exercise 1: [Hello World script]

## task statement: 
* [basic usage of shell scripts]

## Explanation:  
* [writing Begginer level shell scripts]

## command(s):
```
#!/bin/bash
echo "Hello world!"


#### output:
<img width="960" height="540" alt="2025-11-15 (51)" src="https://github.com/user-attachments/assets/083a27a0-28bc-40e5-a5ee-68a2dcb3dc33" />

# Exercise 2: [personlized Greeting script]

## Task statement:
* [Basic Shell script to callout user defined funtion.]

## Explanation:
* [This shell sricpt take input from the user store it in a variable and then call the variable which will give the output as the stored value.]

## command(s):
```
#!/bin/bash
echo "Enter the name."
read name  #'read'takes user input 
echo "Hello, $name! Welcome to shell scripting."

## output:
<img width="960" height="540" alt="2025-11-15 (52)" src="https://github.com/user-attachments/assets/7d280512-dc12-4889-8909-4831686f91a7" />


## Exercise 3: [Arithmetic operations in shell scripts]

## task statement: 
* [basic usage of shell scripts]

## Explanation:  
* [This shell sricpt take input from the user store it in a variable and then call the variable which will give the arithmetic operation output as value.]

## command(s):
```
#!/bin/bash
echo "Enter first number"
read num1
echo "Enter second number."
read num2

echo "Addition: $((num1+num2))"
echo "substraction: $((num1-num2))"
echo "Multiplicatin: $((num1*num2))"
echo "Division: $((num1/num2))"


## output:
<img width="960" height="540" alt="2025-11-15 (53)" src="https://github.com/user-attachments/assets/5058221a-13fb-401f-b3bd-b2f602d94fc2" />



## Exercise 4: [voting]

## task statement: 
* [basic usage of shell scripts]

## Explanation:  
* [This shell sricpt take input from the user store it in a variable and then checking the condition which will lead to the output according to the condition whether it is true or false]

## command(s):
```
    #!/bin/bash
    echo "Enter your age: "
    read age

    if (( age > 18))
    then
    echo "You are eligible to vote."
    else 
    echo "Sorry, you are not eligible to vote."
    fi
## output
<img width="960" height="540" alt="2025-11-15 (54)" src="https://github.com/user-attachments/assets/ea7da6ed-8f59-4ff0-af2c-ca4437a5fc6c" />


## Result
* The exercise were successfully completed for basic shell scripting.
