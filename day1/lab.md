# Day 1 Practice Problems

These practice problems will help you get a better grasp of control flow, conditionals, and string methods!

Some probelms are from [Basic Python Probelms](https://pynative.com/python-basic-exercise-for-beginners/), you can find more problems there if you would like!

Some problems are from [w3resource string exercises](https://www.w3resource.com/python-exercises/string/), you can find more problems there if you would like!

As a reference, you can see useful string methods at [w3schools](https://www.w3schools.com/python/python_ref_string.asp)

### #1
Create a function called `multiplication_or_sum()` that
- accepts 2 numbers as parameters 
- return their product 
- if the product is greater than 1000, then return their sum
- print a message as:
    - The result is __

```python
multiplication_or_sum(10, 20)
# The result is 200
```

### #2
Create a function called `eve_idx_char()` that
- accepts a string as a parameter 
- print characters which are present at an even index number (0, 2, 4, 6...)

```python
eve_idx_char('python')
# p
# t
# o
```

### #3
Create a function called `find_count()` that
- accepts 2 string as parameters
    - 1st parameter is set to the word that we will be searching
    - 2nd parameter is set to the sentence/phrase that we will be searching the word from 1st parameter
- finds how many times the word is used in the sentence/phrase
- print a message as:
    - The word "__" is used in the sentece __ time(s)

```python
find_count('nice', 'nice people deserve nice things')
# The word "nice" is used in the sentece 2 time(s)
```

### #4
Create a function called `fibonacci()` that 
- calculates and prints the first 10 terms of the fibonacci sequence
- print each term and value as:
    - term: 0 / number: 0
    - term: 1 / number: 1
    - term: 2 / number: 1
    - term: 3 / number: 2
    - term: 4 / number: 3
    - term: 5 / number: 5
- note: the next number is found by adding the two numbers before it

```python
fibonacci()
# 0
# 1
# 1
# 2
# 3
# 5
# 8
# 13
# 21
# 34
```

### #5
Create a function called `exponent()` that 
- accepts 2 numbers as parameters
    - 1st parameter is set to base
    - 2nd parameter is set to exponent (power)
- print a message as:
    - (base) raised to the power of (exponent) is: (result)
- example) base = 2, exponent = 3; 2 raised to the power of 3 is: 8

```python
exponent(5, 4)
# 5 raised to the power of 4 is: 625
```

### #6
Create a function called `str_ends()` that
- accepts a string as a parameter
- makes and returns a string with first 2 and the last 2 chars from the parameter
- if the string length is less than 2, return an empty string instead

```python
print(str_ends('excellent'))
# exnt
```

### #7
Create a function called `replace_char()` that
- accepts a string as a parameter
- returns a string where all occurrences of its first char have been changed to '$' except the first char itself

```python
print(change_char('characteristic'))
# chara$teristi$
```

### #8
Create a function called `add_str()` that
- accepts a string as a parameter
- adds 'ing' at the end of a given string
- if the given string already ends with 'ing' then add 'ly' instead 
- if the string length of the given string is less than 3, leave it unchanged

```python
print(add_str('exciting'))
# excitingly
```

### #9 
Create a funtion called `even_idx()` that 
- removes the characters which have odd index values of a given string
- returns the resulted string

```python 
print(even_idx('abcdefg'))
# aceg 
```

### #10
Create a funtion called `delete_all_occurances()` that 
- accepts 2 strings as parameters
    - 1st parameter is what we are using to search in
    - 2nd parameter is what we are trying to delete and look for its occurance in 1st parameter
- deletes all occurrences of specified characters and returns the resulting string
- make sure uppercase/lowercase does not matter (make it case insensitive)

```python
print(delete_all_occurrences('You are your own person', 'yo'))
# u are ur own person
```

Sample answers can be found [here]!(https://repl.it/@mymy209/Day-1-Practice#main.py)