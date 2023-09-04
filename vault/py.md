---
id: pmdwt5x60g5mr33op2h6hm5
title: Py
desc: ''
updated: 1690885514817
created: 1649553504669
---
# Python
https://en.wikipedia.org/wiki/Python_(programming_language)
https://docs.python.org/3/tutorial/controlflow.html

- Pythonic style means code that doesn't just get the syntax right but that follows the conventions of the Python community and uses the language in the way it is intended to be used. 
https://www.udacity.com/blog/2020/09/what-is-pythonic-style.html 
    - tuple unpacking using multiple assignment
    - list comprehensions
    
# Python Syntax
Name your classes and functions consistently; the convention is to use UpperCamelCase for classes and lowercase_with_underscores for functions and methods. Always use self as the name for the first method argument (see A First Look at Classes for more on classes and methods).
## Comments
- \#

## Console or Print
- print()

## Grouping and Indentation
Python uses indentation to determine how a line or group of lines is related to the rest of the program
- Blank lines group parts of program visually and organize files
- 4 space indentation
- < 80 chars per line
## Data Types
### Strings
    - series of characters
    - " " or ' ' >> "In the land's beginning"
### Numbers
- Integers
- Floats 
    - Get float when divide any 2 numbers
    - Get float when mix integer and float
    - Use _ like comma with large nums

## Lists
- index 
    - starts at 0
    - access element with []
- list - ordered coll of items, dupes allowed
    - [], separator: ,
    - mutable
- tuple - ordered immutable list, allows dupes
    - (), separator: ,
- set - unordered, unindexed, no dupes
    - {}, separator: ,
    - immutable
- dictionary - contains key value pair(s), dupes not allwed
    - {}, separator: ,
    - access using ['key_name']
    - mutable
    - ordered with 3.7+

### Objects

### Classes

## Math Operators
- Arithmetic: 
    - \+ \- \* 
    - division: /(float division) //(int division)
    - exponents **
    - modulo %

## Logical Operators
and, or, not

## = ==
- = assignment
- == compares by value; also `is`
- 

## Variables
- dynamic typing; vars cam subsequently be rebound at any time to any object. Var name is generic ref holder w/o fixed data type
- declare - Python has no command for declaring a var
- assign - Var is created when assigned val
- reassign 
### Var Naming Convention
    - can only contain letters, numbers, and _
    - can start with letter or _, not nums
    - spaces not allowed
    - avoid Python keywords and func names as var names
    - make short and descriptive

### Constants
- var whose val stays the same throughout the life of a program
- all caps
- snake_case

### Var Assignment
- declaring
- multiple assignment: x,y,z = 0,1,2
- reassignment

### String Interpolation
 - the process of evaluating a string literal containing one or more placeholders, yielding a result in which the placeholders are replaced with their corresponding values
- f-strings insert var's val into a s
- format() method for older versions of python3
``` python
f"{var_value} lives here"
f"How's life, {a_name}?"
full_name = "{} {}.format(first_name, last_name)
```

### Variable Scope

## Conditionals - Making Decisions
``` python
#
if conditional_test:
    do something indented

# if else for 2 possible situations. If want to test every true condition, use multiple ifs
if condition:
    do something
else:
    do something 

# if-elif-else runs until one test passes; optional else catches anything which isn't caught by preceding conditions
# elif substitute for case-switch or case statements, avoids indentation
if condition:
    do something
elif condition:
    do something
else condition:
    do something
```
### Shorthand If - Conditional Expression or Ternary Operator
`x if c else y` (Js: `c ? x : y`)
``` python
a = 330
b = 330
print("A") if a > b else print("=") if a==b else print("B")
```

## Loops
- for
``` python
magicials = ['timmy', 'nagata', 'elvi']
for magical in magicals:
    print(magical) # timmy nagata elvi

```
- while
``` python
while condition is true:
    do something
    flag, break or continue

```
- try


## Comparisons /Logical Operators
- comparisons
- booleans

## Functions
```python
def func_name(): #(params) function definition ends with :
    func body...
    print(...)

func_name('arg')
```
- return returns val from func
## Lambda Expression
- small anon function can take any number of arguments
- syntax:  lambda args: expression
- `lambda a : a * n`

## List Comprehensions
- Code one liners
- descriptive name = [expression for value in range(x,y)]

``` python
squares = [value ** 2 for value in range(1,11)]
print(squares) # [1,4,9,16,25,36,49,64,81,100]
```


## Functions (Methods)
- Python reference: https://www.w3schools.com/python/python_ref_functions.asp Built-in functions
- filter
``` python
ages = [5, 12, 17, 18, 24, 32]

def myFunc(x):
  if x < 18:
    return False
  else:
    return True

adults = filter(myFunc, ages)

for x in adults:
  print(x)


```
- map
    - syntax: map(func, i)
    - returns object. Can convert to list, tuple, etc
``` python
def myfunc(a, b):
  return a + b

x = map(myfunc, ('apple', 'banana', 'cherry'), ('orange', 'lemon', 'pineapple'))

print(x)
#convert the map into a list, for readability:
print(list(x))

# Return double of n
def addition(n):
    return n + n
 
# We double all numbers using map()
numbers = (1, 2, 3, 4)
result = map(addition, numbers)
print(list(result))
```
- reduce

- slice() 
    - `slice(start, stop, step)`
    - extended indexing syntax `a[start:stop:step]`
    
- enumerate()

- len()
``` python
>>> greeting = "Good Day!"
>>> len(greeting)
9

>>> office_days = ["Tuesday", "Thursday", "Friday"]
>>> len(office_days)
3

>>> london_coordinates = (51.50722, -0.1275)
>>> len(london_coordinates)
2
```
