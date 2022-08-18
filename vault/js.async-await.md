---
id: m9plmgzlwfrnvwapaa7ucx6
title: Async Await
desc: ''
updated: 1660793864222
created: 1658541899080
---
Check out: 

Js is single threaded programming langauge. web tends to be blocking or time consuming. Async is essential

browser event loop 
- Jake Archibald's Talk: https://youtu.be/cCOL7MC4Pl0
- Demos with Angular: https://www.youtube.com/channel/UCYFd...
involves callbacks in event loop

- browser & node js run sgl threaded event loop to run code. 1st runs synchronous. Next async to be called back later.

How event loop works - getData done >> callback
- for macro task (set timeout or set interval), executes on next event loop
- for micro task (fulfilled promise), will be called back before the start of the next 

## promise

```javascript
//Event loop and Order
//L1
console.log('Synchronous 1');
//L2 >> 4
setTimeout(_ => console.log(`Timeout 2`), 0);
//L3 >> 3
Promise.resolve().then(_ => console.log('Promise 3'));
//L4 >> 2
console.log('Synchronous 4');

//How promise based api is consumed
import fetch from 'node-fetch';

const promise = fetch('https://jsonplaceholder.typicode.com/todos/1')

promise
  .then(res => res.json())
  .then(user => {
    throw new Error (uh oh');
    
  }
  
  
  
  
  console.log(':=)', user.title))

[[js.node.md]]
```
[Async Await, Jake Archibald](https://www.youtube.com/watch?v=vn3tm0quoqE)
Event loop, callbacks
Browser and node.js always run single threaded event loop to run code.
- 1st run synchronous code and might cue up callbacks to run later
- event loop keeps up and separate thread pool

callback
- macrotask like setTimeout or setInterval will be executed on next event loop
- microtask like fulfilled promise will be called back before the start of the next event loop

```js
//L1
console.log('Synchronous 1'); //1

//L2
setTimeout(_ => console.log('Timeout 2')); //4

//L3
Promise.resolve().then(_ => console.log('Promise 3')); //2

//L4
console.log('Synchronous 4')'; //2

//output

import fetch from 'node-fetch';

const promise = fetch('url')

promise
  .then(res => res.json())//map to json
  .then(user => {
    throw new Error('uh oh');
    return user;
  })
  .then(user => console.log(' ', user.title))
  .catch(err => console.error(' ', err));

console.log(' Synchronous')


  
  
  .then(user => console.log(' ', user.title))






```

getData(callback)
getData done


