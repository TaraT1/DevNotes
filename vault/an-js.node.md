---
id: jk3c8urg6v1od7pf2ggxidl
title: Node
desc: ''
updated: 1659325235242
created: 1659324207105
---
Synchronous programming language waits for response before moving to next task.

Js is single-threaded, synchronous, processes one operation at a tme, and blocks

Js running in browser gets access to web APIs that make for operations processed asynchronously.
- DOM, querySelector, setTimeout, setInterval 
- Not part of core Js: 

Js handles responses coming back from web APIs with callbacks, promises, and async/await
- Previously jquery used and provided cross browser compatiblilty. ECMAScript Council implemented Js in browswer as standard

Callbacks wait for something to happen and then do something else.

Higher order function - function that takes another function as argument. A function passed in as an argument in higher order function is called a callback
- nesting can lead to callback hell or pyramid doom

Promise - an object that may have value in the future; represents the eventual completion or failure of async op and its values
- 3 possible states: pending, fulfilled, rejected
- fetch is a promise (available thru web API)

Promise chain
promises (promise chaining code) to make async code look sync

Await waits for async process to complete inside async function

Node is Js runtime built on Chrome's V8 Js engine. Can run on server desktop, etc
- built in modules ( libraries or collections of functions)
- http (network access)
- FS (file system access)
- access to pkgs via npm