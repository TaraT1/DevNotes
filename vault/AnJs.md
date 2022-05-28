---
id: 6ihj6c14gk9fzy4mm96cy9q
title: Javascript 
desc: 'Leon class 12, 13'
updated: 1653588430795
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

  
  ```
  


# Functions
- A function is a block of organized, reusable code that is used to perform a single, related action. 
- main building blocks of a program, where code can be called many times without repetition
- functions are values. They can be assigned, copied, or declared in any piece of code

## Function Declaration
- holds space for function in memory
```javascript
function name(parameter1, parameter2... parameterN) {
  ... body ...
}
//call - I call my mom to argue
name(arguments)
```
- function is invokved by its name and arguments
- local variable - variable declared inside a function is only visible within that function
- function can access outer variable and can modify
- can be called before defined and is visible everywhere
- in strict mode, function declaration is visible inside code block, but not outside of it

### Parameters
- where pass data to functions
- argument - value passed to function when it is called (call time term)
- declare functions listing their parameters and call them when passing arguments

### Returning a Value
- A function can return a value back into the calling code as a result
- Return without value is possible - function exits immediately
- function with empty return or without it returns undefined
- avoid enter between return and value, Js assumes ; after return
``` 
return (
  ...
)
```

```
//template literal - ${}
alert('${someVar1} insert variables into ${someVariable} ')
//old school used concatenate
alert( +  )
```
### Naming a function
- functions are actions => verb
- function prefixes: 
  - get - returns value
  - calc - calculates something
  - create - creates something
  - check - checks something, returns bool

### functions == comments
- functions should be short and do one thing
- functions can act like self-describing code by structuring and making it more readable 

## Function Expresssions
- function expressions create new function in the middle of any expression
```
let sayYo = function() {
	alert( "Hello");
}
```
- anonymous function
- terminates with ; (function declarations do not)
- function expressions are created when execution reaches them
  
## Function expression vs function declaration
- function declaration gives more freedom in organizing code and is better for readability
- if need conditional declaration, function expression should be used

## Callback Functions or Callback
- pass function and expect it to be called back later

## Arrow Function
- simple, concise syntax for creating functions
```
let func = (art1, arg2, ..., argN) => expression; //accepts args, evaluates expression, returns result

//instead of function expression:
let func = function(arg1, arg2, ..., argN) {
  return expression;
}
```
- if one argument, () can be omitted
- if no argument, () required
- multiline arrow functions
  - enclose in {}
  - return within {} required

```
let sum = (a,b) => {//curly brace opens multiline func
  let result = a + b;
  return result; //need explicit return inside curly brace
};
alert( sum(1,2));//3
```

# Loops
- repeat an action x number of times
- Js loop types include for, while, do
- each type offers a different way to determine start and end points of a loop
- reference https://github.com/thejsway/thejsway/blob/master/manuscript/chapter04.md
- loops are used to repeat a series of statements
- iteration - each repetition the code runs
- body - code block associated with a loop

## While loop
- repeats code while certain condition is true
- condition of while loop must eventually become false to avoid risk of infinite loop
- use when number of times code should run is not known (like when depending on user interaction)
```
//While loop
while (condition) {
  //code to run while condition is true
  //increment counter
}

let count = 0

while(count < 5){
  console.log(count)
  count++
}

```

## For loop
- updating counter of a for loop inside body is a bad idea - loop will iterate twice
- for loop is best choice when  know in advance # times loop is to run
- loop counter - var used during initialization, condition, and final expression; often named i
```
//for loop
for (initialization; condition; final expression) {
  //code to run while condition is true
}

for (let i = 1; i < 5; i++ ){
  console.log(i)
}
```
- initialization - happens once, sets initial value of loop counter
- condition - evaluated before loop runs; if true, code runs; if false, code doesn't run
- final expression - evaluated after loop runs; often updates counter

# Arrow functions (Leon Office Hours 3.20.22)
```
document.querySelector('h1').addEventListener('click', functionName anon function [function()] or [arrow function] or [reference to another] )

const example = function(){
  
}

const example = (x,i) => { console.log(x,i) }

```
- parenths for parameters are optional if 1 or no params
- {} if one line is optional
- return implicit to right of the arrow

```
let pokemon = ['bulbasaur', 'ditto', 'mew']

let favPoke = pokemon[0]

pokemon.forEach( (x,i)=>console.log(x) )

```

# Built-in Methods for Arrays - Map, forEach
## Map
```
let nums = [10,20,30]

let robotNewArr = nums.map( n => n += 10 ) //will run 3x w 3 elements in nums array

//Values stored in robotNewArr
n => 10 += 10 // 20
n => 20 += 10 // 30
n => 30 += 10 // 40

```
- map creates a new array
- map can take other functions

```
let months = ['Jan', 'Feb', 'mar']

let lowerCaseMonths = months.map( m => m.toLowerCase() )

console.log(lowerCaseMonths)
console.log(months)
```
- original array is untouched