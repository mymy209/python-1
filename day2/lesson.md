<img src="https://i.imgur.com/hJuPCtz.jpg">

# Intro To Python Day 2

| Topics |
| --- |
| Sequences |
| Dictionaries |
| Sets |
| Advanced argument passing |

We will finish up learning the rest of the data types that we didn't cover last time!

<img src="https://i.imgur.com/EbTHZWV.png">

## Dictionaries (`<class 'dict'>`)

A dictionary provides a container for `key: value` pairs. 

### Basic Syntax

a dictionary is created using curly braces

```python
student = {
  'name': 'Myra', 
  'course': 'Intro to Python', 
  'workshop': 1
}
```

### Features 

Dictionaries are mutable:
- values assigned to a key can be changed
- additional items can be added
- existing items can be deleted

Any immutable type can e used as a key, including numbers and tuples. For example

```python
option = 3

d = {
  option: 'three'
}
```

The value of the `option` is "copied" as the key -- thus no "link" to the `option` variable is created. 

### Getting and Setting Values

We use square brackets to get and set an item's value:

```python
name = student['name']
print(name)
# Myra

student['name'] = 'Maria'
print(name)
# Maria
```

### The `get` Method

Note: When accessing a key that does not exist in a dictionary, a `KeyError` will be raised. 

One option to avoid this error is to use the `get` method:

```python
skills = student['skills']
> KeyError: 'skills'
print( student.get('skills') )
> None
# Provide a default value if key not in dictionary
print( student.get('skills', {'HTML': 5, 'JAVASCRIPT': 4}) )
> {'HTML': 5, 'JAVASCRIPT': 4}
```

### The `in` Operator 

We can use the  `in` operator to check if the dictionary includes a key:

```python	
if 'course' in student:
  print( f"{student['name']} is enrolled in {student['course']}")
else:
  print( f"{student['name']} is not enrolled in a course")
```

### Adding Items

Simply assigning to a key that does not exist will create a new item in the dictionary.

```python
student['age'] = 19
```

### Deleting Items

The `del` statement is used to delete an item from a dictionary:

```python
del student['age']

'age' in student
# False
```

### Number of Items

Use the built-in `len` function to retrieve the number of items in a dictionary:

```python
print( student )
# {'name': 'Maria', 'course': 'Intro to Python'}

len(student)
# 2

len({})
# 0
```

### Iterating Over Items

`for` loops are used to iterate over the items in a dictionnary. 

However, accessing the value of an item as follows is considered to be a Python [anti-pattern](https://en.wikipedia.org/wiki/Anti-pattern):

```python
for key in student:
  print( f"{key} = {student[key]}" )
```
	
The preferred approach is to use the `items()` method to obtain a [dictionary view object](https://docs.python.org/3/library/stdtypes.html#dictionary-view-objects).

`student.items()` returns a wrapped set of (key, value) tuples:

```python
student.items()
> dict_items([('name', 'Tina'), ('course', 'SEI')])
```

Then use a `for in` loop to iterate over the view object:

```python
for key, val in student.items():
  print( f"{key} = {val}" )
```

The `for` statement "unpacks" the tuples by assigning its values to multiple variables like with `key, val` above.

## Lists (`<class 'list'>`)

A list provides a container for 0 or more items (AKA elements). 

Lists can contain items of different types, including dictionaries and nested lists. 

### Basic Syntax

Lists can be created with a set of square brackets:

```python
colors = ['red', 'green', 'blue']
```

The number of items in a list can be found with the built-in `len()` function:

```python
len(colors)
# 3
```

### Features
- Type of sequence
- Ordered 
- Mutable
    - Items within a list can be replaced
    - Items can be added/removed from a list

### Accessing Items

We can access items of a list using square brackets with an expression that evaluates to an integer inside it:

```python
idx = 1
colors[idx + 1]
# blue

# we can also use negative integers to count backwards
colors[-1]
# blue
```

### Assigning Items

We also use square brackets for assignment:

```python
colors[-1] = 'purple'
print(colors)
# ['red', 'green', 'purple']

colors[0] = 'orange'
print(colors)
# ['orange', 'green', 'purple']
```

Note: assigning to a non-existing index will result in an error

### Adding an Item

We can use `append()` method to add an item

```python
colors.append('pink')
print(colors)
# ['orange', 'green', 'purple', 'pink']
```

To add multiple items, use `extend()` method

```python 
colors.extend('white', 'black')
print(colors)
# ['orange', 'green', 'purple', 'pink', 'white', 'black']
```

We can even combine lists to create a new one by using the `+` operator

```python
odds = [1, 3, 5]
evens = [2, 4, 6]
nums = odds + evens
print(nums)
# [1, 3, 5, 2, 4, 6]
```

We can add an item at specific index using `insert` method

```python
print(colors)
# ['orange', 'green', 'purple', 'pink', 'white', 'black']

colors.insert(1, 'yellow')
print(colors)
# ['orange', 'yellow', 'green', 'purple', 'pink', 'white', 'black']
```

### Removing an Item

We can use the `pop()` method to remove and return item at specific index (if not specified, it will remove the last item in the list)

```python
green = colors.pop(2)
print(colors)
# ['orange', 'yellow', 'purple', 'pink', 'white', 'black']
print(green)
# 'green'
```

We can also use the `del` operator to delete an item if we don't care the returned value

```python
del colors[1]
print(colors)
# ['orange', 'purple', 'pink', 'white', 'black']
```

There is also `remove()` method that removes the 1st matching item

```python
colors.remove('orange')
print(colors)
# ['purple', 'pink', 'white', 'black']
```

### Clearing an Entire List

The `clear()` method clears the entire list

```python
colors.clear()
print(colors)
# []
```

### Iterating Over Items in a List

The `for in` loop is used to iterate over the items in a list

```python
colors = ['red', 'green', 'blue']
for color in colors:
    print(color)
# red
# green
# blue
```

We can use the built-in `enumerate()` function to provide the index and the value

```python
for idx, color in enumerate(colors):
    print(idx, color)
# 0 red
# 1 green
# 2 blue
```

## List Comprehensions

List comprehensions are a powerful feature in Python.

They provide a concise way to create and work with lists. 

### Basic Syntax

```python
# [<expression> for <item> in <list>]
# This reads as: I want <expression> for each <item> in <list>
```

### Example 1

Say we needed to squal all of the numbers in a list and put them into a new list, we might use a for loop like this:

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
	
# I want 'n * n' for each 'n' in nums 
squares = []
for n in nums:
  squares.append(n * n)
print(squares)
# [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

A list comprehension can reduce this code to:

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

squares = [n * n for n in nums]
print(squares)
# [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

### Example 2

Say we want to create a new list with even squared numbers: 

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
	
even_squares = []
for n in nums:
  square = n * n 
  if square % 2 == 0:
    even_squares.append(square)
print(even_squares)
# [4, 16, 36, 64, 100]
```

Again list comprehensions can reduce this to:

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
	
even_squares = []

even_squares = [n * n for n in nums if (n * n) % 2 == 0]
print(even_squares)
# [4, 16, 36, 64, 100]
```

## Tuples (`<class 'tuple'>`)

Tuples are very similar to lists. 

### Basic Syntax

Tuples can be defined in a few different ways. Typically, they are defined with a pair of parentheses. 

```python
colors = ('red', 'green', 'blue')
parint(colors)
# ('red', 'green', 'blue')

print(len(colors))
# 3
```

Note: the parentheses are actually optional (except when creating an empty tuple). 

We can create an empty tuple!

```python
things = ()
print(type(things))
# <class 'tuple'>
```

If you need to create a typle with 1 item, comma is necessary

```python
fake_tuple = ('tuple')
print(type(fake_tuple))
# <class 'str'>

real_tuple = ('tuple',)
print(type(real_tuple))
# <class 'tuple'>
```

### Features

Tuples are immutable. 

Since tuples can't be changed after they are created, they are great for protecting data that you don't want to be changed. 

Python iterates over tuples faster than lists. 

Generally, you'll find that tuples are used to contain heterogeneous (different) data types and lists for homogeneous (similar) data types.

### Accessing Items

We can retrieve their items in the same way as lists using square brackets

```python
colors2 = ('red', 'green', 'blue')
green = colors[1]
print(green)
# green
```

Sequences (strings, lists, tuples) also have an `index()` method that returns the index of the 1st match

```python 
blue_idx = colors2.index('blue')
print(blue_idx)
#2
```

### Iterating Over Items in a Tuple

Items in tuples are iterated over by using `for` loops, just like how we did with lists

```python
for idx, color in enumerate(colors2):
  print(idx, color)
# 0 red
# 1 green
# 2 blue
```

### Unpacking Tuples

All sequences (strings, lists, tuples) have a convinient feature called **unpacking** for performing umtiple variable assignments in a single line of code

```python
r, g, b = colors2
print(r, g, b)
# red green blue
```

Comma separated variables on the left-side of the assignment operator and a sequence of values on the right is what it takes.






