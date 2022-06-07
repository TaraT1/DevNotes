---
id: 77z1hygtl1q29yha1kndept
title: functions
desc: ''
updated: 1654200300595
created: 1653421978749
---
# Functions
- A function is a block of organized, reusable code that is used to perform a single, related action. 
- main building blocks of a program, where code can be called many times without repetition
- functions are values. They can be assigned, copied, or declared in any piece of code

## Function Declaration
- holds space for function in memory
```
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
- comment 
  - single line //
  - multiple lines /* */

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
- function declarations are not part of reguarl top to bottom flow of control. They are conceptully moved to top of their scope and can be used by all the code in tat scope
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

