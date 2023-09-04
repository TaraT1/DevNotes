---
id: 0391rxitz6qnq99vicdht7w
title: React
desc: ''
updated: 1668915634114
created: 1667248557067
---
Refs: 
- [Travis Media](https://www.youtube.com/watch?v=w7ejDZ8SWv8)
- [dox](https://reactjs.org/)

React is a library for building UI
- runs on client as SPA
- can be used to build FS apps
- FE framework

Why use?
- structure view layer of app (MVC)
- reusable componewnts with their own state
- JSX dynamic markup
- Interactive UIs w vDOM
- performance, testing, industry popularity

- Declarative Views - view for each state. React updates and renders components when data changes. Makes code more predictable and easier to debug
- Encapsulated Components that manage their own state to make complex UIs. Component logic written in js instead of templates can pass data and keep state out of DOM
- React Components - render() method takes input data and returns what to display. Component data can be accessed by render()this.props JSX Babel Js compiler - xml like syntax that is helpful working w UI inside Js
- Stateful Components
    - input data: this.props
    - internal state data: this.state
    - components state change update by re-invoking render()

## Components
Components can be created with Classes (older) or Functions (with hooks)
- render/return JSX (Js Syntax Extension) 
- can take in props

## State
determines how component renders and behaves
- includes data
- app or global state refers to state that is avail to entire UI
- prior to 16.8 to hold state had to use class components
- now use functional components with hooks (like redux)

## React Hooks
functions that allow us to hook into the React state and lifecycle features from func components

- useState returns stateful value and function to update it
- useEffect performs side effects in function components (make http reqs when page loads)
- Also useContext, useReducer, useRef, etc. and can create custom hooks

## Create New React App
npm create-react-app. Install using npm
react dev tools in browser
````
npx create-react-app app-name
```
runs create app and folder dir and deps

15:12

