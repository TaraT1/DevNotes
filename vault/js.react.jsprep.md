---
id: s2cmnxla5pycm5ku0caf8h6
title: Jspre
desc: ''
updated: 1718413868173
created: 1718393615287
---
Recommended info b4 React: 'tube [All The Javascript You Need to Know for React](https://www.youtube.com/watch?v=m55PTVUrlnA&t=286s)
## Functions
reference: [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
### Function Declaration or Function Statement 
``` javascript
function doSomething() {
...    
}
```
### Arrow Functions
Use arrow functions for cleaner code and better callback handling
``` javascript
//arrow function
varKeyword functionName = () {
    ...
}
// function expression - const, let, var
const doSomething = () => {
    ...
}

```
## Exporting Functions
- function declartion: 
``` javascript
export default function doSomething() {
    ...[]
}
```
- function expression 
``` javascript
export const doSomething = () => {
    ...
}

//React Component
const myComponent = () => {
    return <div>... </div>
}
```
### Anonymous Functions
- can execute commands without having to declare a function
``` javascript
//Js anon function 
<button onClick = {}>
</button>

//React - can execute commands without having to declare a function
<button 
    onClick={() => {
        console.log("Hi Vorld")
    }}
    ></button>
```

## Condtionals - Short Circuiting Operators and Ternary Operators
JSX - javascript in html. Cleaner and fewer lines of code
- short-circuit evaluation - an expression is evaluated from left to right until it is confirmed the remaining conditions will not affect the already evaluated result; leads to efficient processing
    - &&: ref: https://www.geeksforgeeks.org/javascript-short-circuiting/
        console.log(false && true) //false  
        console.log(true && true) //true
    - ||:  
        console.log(true || false) //true  
        console.log(false || true) //true
    
``` javascript
//
if (age > 10) {
    name = "Pedro"
} else {
    name = "Jack"
}
// with short circuit
let name = age > 10 && "Pedro" //Let name = "Pedro" if condition is true
let name = age > 10 || "Pedro" //??? not clear how to use here

// With ternary operator: 
let name = age > 10 ? "Pedro" : "Jack"

// React component
// UI changes based on state of application; chznges based on result of conditional
const Component = () => {
    return age > 10 ? <div> Pedro </div> : <div> Jack </div>
}
```

## Objects
- aka dictionaries (Python), hash tables, hash maps 
 
 ### Destructuring Objects
 ``` javascript
 const person = {
    name: "Pedro",
    age: 20, 
    isMarried: false,
 }
 // ## Creating var that represent specific values inside of object
 const name = person.name
 const age = person.age
 const isMarried = person.isMarried

// ## Make concise using destructuring property of objects
const { name, age, isMarried } = person //used a lot for working props

// ## Shorthand notation
const person = {
    name, //instead of name: name - when key of value pair has same name as variable (don't have to repeat var name)
    age,
    isMarried: false,
}

// Reuse & duplicate object with modifications (person)
const person2 = {...person, name: "Jack" } // Duplicate key-value pairs, with modification after the spread operator

// Arrays
const names = ["Pedro", "Jack", "Jessica"]
const names2 = [...names, "Joel"] //names + Joel; How manipulate and add elements to arrays inside of states
```
## Methods of Manipulating Arrays
.map()  
.filter()  
.reduce()  

```
let names = ["Pedro", "Jessica", "Carol"]

//could use for or forEach loop
//using map
names.map((name) => {
    return name + "1"
})

// In React, display list
names.map((name) => {
    return <h1> {name} </h1>
})

//Remove elements
let names = ["Pedro", "Jessica", "Carol", "Pedro", "Pedro"]
 names.filter((name) => {
    return name !== "Pedro"
 })
```

 ## Async + Await + Fetch
 - Working with APIs - promises and async await
 - Axios (a React library) is very similar to Fetch API

 

 