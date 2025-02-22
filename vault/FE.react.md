---
id: 52anmgl8a3a2b30i5q62n56
title: react
desc: ''
updated: 1750967848148
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

//Example: setting color of button
let color = "green"
let isCorrect = false

color = isCorrect ? "green" : "red"
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
#### Fetch
- ? - will only try to access key in object if it exists
```js
const fetchData = async () => {
    const data = await fetch("imaginaryapi.com")
    const name = data.person?.name //? -if doesn't exist, will not try to access and will not break app
}
```

PedroTech js for React https://www.youtube.com/watch?v=ACaT1Gfhe6I&t=0s
### DOM
Document object Model - representation of web page js can interact with. Tree-like structure with nodes js can interact with. 
- React creates virtual representation of the DOM. Uses jsx. Html goes inside the jsx.
### Import/Export
React: `import axios from "axios"`

### Template Literals

```
const fetchData = async (animalName) => {
    const data = await fetch("imaginaryapi.com/searchterm=???+animalName") //not sure what would be here to be replaced by template literal 
    const name = data.animal?.name

    const dataUpdate = await fetch(`imaginaryapi.com/searchterm=${animalName}`)
}
```
### More advanced js concepts
- closure - callback function accesses outer function's scope even after execution
    - Example: custom hook in React
- currying - take function with multiple arguments and separating each arg into single function. Makes code cleaner, more modular, and more reusable
- memoization - use memo hook and use callback hook; 
    - Deprecated for new usage. In use in codebases.


## React Roadmap
[How To Learn React In 2024 - React Roadmap](https://www.youtube.com/watch?v=bBuaKlv56P0)


- understand why and what React is used for
    - developed by fb 
### Beginner, Build
-  Use vite, create react app is obsolete
-  jsx; (vs html); functional components, props, how to reuse components, why divide project into different components
-  handle user inputs inside app 
- what is reuse state hooks

### More advanced beginner:  (few weeks)
- Conditional rendering (!important)
- how to use lists -using map function and displaying list (using component); 
- how to handle form in app - get data, how to submit, how to put into states
- CSS in react - inline styling, import css file

### Intermediate: (month)
- use state
- use effect hook
- life cycle methods
- state mgt with use context hook and context api as a whole
- how to make website with multiple routes using react route or dom. Build site
- fetch data from api and display in screen. External libs: Check out react query, fetch api, use effect hook
- Build projects. Refer to docs and AI as learning 
### Advanced 
- remaining useful hooks. use graph hook?
- complex state mgt (react query)
- optimizing for performance
- best practices
- ts - translate from js to ts
- ~testing (job or startup)
- Introduce graphQL api (still had momentum). (can integrate using apollo client library). 
- something other than vite. nextjs is gaining momentum

Using concept >>> implement something a little different with the concept 70-80%

### Obsolete Learning Topics
- class components (2018 introduction of hooks and functional components)
- higher order components
- prop types (Using typescript instead of js)
- redux used for state mgt. Not necessary for the beginning

- Newer version of React is v19