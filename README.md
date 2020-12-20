<img src="https://i.imgur.com/IjMC9s2.png" width=20%>

# Intro To Python Day 1

| Topics |
| --- |
| Datatypes |
| Basic Functions |
| Control Flow |

## Overview

Python is a OOP language that was created and released in 1991. It is known as a high-level interpreted programming language, which is designed for writing applications.

Python is a dynamic scripting language that does not have to be compiled to machine code before it can be executed (Assembly, C, C++) - it runs within an interpreter that handles the conversion into machine code.

Python comes with a large standard library and is suitable for many types of programming tasks from web development to machine learning.

However, if Python does not include functionality that you need, there is a huge repository, the [Python Package Index](https://pypi.org/), with over 169,000 third-party packages available for use.

## To get started

Python is usually installed into machines/computers when programming applications, but we will be using an in-broswer IDE called [repl.it](https://repl.it/) to prevent setup complications.

Let's dive right into learning Python!

## Data Types 

<img src="https://i.imgur.com/EbTHZWV.png">
<br>
As shown in the tree chart, Python has 5 main data types which each contains more specific kinds within it. 
For today, we will learn about integer, float, boolean, and string data types. 


## Checking Data Type

We can use the `type()` python built-in function 

```python
type(1)
# <class 'int'>

type('hello')
# <class 'str'>

type(True)
# <class 'bool'>

# anything typed after # or """ will be commented out 
```

## Intro to Functions

<img src="https://i.imgur.com/7l8ROFn.png">

Functions are great at "encapsulating" a task by combining many instructions into a single line of code. 
This make code easier to read, understand, organize, and follow the DRY principle of programming. (Don't Repeat Yourself)

There are two steps to creating a funtion: 
1. Declare and define the function
2. Call the function

Most of the times, data we use in applications are not static and mutate -- we use variables to make it easier to handle these data!

Just to get started, let's declare some variables
```python
teacher = 'Myra'
day = 1
ready = True
```

One of the most useful tool in coding is using a console -- it is a text-only computer interface that comes in handy to check what is going on when the application/code is running. 
`print()` is a built-in function to make whatever in the parameter print out in the console. 

Let's mess with the `print()` a little bit: 

```python
print('hello')
print(1 + 2)
print(teacher)
```

Now let's get a little more creative: 

```python
print('Today is day ' + str(day) + ' of Python coding!')
print('Is ready to get coding: ' + str(ready))
```

You can concatinate (combine) words and variables, and print them all together in one single line!
However, concatination can only be done when the data types of each element is the same. 
To compensate this, we use the `str()` converts the data type (class type) to a string. 


There are many built-in functions that complete specific tasks, but most of the times we code custom functions to do whatever we need to do!

### Exercise 1

Create a function called `add_nums()` that
- takes 2 numbers as parameters
- returns the sum of 2 numbers

<details>
<summary>Bonus</summary>
<p>

Create a function called `add_nums2()` that
- prompts 2 numbers 
- returns the sum of 2 numbers

</p>
</details>

## Control Flow

### Exercise 2

Create a function called `signal()` that 
- prompts what color the signal is
- prints a message depending on color inputted: 
    - green --> 'Go!'
    - yellow --> 'Yield!'
    - red --> 'Stop!'
    - anything else --> 'Bummer...'

<details>
<summary>Bonus</summary>
<p>

Make it case insensitive!
- e.g) Green, GREEN, grEeN, green would be all the same 
Side note: google is your bestfriend :)

</p>
</details>

The message returned would change based on the input; 

green --> "Go!"

yellow --> "Yield!"

red --> "Stop!"

anything else --> "Bummer..."







