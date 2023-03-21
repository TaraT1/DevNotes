---
id: 52anmgl8a3a2b30i5q62n56
title: react
desc: ''
updated: 1681433758711
created: 1679962485382
---

Refs: [React dox](https://react.dev/learn)  
js syntax: mdn and javascript.info

React apps are made out of components
- component - a piece of UI that has its own logic and appearance (e.g. button)
- React components are js funcs that return markup
    - start w capital letter (html tags are lowercase)
    
    



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
- React is declaritive programming. (sammich from sammich shop. Name what is wanted)
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