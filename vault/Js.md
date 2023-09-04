---
id: 6ihj6c14gk9fzy4mm96cy9q
title: JS
desc: 'Leon class 12, 13'
updated: 1654059401631
created: 1650508492016
---

# Reference (homework): 
- [Js variables] (https://javascript.info/variables) 
- [Js functions] (https://javascript.info/function-basics)

# Programming
- computer does what you tell it to do
- program - set of instructions you write to tell computer what to do
- programming is the task of writing instructions in a language computer can understand

## basic logic - off, on is universal 
- 0, 1  
    - logic gates
    - low level computer language computer can understand

- Book to check Code the Hidden Language of Computer Hardware and Software - Charles Petzold
- Independence Day - 0 1 to reverse engineering
- build upload boom (Independence Day)

## DOM - document object model
- data representation of objects that comprise the structure and content of a document of the web

!!!no copying and pasting code

## IDs
- Used for selecting distinct elements
- 1 id with same value per document
  ``` css
  #zebra {
    color: red;
  }
  ```

## Classes
- Classes are used for selecting multiple elements
- Multiple items with same value are allowed per document
  ``` css
  .bob {
    color: red;
  }
  ```
  
## Play, Break, Delete, Repeat
- event listener
- value out of input
- something into DOM

When learning programming language:
1. variables
2. conditionals
3. functions
4. loops

# Variables
- label used to store value (named storage for data)
- declaration - creates space in memory
  - variable declared more than once triggers error
- assignment -  assigned value
- reassignment - changing variable value (does not use let)
- naming convention: camelCase
  ○ 1st word lowercase rest first letter of word capitalize

``` script
let <var name>; //declares var - declaration, creates space in memory
<var name> = ??? //assign - assignment

let name = 'John';

//one line for multiple variables - not recommended because of readability
let user = 'John', age = 25, message = 'right';

//multi-line
let user = 'John',
    age  = 25,
    message = 'right'; 
    
//comma style
let user = 'John'
    , age = 25
    , message = 'right';
```

### Var Scope
- let - block scope, can change
- const - global, unchanging
  - global variables are declared outside of any function
  - visible from any function unless shadowed by locals
  - capital-named constants are only used as aliases for “hard-coded” values. (Values are known prior to execution)
  ```const BIRTHDAY = '05.02.1963';
- var is now  old-school

## Strings
- " or ' surrounded text
- \ - used to escape 
- \t - tab
- \n - new line

## Numbers
- Numbers represent numerical data
- integers, floats (nums w decimal places)
- signed numbers - positive and negative

### Arithmetic in Js
- \+ - * / %

    ```
    let age = 25
    age = 30 //reassignment
    age = age +5
    age += 10
    ```

- Js can manipulate dom in real time

# II Conditionals - Making Decisions
- comparisons: equality ===
- booleans 

## Comparisons /Logical Operators 
- = 
- = is assignment
- == value
- === value and type comparison
- !=
- !== - value & type
- \>
- <
- \>=
- <=

## Conditionals
``` javascript
if (condition is true) {
  //do some shit
} else if (condition is true) {
  //do some other cool shit
}else{
  //default
}
```

## Multiple Conditions
- && - and - both sides have to be true
- || or - 1 has to be true

### ? operator - Ternary Operator
```
condition to test ? value if true : value if false
```

### ?? operator - Nullish Coalescing Operator
- provides a way to deal with null and undefined values
```
a ?? b
\\if a is defined, then a
\\if a isn’t defined, then b
```


## Pseudocode
- coding in conversational language to solve problems
- transferrable to other languages
- test while implementing
