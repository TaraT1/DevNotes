---
id: 0391rxitz6qnq99vicdht7w
title: React
desc: ''
updated: 1709920951454
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
```
npx create-react-app app-name
```
runs create app and folder dir and deps

15:12

## React Update with Typescript - React Tutorial for Beginners
(programming with Mosh 'tube)  

- React is a  Js library used to build dynamic and interactive user
interfaces
    - developed in 2011 by fb 
    - most widely used Js library for FE dev
- Using TypeScript, a superset of Js that adds static typing, can catch errors early in dev process
- c.f. [[js.react.tsvsjsx]] 

### Why was React created
- Browser takes html and creates document object model (DOM), a tree-like structure. Allows use of Js and change page content responding to user actions
    - query and update dom elements using vanilla Js
        - gets challenging with growth and complexity to manage
    - With React, describe web page using small, reusable components and React takes care of efficiently creating and updating DOM elements
    - Components help write reusable, modular, and better organized code

### Dev Environment
1. Create React App (CRA)
2. Vite - faster, gives smaller bundle sizes
```bash
npm create vite@latest ## or vite@4.1.0 - version Mosh uses
# name, select framework (react), language (typescript)

# cd to project folder 
npm install # or npm i
npm run dev //from terminal
```
### Create React Component 
11:24
- In src folder, add new file. Typescript files are ts (plain typescript file) or tsx (React components)
- 2 ways to create React component: Js class or function. Function based more popular as more concise and easier to write
    - Early React projects used class components
    - c.f. older React course
- Pascal syntax - each word is capitalized
- React is platform agnostic.  mobile: ReactNative. Can build web and desktop devices

### Library vs Framework
- Library is tool that provides specific functionality
- Framework is a set of tools and guidelines for buildikng apps
- React is a library. It is a tool for building dynamic and interactive user interfaces. It requires additional tools
    - for routing (allowing user to go from one page to another), making http calls, managing app state, internationalization, form validation, animations, etc.

## Building Components 
Course also covers: 
    - Rendering markup with JSX
    - Managing state
    - Passing input via props
    - Debugging React apps
### Creating a ListGroup Component
- using Bs5
- In React a component cannot return more than 1 element. Solutions:
    - wrap in div or other element. Makes React happy, but unnecessary
    - Wrap element(s) in <Fragment></Fragment>. Requires import {Fragment} from "react"; 
    - Wrap elements using <></> (fragment - children wrapped in <>)

### Render list of items
### Conditional Rendering 
- hook - function that allows tapping into blt-in features in React.
### Handling Events
### Managing State
### Passing Data Via Props
- Props are inputs to component. Just like can call a function and give params
- Use interface to define interface of an object. 
- Using props can pass data to component
### State and Props
- Props (properties) - input or arguments passed to a component; 
    - similar to function arguments; 
    - immutable (read-only)
    - cause re-render with changes
- State - data managed by a component that can change over time; 
    - similar to local vars inside a function; 
    - mutable 
    - cause re-render with changes
### Passing children
### React dev tools
use to inspect React apps. Install in browser.

## React Versions
- Docs in https://react.dev/learn 
- modern - more function based.
    - uses hooks, import export js functions
- older: components are class based. 

