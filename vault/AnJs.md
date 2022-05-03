---
id: 6ihj6c14gk9fzy4mm96cy9q
title: Javascript 
desc: 'Leon class 12, 13'
updated: 1651440308731
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
- var is now  old-school

## Functions
- A function is a block of organized, reusable code that is used to perform a single, related action. 
- main building blocks of a program, where code can be called many times without repetition

### Function declaration
```javascript
function name(parameter1, parameter2... parameterN) {
  ... body ...
}
//call
name(arguments)
```
- function is invokved by its name
- local variable - variable declared inside a function is only visible within that function
- function can access outer variable and can modify

### Parameters
- where pass data to functions
- argument - value passed to function when it is called (call time term)
- declare functions listing their parameters and call them when passing arguments

### Returning a Value
- A function can return a value back into the calling code as a result
- Return without value is possible - function exits immediately
- function with empty return or without it returns undefined
- avoid enter between return and value
``` 
return (
  ...
)
```

### Naming a function
- functions are actions => verb
- function prefixes: 
  - get - returns value
  - calc - calculates something
  - create - creates something
  - check - checks something, returns bool

### functions === comments
- functions should be short and do one thing
- functions can act like self-describing code by structuring and making it more readable 

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

## Pseudocode
- coding in conversational language to solve problems
- transferrable to other languages

## Useful Js
  ``` javascript
  //event listener - mouse enter, double click 
  document.querySelector('#check').addEventListener('click', functionToRun)

  document.getElementById('purple').onclick = makePurple
  
  //functions to make color => white
  function makePurple() {
      document.querySelector('body').style.backgroundColor = 'rgba(241,63,247,1)' 
      document.querySelector('body').style.color = 'white'
  }
  //query selector - pulls data out of DOM
  let assignedVar = document.querySelector('#day').value
  
//place text in DOM
document.querySelector('h2').innerText
  
//Enter input
const input = document.querySelector('#myInput');
input.addEventListener('keyup',function(e){
    if (e.keyCode === 13) {
    alert('hi');
  }  
});

input.addEventListener('click',function(){
  alert('you clicked me!');
});



  
  ```
  
## Loops
- repeat an action x number of times
- Js types include for, while, do
- each type offers a different way to determine start and end points of a loop
  ### For Loops
  ```
  for ([initialExpression]; [ conditionExpression]; [incrementExpression]){
    //do stuff
  }
  
  for (let i = 1; i < 5; i++) {
    console.log(i)
  }
  ```

  

  
  
  