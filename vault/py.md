---
id: pmdwt5x60g5mr33op2h6hm5
title: Py
desc: ''
updated: 1689256613878
created: 1649553504669
---
# Python
# Python Syntax

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
- Arithmetic: 
    - + - * /
    - exponents **

### Objects

### Classes

## Math Operators

## Variables

### Var Naming Convention
    - can only contain letters, numbers, and _
    - can start with letter or _, not nums
    - spaces not allowed
    - avoid Python keywords and func names as var names
    - make short and descriptive

### Constants
- var whose val stays the same throughout the life of a program
- all caps

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
```
if

if else
```
## Lists
- index 
    - starts at 0
    - access element with []
- list - ordered coll of items
    - [], separator: ,
    - mutable
- tuple - immutable list
    - (), separator: ,
- dictionary

## Loops
- for
``` python
magicials = ['timmy', 'nagata', 'elvi']
for magical in magicals:
    print(magical) # timmy nagata elvi

```

## Comparisons /Logical Operators
- comparisons
- booleans

## Functions

## List Comprehensions
- Code one liners
- descriptive name = [expression for value in range(x,y)]

``` python
squares = [value ** 2 for value in range(1,11)]
print(squares) # [1,4,9,16,25,36,49,64,81,100]
```
