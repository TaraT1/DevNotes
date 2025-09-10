---
id: 0391rxitz6qnq99vicdht7w
title: React
desc: ''
updated: 1756751294178
created: 1667248557067
---
Refs:

- [Travis Media](https://www.youtube.com/watch?v=w7ejDZ8SWv8)
- [dox](https://reactjs.org/)
- [tech w tim &#39;tube](https://www.youtube.com/watch?v=G6D9cBaLViA)
- [roadmap](https://www.onepin.io/roadmap/A-visual-timeline-roadmap-to-master-React-in-03-months-679266451dd9295920315d17)

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

## Create New React App - DEPRECATED

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
  - Wrap element(s) in `<Fragment></Fragment>`. Requires import {Fragment} from "react";
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

### React Tech w Tim 'tube

- jsx
- component - function that returns jsx code (html)

  - starts with capital letter
  - returns need to have parent element
    - can use fragment <>...</>
- state shows change; something where once changed componenet will change and re-render itself to show nwe state

  - syntax:

  ```javascript
  function Home(){
      const [searchQuery, setSearchQuery] = useState("")
      //submit btn by default refreshes page
      e.preventDefault()
      setSearchQuery('')
  }
  ```

  - when state changes then component is re-rendered
- hook
- page routing

  - React Router
- API calls

  - good practice to use separate file for API calls
  - fetch() - function to send network request
- useEffect - allows adding side effects to functions /components & define when run
- contexts

  - React context
  - storage: localStorage; sessionStorage
  - context allows state to be available globally to anything that's within provided context
- children - reserved property of written or rendered component

## Scrimba Learn React

[Scrimba tut with Bob Ziroll](https://www.youtube.com/watch?v=x4rFhThSX04&t=781s)

- https://github.com/scrimba/learn-react

## React is a Library

- library - collection of reusable code
  - reduces need to write repetitive/complex things from scratch
  - dev controls how/when used. Few boundaries
- framework - predetermined architcture - follow specified pattern of development
  - work within boundaries set by framework
  - opinionated - right and wrong ways to use It

### History

- 2006  jQuery - bridge browsers
- 2010  Angular.js (v1), ember, backbone.js
- 2013  React, Angular v2, Vue.js
- 2016  svelt, nextjs - fs framework using React as its UI library
- 2020  ...

### Composable /Declarative

- composable - composable code is code that can be combined to create more powerful higher-level constructs. Easily reusable and interchangeable pieces of the web that can be combined in various ways to create complex systems (Lego bricks are composable unlike the statue of David)
  - component -identifiable part of a larger program or construction. Usually provides specific functionality or group of related functions
- Declarative - can lean on React library to handle manual, tedious tasks
- imperative - in contrast to declarative - Describe every step how task should be done

### Code

- Save files as jsx if there's any jsx
- img may need absolute path when using vite
- vite
- file/content structure
  - index.css
  - index.html - contains html element with "root" id
  - index.jsx

```javascript
import {createRoot} from "react-dom/client"

//Initialize root, which is element in the body
const root = createRoot(document.getElementById("root"))
root.render(
    <h1>...</h1>
)
```

### Components

A component is a function that returns React elements.

- A React element is react version of what we see in the DOM.
- When returning React elements (html elements)
  - jsx to calls to createElement
  - turns to js objects that react interprets and turns into DOM nodes under the hood.
  - Hence, a React component is a function that returns React elements (UI)

```javascript
import {createRoot} from "react-dom/client"
const root = createRoot(document.getElementById("root"))

function Page() {
    return (
        <div>
            <header>
                ...
            </header>
            <main>
                ...
            </main>
        </div>
    )
}
```

- Functions give power of reusability - encapsulating reusable pieces of code, adding params allows flexibility, call func when need to accomplish task

```javascript
function TemporaryName() {
    return  ( //Can start html on same line w/o ()
        html for root...
    )
}

root.render(
   <TemporaryName /> //self-closing tag
)

```

- Custom components use pascal case: TemporaryName
- Call with < /> - self-closing angle brackets

### Fragments

- Avoid adding unnecessary html elements in the dom mode by using fragments
- <>...</> - **New**
- **Old**

```javascript
import {Fragment} from "react" 

<Fragment>
    ...
</Fragment>
```

### Parent/Child Components

wsl: learn-react/challenges
Breakdown elements into separate components and call them

```javascript
/* Challenge
Move header element from Page component into its own component Header

Render instance of Header compoent insde Page component where header used to be

2: Move main content to its own component Main

3: Move footer content to its own component Footer
*/

import {createRoot} from "react-dom/client"

const root = createRoot(document.getElementById("root"))


function Page() {
    return (
        <>
            <Header />
            <MainContent />
            <Footer />
        </>)
}

function Header() {
    return (
        <header>
            <img src="./react-logo.png" alt="React logo" width="50rem"/>
        </header>
    )
}

function MainContent() {
    return (
        <>
          <main>
                <h1>Reason Excited for Learning React </h1>
                <h2>(this is slick)</h2>
                <ol>
                    <li>React is a popular library, so I too can be a cool kid</li>
                    <li>Money magnet skill</li>
                    <li>It will be more better to implement my fantastic ideas</li>
                </ol>
            </main> 
        </>
    )
}

function Footer () {
    return (
            <footer>
                <small>Copr. 2025 Thierry Development. All rights reserved.</small>
            </footer>
    )
}

root.render(
    <Page />
)
```

### Styling with Classes

- Add classes to jsx elements and access classes in css in order to style them.
- React creates DOM elements from jsx. className accesses native DOM properties in jsx.
- In React use className because it accesses DOM properties, not because class is a reserved js keyword

```
const ul = document.createElement("ul")
ul.className = ""
```

### Organizng Classes

- Can separate components in index.jsx for modularity. Hence change file structure: Header.jsx, MainContent.jsx, Footer.jsx
- export using `export default function FunctionName from "./FileName"
- In index.jsx: `import Header from ... "./fileName`

### Mental Models

### Initial Project

- Create App comp in separate App.jsx file (sibling to index.jsx)
- `components` folder
- Create components in sep files inside components folder. Navbar, Main
- export and import Navbar and Main composable
- import and render App comp inside index.jsx using ReactDOM
- from google fonts, get "Inter" font with weights 400, 600, 700. Put links above style.css link in index.html

### Reusability

- Places for data that can be nested, repeated.

### Props

- prop or property
- Makes components reusable

### Aside: JS inside

- {} - embed parameters  for React

```javascript
import ReactDOM from "react-dom/client"

function App() {
    const hours = new Date().getHours()
    let timeOfDay

    if (hours < 12) {
        timeOfDay = "moanin'"
    } else if (hours >= 12 && hours < 18 ) {
        timeOfDay = "afternoon"
    } else if (hours < 21 ) {
        timeOfDay = "eve"
    } else {
        timeOfDay = "night"
    }

    return (
        <h1>Good {timeOfDay}</h1> //renders Good timeOfDay
    )
}

ReactDOM.createRoot(document.getElementById("root")).render(<App />)
```

### Receiving Props in a Component

- function Component(props){...} In Component, label {props.var} that concurs with App.jsx data

### Quiz

- What do props help us help us accomplish?

  - Props help to customize components and make them reusable
- How do you pass a prop into a component?

  - Establish the props name as the component function's parameter, e.g., props.
  - Like attr to html element `<img src="???">`
- Can you pass custom prop to a native DOM element? Why or why not?

  - I don't think so. Is there a way to get to the native DOM?
  - No, jsx describing native DOM elements will be turned into real DOM elements by React. Real DOM elements only have properties/attrs specified in HTML specs.
- How receive props in component?

```javascript
function Navbar() {
    return (
        <header>
        ...
        </header>
    )
}
function Navbar(props)
<div>props.data</div>
```

- what data type is `props` when component receives it?
  - The data type of `props` when component receives it is an object, which uses . syntax.

## Destructuring Props

```javascript
const person = {
    img: "image file",
    name: "name name",
    phone: "ph#"
    email: "emailaddy"
}

const {img, name} = person
const {img: image, name} = person // : renames img to image
```

### Map Component in App

Using dir structure:

- Component.jsx - holds structure, props, attrs,
- App.jsx holds pointers to where data is on page. Import components and external data. Data can be accessed via .map()
- dataFile.js - holds specific detailed data e.g. data for each entry

```javascript
//Component.jsx
export default function Entry(props) {
    return (
        <article className="journal-entry">
            <div className="main-image-container">
                <img 
                    className="main-image"
                    src={props.img.src} 
                    alt={props.img.alt}
                />
            </div>
            <div className="info-container">
                <img 
                    className="marker"
                    src="../images/marker.png" 
                    alt="map marker icon"
                />
                <span className="country">{props.country}</span>
                <a href={props.googleMapsLink} target="_blank">View on Google Maps</a>
                <h2 className="entry-title">{props.title}</h2>
                <p className="trip-dates">{props.dates}</p>
                <p className="entry-text">{props.text}</p>
            </div>
          
        </article>
    )
}

//data.js
    {
        id: 1,
        img: {
            src: "https://scrimba.com/links/travel-journal-japan-image-url",
            alt: "Mount Fuji"
        },
        title: "Mount Fuji",
        country: "Japan",
        googleMapsLink: "https://maps.app.goo.gl/6RLYZDuuuqJ7kNGZ9",
        dates: "12 Jan, 2021 - 24 Jan, 2021",
        text: "Mount Fuji is the tallest mountain in Japan, standing at 3,776 meters (12,380 feet). Mount Fuji is the single most popular tourist site in Japan, for both Japanese and foreign tourists."
    },
    {
        id: 2,
        img: {
            src: "https://scrimba.com/links/travel-journal-australia-image-url",
            alt: "Sydney Opera House"
        },
        title: "Sydney Opera House",
        country: "Australia",
        googleMapsLink: "https://maps.app.goo.gl/Zr17SCrsJeCEKMd36",
        dates: "27 May, 2021 - 8 Jun, 2021",
        text: "The Sydney Opera House is a multi-venue performing arts centre in Sydney. Located on the banks of the Sydney Harbour, it is often regarded as one of the 20th century's most famous and distinctive buildings."
    },

//App.jsx
import Header from "./components/Header"
import Entry from "./components/Entry"
import data from "./data"

export default function App() {
    const dataEntries = data.map(entry => { //destructure, declare
        return (
            <Entry 
                img={entry.img}
                title={entry.title}
                country={entry.country}
                googleMapsLink={entry.googleMapsLink}
                dates={entry.dates}
                text={entry.text}
                />
        )
    })

    return (
        <>
            <Header />
            <main className="container">
                {dataEntries}
            </main>
        </>
    )
}
```

### Unique key props

    - "Each child in a list should have a unique "key" prop." Pass unique prop in key field: key: {}. (Best generated from db ids and not map index method)
    - Using .map() to create unique id, is not recommended

### Pass object as props.

Rather than putting in each property of an object or component. Can pass object as single prop plus its associated key

```javascript
export default function App() {
    const dataEntries = data.map(entry => { //destructure, declare
        return (
            <Entry 
                key={entry.id} //from datafile
                entry={entry} //refers to the whole object. Passing object thru props. Props in component need additional pointer
            />
        )
    })
}

export default function Entry(props){
        return (
        <article className="journal-entry" >
            <div className="main-image-container">
                <img 
                    className="main-image"
                    src={props.entry.img.src} //<Entry entry={entry}
                    alt={props.entry.img.alt}
                />
            </div>
            <div className="info-container">
                <img 
                    className="marker"
                    src="../images/marker.png" 
                    alt="map marker icon"
                />
                <span className="country">{props.entry.country}</span>
                <a href={props.entry.googleMapsLink} target="_blank">View on Google Maps</a>
                <h2 className="entry-title">{props.entry.title}</h2>
                <p className="trip-dates">{props.entry.dates}</p>
                <p className="entry-text">{props.entry.text}</p>
            </div>
          
        </article>
    )
}

//* Syntatic sugar with object spread notation {...entry}
export default function App() {
    const dataEntries = data.map(entry => { //destructure, declare
        return (
            <Entry
                key={entry.id}
                {...entry} 
            />
        )}}

export default function Entry(props){
        return (
        <article className="journal-entry" >
            <div className="main-image-container">
                <img 
                    className="main-image"
                    src={props.img.src} //<Entry entry={entry}
                    alt={props.img.alt}
                />
            </div>
            <div>
                <span className="country">{props.country}</span>
                <a href={props.googleMapsLink} target="_blank">View on Google Maps</a>
                <h2 className="entry-title">{props.title}</h2>
                <p className="trip-dates">{props.dates}</p>
                <p className="entry-text">{props.text}</p>
            </div>

```

{...}: Syntactic sugar with object spread notation

- verbose syntax for component but not on App()

## State

State is a component's memory.

### Static Web Pages

- For the most part are read only. Ex: blogs, news sites, recipes

### Dynamic Web Pages

- User has ability to change data - read/write
- highly interactive
- displays specialized data
- Ex: bank website, airbnb, ecommerce sites

## Event Listeners

- can be placed in javascript DOM
- in html script tag
- [react documentation Responding to Events](https://react.dev/learn/responding-to-events)

```javascript
//App.jsx
function App(){...}

someElement.addEventListener("click", function() {})

ReactDOM.createRoot(document.getElementById('root')).render(<App />)

//html
<div id='root'>
<button onclick="handleClick()">Trigger event</button> //handleClick() in js file
<script src="./index.jsx"...</script>
</div>
```

For React, event listeners

- can be placed inside the component above the return as an attribute added to elements.
- can also define event handler inline in jsx as function declaration or anonymous or arrow function
- By convention event handler functions start with `handle` followed by name of the event. handleClick, handleMouseEnter, &c
- passing vs calling a function. Functions passed to event handlers must be passed and not called. When a function is called, it fires with rendering and not when triggered.

```javascript
//pass function
<button onClick={() => alert('Passing a function')}>Passing onClick</button>
<button onClick={handleClick}>Passes handleClick function</button>

//calling function
<button onClick={alert('Rendering without clicking')}></button>
```

```
function App() {

    function handleClick() {
        console.log("Clicked")
    }

    return (
        <>
            <div></div>
            <button onClick={function() {console.log("Clicked!")}}>Click this inline function</button> {/* inline event listener function. Note: onClick in React - not onclick*/}
      
            <button onClick={}>Click & function above component's return 
        </button>

    )
}
```

- [React dox adding interactivity](https://react.dev/learn/adding-interactivity)
- [React dox mouse events](https://react.dev/reference/react-dom/components/common#mouseevent-handler)
- Example proj11 event list c.f. Event Listener in proj /home/tarat/React/first-react/

## React State

- Props refers to properties being passed into a component - as in how a function receives parameters. A component receiving props is not allowed to modify props. Props are immutable.
- State refers to values that are managed by the component, similar to variables declared inside a function. Would use state any time saving/displaying changing values.

### View as a function of state

1. Render - runs function and displays what gets returned.
   - function runs again if prop value changes or its internal state values change
2. `setState` function changes state, which causes React to re-render component
   - In contrast, changing local, non-state var does not cause React to re-render
3. view = function(state)
   - When state changes >>> React re-renders component
   - Something new gets returned, replacing what used to be on the page

```javascript
import React from "react"

export default function App(){ let [isImportant, setIsImportant] = React.useState("Yes") //using destructuring; convention of function is setVarName (isImportant in this case)

    function handleClick() {
        setIsImportant("Definitely")
    }

    return (
        <main>
            <h1 className="title">Is state important to know?</h1>
            <button onClick={handleClick} className="value">{isImportant}</button>
        </main>
    )
}
```

React limits the number of re-renders to prevent an infinite loop

### Set state

`React.useState()` e.g., `const [count, setCount] = React.useState(0)`
    - [var, setter func]

- To set state that relies on previous value, use callback function. Naming convention: prev + var name

```javascript
const [count, setCount] = React.useState(0)
function add() {
    setCount(prevCount => prevCount + 1)
}
```

- rule: Never directly modify state in React
  No-nos: arr.push(newElement), count ++

### React Forms

- 6:26:20 Zirolli 'tube
- React 19 handles forms much better than previous versions. Uses built-in browser
- ref: [React dox: forms](https://react.dev/reference/react-dom/components/form)

index.jsx

```jsx
//...

//Refactor: Declarative form submission; Evolving of handling forms in React versions from in reverse
function App() {

    function signUp(formData){
        const data = Object.fromEntries(formData)
        const dietaryRestrictions = formData.getAll("dietaryRestrictions")

        const allData = {
            ...data,
            dietaryRestrictions // dietaryRestrictions: dietaryRestrictions 
        }
    }
    // function signUp(formData) {
    //     const email = formData.get("email")
    //     const password = formData.get("password")
    //     const emplStatus = formData.get("emplStatus")
    //     const dietaryRestrictions = formData.getAll("dietaryRestrictions") //.getAll gets all

    }
    return (
        <section>
            <h1>Signup form with declarative form submission </h1>
            <form action={signUp}>
            <label htmlFor="email" >Email:</label>{/*Note: specifying function in form action overrides method or encType*/}
            <input id="email" defaultValue="e@mail.com" type="email" name="email" placeholder="e@mail.com" /> <br />

            <label htmlFor="password">pWord:</label>
            <input id=password defaultValue="password123" type="password" name="password">

            <label htmlFor="description">Description:</label>
            <textarea id="description name="description" defaultValue="Describe"></textarea>

            <fieldset>
                <legend>Employment status:</legend>
                <label>
                    <input type="radio" name="employmentStatus" value="unemployed" />
                    Unemployed
                </label>
                <label>
                    <input type="radio" name="employmentStatus" value="part-time" />
                    Part-time
                </label>
                <label>
                    <input type="full-time" name="employmentStatus" defaultChecked={true} value="full-time" />
                    Full-time
                </label>
            </fieldset>

            <fieldset>
                <legend>Dietary Restrictions:</legend>
                <label>
                    <input type="checkbox" name="dietaryRestrictions" value="religious" />
                    Religious
                </label>
                <label>
                    <input type="checkbox" name="dietaryRestrictions"
                    value="plant-based" />
                    Plant-based
                </label>
                <label>
                    <input type="checkbox" name="dietaryRestrictions"
                    defaultChecked={true} value="none" />
                    None
                </label>
            </fieldset>

            <label htmlFor="favColor">What color are you into?</label>
            <select id="favColor" name="favColor" defaultValue="indigo" required>
                <option value="" disabled>Choose a color</option>
                <option value="red">Red</option>
                <option value="orange">Orange</option>
                <option value="yellow">Yellow</option>
                <option value="green">Green</option>
                <option value="blue">Blue</option>
                <option value="indigo">Indigo</option>
                <option value="violet">Violet</option>
        </select>

        <button>Submit</button>

    </form>
    </section>
    )

}

//Form Submission - post, get methods & query strings
function App() {
    function handleSubmit(event){
        event.preventDefault() // prevent full page refresh
        const formElement = event.currentTarget
        const formData = new FormData(formElement)
        const email = formData.get("email")
        console.log(email) //Submit form to a backend
        formElement.reset()
    }

    return (
        <>
        <section>
        <h1>signup form</h1>
        <form action="phpfile.php" onSubmit} method="POST"> {/*action can take {} */}
            <label htmlFor="email">Mail o E</label>
            <input id="email" type="email" placeholder="e@e.com" />
        </section>
        </>
    )
}

```

- Object.fromEntries(formData) grabs all the data from the form

## Conditional Rendering

- render parts of page based on condition.
  - true: renders
  - false: won't be rendered. Won't be added to document

```javascript
export default function Joke(props) {
    /**
     * challenge1:
     * - create state `isShown` (boolean, default: `false`)
     * - add btn that toggles val back and forth
     */
    const [isShown, setIsShown] = React.useState(false)

    function toggleShown() {
        setIsShown(prevShown => !prevShown)
    }

    /**
     * Challenge2
     * Display punchline p only if `isShown` is true
     */
    return(
        <div>
            {props.setup && <h3>{props.setup}</h3>} //if truthy val, show setup
            {isShown && <p>{props.punchline}</p>}//isShown === true &&
            <button onClick={toggleShown}>Show punchline</button>
            <hr />
        </div>
    )
}
```

- proj22 conditional rendering in first-react
- && short-circuit - quickly display or not display

```javascript
export default function App(){
    const [unreadMessages, setUnreadMessages] = React.useState(['a', 'b'])
    /**
     * challenge1: display <h1> if there are unread msgs
     * challenge2: if 0 unread msgs, display p saying You have no unread messages
     */
  
    return (
        <div>
            { unreadMessages && <h1>Always true even if arr is blank </h1>}

            { 
                unreadMessages.length > 0 && 
            <h1> You got {unreadMessages.length} unread messages </h1>
            }

            {
                unreadMessages.length === 0 &&
                <p>You have no unread messages</p>
            }
        </div>
      
    )
  
}

```

- Using &&, setting explicit boolean not just truthy avoids bugs
- ternary option avoids potential bug `{isShown ?`<p>`{props.punchline}`</p>` : null}
- ternary exercise in first-react/proj22a App.jsx - nested ternary not working

### Quiz

1. What is conditional rendering
    In highly dynamic web app, may have changing data or changing local state. Conditional rendering is when only sometimes display something on the page based on condition
2. When use &&
   Either display something or display nothing
3. When use ternary
   Decide which of 2 things to display 
4. What if need more than 2 options to display
   if...else if...else conditional or switch. Nested ternary is kinda messy

### State & Props in the Component Tree
- Passing data around React
- State passes down - from parent to child. Cannot pass state to component sibling or from component child
- Solns for passing data include passing down through props. React tool context; 3rd party libraries redux, zoostand
- proj 25 /03.43 git
- Best practice is to to keep state locally defined. If state is global, other soln is called for 

### Inline Styles in React
Use for more dynamic styling
`<button style={{}}>`
- {}: signals to evaluate js in jsx; {{}} is for inline style expression
- React css is written in camelcase (like DOM)
- also: 
```
const styles = {
    backgroundColor: turquosise;
}
<button style={styles}>
```

## Derived State 
- Setting state based on the initial value of the incoming props
- c.f. https://github.com/scrimba/learn-react/tree/main/03.%20React%20State/48.%20Sound%20pads%20challenge%20-%20part%204.1%20-%20local%20state first-react proj29; 'tube 8:44
- Can end up with multiple sources of truth
- better to have unified source of truth

## Scribma Learning Summary
I. Event listeners  
II. State  
III. Conditional Rendering  
IV. Forms  
V. State Mgt **Strategies**  

### Important functional programming concepts for React
- pure function - given same inputs produces same outputs
- immutability - props are immutable as is state. (State is not directly changed. Setter function is used to make changes)
- components should avoid side effects; should not affect outside system

### outside effects - React can't handle
- React doesn't automatically connect to outside effects 
    - local storage
    - API/db interactions
    - subscriptions (e.g. websocket connections)

## useEffect()
- provides escape hatch
- https://react.dev/learn/synchronizing-with-effects