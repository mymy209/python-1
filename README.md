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


### Checking Data Type

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

### Integer Numbers (`<class 'int'>`)

If a number isn't followed by a decimal point, and integer (whole number) is assumed:

```python
type(25)
# <class 'int'>
```

### Floating-point Numbers (`<class 'float'>`)

Numbers with decimal.

```python 
type(3.14159)
# <class 'float'>

type(25.)
# <class 'float'>
```

### Complex Numbers (`<class 'complex'>`)

Python even has a data type for complex numbers, aka imaginary numbers. 

j = sqrt(-1)

```python
type(1 + 2j)

# <class 'complex'>
```

### Booleans (`<class 'bool>`)

Logical data types often used in conditional expressions.

```python
type(True)
# <class 'bool'>

type(False)
# <class 'bool'>
```

### Strings (`<class 'str'>`)

Strings are made up of ordered sequences of characters.

```python 
type('welcome')
# <class 'str'>

type(' ')
# <class 'str'>
```

### Nothingness (`<class 'NoneType`>)

None is not the same as 0, False, or an empty string. None is a datatype of its own (NoneType) and only None can be None.

```python
type(None)
# <class 'NoneType'>
```

We will go over rest of the data types next time!

## Intro to Functions

<img src="https://i.imgur.com/7l8ROFn.png">

Functions are great at "encapsulating" a task by combining many instructions into a single line of code. 
This make code easier to read, understand, organize, and follow the DRY principle of programming. (Don't Repeat Yourself)

There are two steps to creating a funtion: 
1. Declare and define the function
2. Call the function

Most of the times, data we use in applications are not static and mutate -- we use variables to store and handle these data!

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

### Concatination

Now let's get a little more creative: 

```python
print('Today is day ' + str(day) + ' of Python coding!')
print('Is ready to get coding: ' + str(ready))
```

You can concatinate (combine) words and variables, and print them all together in one single line!
However, concatination (and most operations) can be done only when the data types of each element is the same. 
To compensate this, we use the `str()` converts the data type (class type) to a string. 

Here are some conversions we can do when needed:

```python 
str(item)        # converts item to a string
int(item, base)  # converts the provided item to an integer with the provided base
float(item)      # converts the item to a floating-point number
hex(int)         # converts an integer to a hexadecimal STRING
oct(int)         # converts an integer to an octal STRING
tuple(item)      # converts item to a tuple
list(item)       # converts item to a list
dict(item)       # converts item to a dictionary
```

### String Interpolation

String interpolation evaluates Python expressions and embeds the result within strings. 
Its simple and short syntax can get convinient!
You just need to add an `f` before the string: 

```python
state = 'Hawaii'
year = 1959
message = f'{state} was the last state to join the U.S. in {year}.'
```

We can even "inject" the result of the expressions into the formatted string (f-String).

```python
template = 'My name is {} and I like {}'
print(template.format('Myra', 'tacos'))
# 'My name is Myra and I like tacos'
```

### Useful String Methods

There are many built-in methods for strings! 

```python
"ace of spades".split(" ")
# ['ace', 'of', 'spades']

# However, this won't work
"abcd".split("")

# Instead, use the list() function like this:
list("abcd")
# ['a', 'b', 'c', 'd']

"qqxzzz".index("x")  
# 2  
# Warning: Raises error if substring not found


"boo".upper()
# "BOO"

"WHY???".lower()
# "why???"

"Then I went to the store I like".replace("I", "you")
# 'Then you went to the store you like'

"eggs" in "green eggs and ham"
# True
# finds out if a string contains a substring
```

### Python's Built-in Functions

```python
len("Tacos")
# 5
# finds the length of sequence or collection 
#(more on these next time!)
```

Because string is a sequence, we can use square brackets to access the characters in the string (but not to assign them)

```python
course = 'Intro to Python'
print(course[0])
# 'I'

# we can ene use negative indexes!
last_letter = course[-1]
print(last_letter)
# 'n'
```

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

Control flow refers to the order in which code executes in a program as determined by the use of constructs in the code.

Control flow heavily relies on comparisons, evaluations, and mathmatical operations. Before we get into technical python control flow, let's learn about the basics of control flow in general programming. 

Like stated above, control flow comes down to different code paths executing according to the evaluation of conditional expressions. 

In other words, if the conditional expression evaluates to truthiness, do this, optionally, do something else. 

### Truthy & Falsey in Python

Conditional expressions for `if` statements etc, rely on an expression evaluating to `True`/**truthy** or `False`/**falsey** to deterimine which path the code will follow. 

Falsey values in Python:
- `False`
- `None`
- Zero in any numeric type: `0`, `0.0`, `0j`
- Empty sequences/collections:
    - `''` (empty string)
    - `[]` (empty list)
    - `()` (empty typle)
    - `{}` (empty dictionary)
    - `range(0)` (empty range) 

### Math Operators

- `+` (addition)
- `-` (subtraction)
- `*` (multiplication)
- `/` (division)
- `%` (modulo/remainder)
- `**` (exponentiation)

#### Integer Division

As a side note, double-slash will "floor" division (round down to the nearest whole number).

```python
print(5 // 2)
# 2
```

### Comparison Operators

- `<` (less than)
- `>` (greater than)
- `<==` (less than or equal)
- `>==` (greater than or equal)
- `==` (equal to)
- `!=` (not equal to)

```python
8 > 8
# False: 8 is not greater than 8.

8 >= 8
# True: 8 is greater than or equal to 8 (checks if 8 is greater than or equal to 8).

8 < 8
# False: 8 is not less than 8.

7 == 7
# True: 7 is equal to 7.

7 == "7"
# False: One is a number and the other is a string.

7 != 7
# False: 7 equals 7 (checks if they are NOT equal).

6 != 7
# True: 6 is not equal to 7.
# Note that in addition to the != operator, you can also use this for inequality

6 <> 7
# True: 6 is less than 7 (checks if 6 is less than or greater than 7).
```

### Logical Operators

#### `or` 

If the first operant is truthy, return it, otherwise return the second operand

#### `and`

If the first operand is falsey, return it, otherwise return the second operand.

```python
True or False
# True

False or True
# True

'hello' or 0
# 'hello'

0 or 'hello'
# 'hello'

True and False
# False

False and True
# False

'hello' and 0
# 0

0 and 'hello'
# 0

'hello' and 'tacos'
# 'tacos'
```

Generally, there are two types of control flow: 
- branching (`if`)
- looping (`for`
- jump (`return`)

### Branching

Branching allows us to run one of several code paths depending upon the result of conditional expression(s). 

Single path `if` statement:

```python
if condition: 
    # code block
```

<details>
<summary>Example</summary>
<p>

```python
shoe_lace = 'untied'
if shoe_lace == 'untied':
    print('Tie your shoe lace!')
```

</p>
</details>


Dual path `if..else` statement:

```python
if condition: 
    # code block
else:
    # code block
```

<details>
<summary>Example</summary>
<p>

```python
shoe_lace = 'untied'
if shoe_lace == 'untied':
    print('Tie your shoe lace!')
else:
    print('Happy feet :)')
```

</p>
</details>

Multi-path `if..elif..else` statement:

```python
if condition1:
    # code block
elif condition2:
    # code block
elif condition3:
    # code block
else: 
    #code block
```

Side note: `else` is always optional!

<details>
<summary>Example</summary>
<p>

```python
shoe_lace = 'untied'
if shoe_lace == 'untied':
    print('Tie your shoe lace!')
elif shoe_lace == 'tied':
    print('Happy feet :)')
else:
    print('Check your shoe lace!')
```

</p>
</details>

### Looping

`for` loop iterates (repeats) over the items in a sequence. 

We'll learn about sequences next workshop, but here is an example just to introduce the idea of it:

Loop through a **list**

```python
groceries = ['apples', 'eggs', 'milk', 'bread']

for item in groceries:
    print(item)

# 'apples'
# 'eggs'
# 'milk'
# 'bread'
```

`while` loop continuously iterates while a given condition is truthy.

`while` loops are great for when you don't know how many times you will need to iterate.

```python
while condition:
    # code block
```

## Jump

`return` is used to end the execution of the function and "returns" the result to the caller. 

Example:

```python
def subtract_nums(num1, num2):
    difference = num1 - num2
    return difference

print(subtract_nums(10, 5))

# 5
```

`break` can be used to immediately exit `for` and `while` loops and continue executing any statements that follow them. 

Example: 

```python
n = 5
while n > 0:
    n = n-1
    if n == 2:
        break
    print(n)
print('Loop is finished')

# 4
# 3
# Loop is finished
```

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











