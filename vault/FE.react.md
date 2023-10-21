---
id: 52anmgl8a3a2b30i5q62n56
title: react
desc: ''
updated: 1727053396475
created: 1679962485382
---

Refs: [React dox](https://react.dev/learn)  
js syntax: mdn and javascript.info

React apps are made out of components
- component - a piece of UI that has its own logic and appearance (e.g. button)
- React components are js funcs that return markup
    - start w capital letter (html tags are lowercase)
    
    
# React
- Javascript library used to build reusable and scalable UI components that offer real-time functionality and modularity
- facebook
- minimizes page reloads; primarily aims to provide speed, simplicity, and scalability
- Composition model; Component based architecture, unidirectional data flow, virtual DOM
- better choice for projects that need to handle large data sets and be highly interactive
- JSX
- React Native is foundation block for building mobile apps



### React as framework or library
[React is going from library to framework](https://www.robinwieruch.de/learning-react/?utm_source=reactdigest&utm_medium&utm_campaign=1593)
- new dox point to React as framework
## React Fundamentals
[Elements](https://www.robinwieruch.de/react-element-component/), 
[React Hooks](https://www.robinwieruch.de/react-hooks/), 
[Custom Hooks](https://www.robinwieruch.de/react-custom-hook/), 
[Function Components](https://www.robinwieruch.de/react-function-component/), 
[Event Handlers](https://www.robinwieruch.de/react-event-handler/), 
[Forms](https://www.robinwieruch.de/react-form/), 
[Refs](https://www.robinwieruch.de/react-ref/), 
[Conditional Rendering](https://www.robinwieruch.de/conditional-rendering-react/), [Props](https://www.robinwieruch.de/react-pass-props-to-component/) before integrating complementary third-party libraries like [React Testing Library](https://www.robinwieruch.de/react-testing-library/) or [Styled Components](https://www.robinwieruch.de/styled-components/) (or any other [React styling solution](https://www.robinwieruch.de/react-css-styling/)).

When learning React as a framework, the biggest bet would be learning [Next.js](https://nextjs.org). It comes with file-based routing, many rendering techniques (CSR, SSG, ISR, SSR) with SSR as the first-class citizen, built-in image, SEO, and font support. It also comes as close as it gets to using React in a framework, because it collaborates heavily with React on features like React Server Components. In addition, many React core developers are now working for Vercel, the company behind Next.js.

[WDS](https://www.youtube.com/watch?v=Rh3tobg7hEo)  
React - library for web and native user interfaces  
- components - write with code and markup
- add interactivity (onChange)

### Think in React
- what is final version going to look like. Break into components
- break UI into component hierarchy

- js is imperative. do this then this then this. (recipe w instructions)
- React is declarative programming. (sammich from sammich shop. Name what is wanted)
- jsx

### Starting  Project
create react app: ```npm create vite@latest```
choose javascript svc (slightly faster) or javascript
npm install (npm i)
npm run dev

React todo list  
https://github.com/WebDevSimplified/react-todo-list

- fragment <>...</>
- state - useState
- destructuring (js) 

### Resource
- https://egghead.io/courses/the-beginner-s-guide-to-react

## Js Needed for React
from PedroTech https://www.youtube.com/watch?v=m55PTVUrlnA

### Arrow Functions
- declarative function:   
    ```function doSomething(){...}```
    - export: export default function doSomething...
    
- arrow function:  
    ```const doSomething = () => {...}```
    - export const doSomething...

- In React, define components, which are functions that take in props and return html  
    ```javascript
    const MyComponent = () => {
        return <div> </div>
    }
    ```
### Anonymous Functions
- 
```html
<button onClick={}>//pass name of function in {} with js
</button>
```
- with React can pass name of function in {} or can create anon func

```js
<button 
    onClick={() => {
        console.log('Hey Now')
        }}
></button>
```
- with React can pass name of function in {} or can create anon func
- Allows execute commands without declaring function

### Conditionals
- jsx
- minimize code using UI

#### Short Circuit Evaluation Using Logical Operators || and &&
```js
let age = 16
let name = age > 10 && "Pedro" //let name = "Pedro" if condition is true
// x || y returns first arg that is truthy or the last arg
// x && y returns first arg that is falsy or the last arg
```
#### Ternary Operator
```js
// condition ? truthy : falsy
let name = age > 10 ? "Pedro" : "Jack"

const Component = () => {
    return age > 10 ? <div> Pedro </> : <div> Jack </div>
}
``` 
### Objects
dictionaries
#### destructuring objects - use for brevity
```js
const person = {
    name: "t",
    age: 61,
    isMarried: true,
}

const name = person.name
const age = person.age
const isMarried = person.isMarried

//using destructuring
const {name, age, isMarried} = person
```
#### Shorthand for object key and variable /value pairs
```
//Vars = var in objects
const name = "t"
const age = 61

const person = {
    name, //shorthand notation for name(key): name(variable /value)
    age, //age(key): age(var)
    isMarried: true
}
```
#### Spread Operator in Objects and Arrays
```js
//Object
const person = {
    name: 't',
    age: 61,
    isMarried: true
}

const person2 = {...person, name: "t2"} //Changes name value in person object; Keeps other values of object

//Array
const names = ['a', 'b', 'c']
const names2 = [...names, 'd'] //Can use to add and manipulates arrays inside of states 
```
### Important Array Methods to know
- .map()
- .filter()
- .reduce()

```js
let names = ['a', 'b', 'c']

names.map((name) => {
    return <h1> {name} </h1>
}) //Generates header for each name in list

let names = ['Pedro', 'Jessica', 'Carol', 'Pedro', 'Pedro']
names.filter((name) => {
    return name !== 'Pedro'
})//names = ['Jessica', 'Carol']
```
### Async + Await + Fetch
- Axios is a React api

PedroTech js for React https://www.youtube.com/watch?v=ACaT1Gfhe6I&t=0s
### DOM
Document object Model - representation of web page js can interact with. Tree-like structure with nodes js can interact with. 
- React creates virtual representation of the DOM. Uses jsx. Html goes inside the jsx.
### Import/Export
React: `import axios from "axios"`


