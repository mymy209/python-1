<img src="https://i.imgur.com/CflwUfS.jpg">

# Intro to Python Day 3

| Topics |
| --- |
| Classes |
| Methods |

## Review Python

Python is an object-oriented programming language (OOP).

OOP is characterized by use of objects that are great at encapulation. **Encapsulation** is the bundling of related properties (attributes) and methods (behavior) together in an object.

To create objects, we use **classes**. 

Remember when we used the `type()` function, it always returned `<class ___>`?
That means that every variable or data is an object. They have properties and/or methods encapsulated within.

To check these properties and/or mathods, we can use the `dir()` function

```python
nums = [1, 2, 3]
print(dir(nums))
# ['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
```

The methods that start and end with double-underscores are called [magic (or dunder) methods](https://rszalski.github.io/magicmethods/).

### Writing a Basic Python `class`

To get started with classes, let's define a `Dog` class to create doggies form

```python
class Dog(): 
    def __init__(self, name, age = 0):
        self.name = name
        self.age = age

    def bark(self):
        print(f'{self.name} says woof!')

# naming convention for Python classes is UpperCamelCasing :)
```

Python automatically calls the `__init__` magic method when a new dog is created. 

`__init__` is short for "initialize" because the method is used to initialize the properties of the new object. 

### `

