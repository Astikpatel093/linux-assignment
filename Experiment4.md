## Experiment [4]: [BASH or SHELL scripting]
### Name: Astik Patel, Roll No.: 590029070 Date: 2025-09-04

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
```

#### output:
Hello world!
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
```

## output:
Enter the name.
Astik
Hello, Astik! Welcome to shell scripting.

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
Enter first number
1
Enter second number.
2
Addition: 3
substraction: -1
Multiplicatin: 2
Division: 0


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
Enter your age: 
18
Sorry, you are not eligible to vote.

## Result
* The exercise were successfully completed for basic shell scripting.
