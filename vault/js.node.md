---
id: jk3c8urg6v1od7pf2ggxidl
title: Node
desc: ''
updated: 1662325165227
created: 1659324207105
---
Synchronous programming language waits for response before moving to next task.

Js is single-threaded, synchronous, processes one operation at a tme, and blocks

Js running in browser gets access to web APIs that make for operations processed asynchronously.
- DOM, querySelector, setTimeout, setInterval 
- Not part of core Js: 

Js handles responses coming back from web APIs with callbacks, promises, and async/await
- Previously jquery used and provided cross browser compatiblilty. ECMAScript Council implemented Js in browswer as standard
-Browser environment gives access to setTimeout and setInterval

Ex code: async-practice


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






[[js.async-await]]

[Traversy Media Tutorial](https://youtu.be/fBNz5xF-Kx4)
[github for code](https://github.com/bradtraversy/node_crash_course)

Code is in wsl ~/LearnWithLeon/crash-course

Node is:
- fast efficient, and highly scalable
- event driven, non-blocking I/O model
- popular
- same language on FE and BE

Non-blocking I/O
- works on single thread using non-blocking I/O calls
- supports 10s of thousand concurrent connections
- optimizes throughput & scalability in apps w many I/O ops
- fast & efficient. Don't want to use with cpu intensive apps (long-running calcs)

Best types of projects for node are anything not cpu intensive
- REST API & microservices
- real time services (chat, live updates)
- CRUD apps - blogs, shopping carts, soc networks
- tools & utilities

npm - node package manager. Used to install 3rd party pkgs
- stored in node_modules folder
- dependencies listed in package.json file
- npm scripts can be created to run tasks such as running server

```js
npm init //generates package.json file
npm install express //installs pkg locally
npm install -g nodemon //installs pkg globally; nodeman is live server
```

## Node Modules
- Node core modules (path, fs, http, etc)
- 3rd party modules /pkgs installed via npm
- custom modules (files)

```js
const path = require ('path');//path is node core module
const myFile = require('./myFile');//./current folder; 
```
node comes w repl. Activate with node
```js
//1st thing create package.json.
npm init // package.json file stores dependencies
```

Following tut code from wsl vs code
Notes:
/node_modules holds dependencies. If dependencies listed in package-json, will get installed.
- package-lock.json tracks deps with versions
- installations come from npmjs.org

Install dev dependencies
npm install --save-dev <pkg>

node_modules are local only, don't get saved to cloud or etc.

Main file is index.js
run file: node <filename> (Does not have to have .js)

node has Module Wrapper Function
(function (exports, require, module, __filename, __dirname){
})
- gives access to methods

Node does not have import method yet. (Have to use Babel)
import Person from './person'; //ES6
const Person = require('./person'); //common js

Documentation in nodejs.org

new folder: reference
path_demo.js

github for tut https://github.com/bradtraversy/node_crash_course

Modules include fs, os, path. Examples in /reference
url module - 

### Morgan.js
Morgan is middleware that logs http requests and errors; accesses request and response lifecycle methods
```
npm install morgan
```
invoke in index.js (or such) with
```
const morgan = require('morgan')
```