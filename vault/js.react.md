---
id: 0391rxitz6qnq99vicdht7w
title: React
desc: ''
updated: 1667250291109
created: 1667248557067
---
Ref: [Travis Media](https://www.youtube.com/watch?v=w7ejDZ8SWv8)

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

