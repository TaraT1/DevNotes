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
- 1st run synchronous code and might cue up asynchronous callbacks to run later. (getData(callback))
- event loop keeps doing its thing in separate thread pool. (getData done)

## Callback Priorities
- Macrotasks like setTimeout or setInterval will be executed on next event loop
- Microtasks like fulfilled promise will be called back before the start of the next event loop

```js
//L1
console.log('Synchronous 1'); //1

//L2
setTimeout(_ => console.log('Timeout 2')); //4

//L3
Promise.resolve().then(_ => console.log('Promise 3')); //3

//L4
console.log('Synchronous 4')'; //2

//output

import fetch from 'node-fetch';

const promise = fetch('url')

promise
  .then(res => res.json())//map to json
  .then(user => console.log(' ', user.title))
  .catch(err => console.error(' ', err));//With promises can catch errors with a single function at the bottom of promise chain

console.log('Synchronous')
/*Output:
Synchronous
api result
*/
```

## Promises Error Handling
- With promises can catch errors with a single function at the bottom of promise chain. Will handle errors anywhere in async code. If error, future .then callbacks are bypassed.
- Callback based code requires separate error handler for async operations

```js
const codeBlock = () => {
  // let i = 0;
  // while(i< 1000000000) {i++;}
  
  //return 'billion loops done'; //script frozen until while loop complete
  /*
  return new Promise((resolve, reject) => {
   let i = 0;
   while(i< 1000000000) {i++;}//Blocking, still happening on main thread

   resolve('billion loops done);//resolving happens as microtask

  })
  */
  return Promise.resolve().then(v => {//executed after synch code in macrotask is completed
    let i = 0; 
    while(i < 1000000000) {i++}
    return 'billion loops done';
  })
  
  log('Synchronous 1');

  log(codeBlock());

  log('Synchronous 2');

}
//async function turns function into promise of function; sets up context to use await keyword
const getFruit = async(name) => {
  const fruits = {
    pineapple: 'fruit1',
    peach: 'fruit2',
    strawberry: 'fruit3'
  }
  return (fruits[name]);

getFruit('peach').then(console.log)
}
//Async & Await
const makeSmoothie = async() => {
  const a = await getFruit('pineapple');
  const b = await getFruit('strawberry');

  //return [a,b]  //Fails to run code cucurrently
  return Promise.all([a,b]);
}
makeSmoothie().then(log)

//promise
const makeSmoothie2 = () => {
  let a;
  return getFruit('pineapple')
    .then(v => {
      a = v;//corrected code from comments
      return getFruit('strawberry')
    })
    .then(v => [v,a])
}

//optimizes Async + Await; don't want to pause func unnecessarily
const makeSmoothieOpt = async() => {
  const a = getFruit('pineapple');
  const b = getFruit('strawberry');
  const smoothie = await Promise.all([a,b]);//add promises to array and await Promise.all

  return smoothie
}
makeSmoothieOpt().then(log)

//Async+Await & Error Handling - wrap in try-catch block - more flex
const badSmoothie = async() => {
  try {
    const a = getFruit('pineapple');
    const b = getFruit('strawberry');
    const smoothie = await Promise.all([a,b]);

    throw 'broken!'

    return smoothie;
  } catch(err){
      console.log(err)
      // Can catch error and throw another error 
      // or can throw another value
      // Returning value ignores err and providing some replacement value
      // consumer of promise won't get error, gets resolved value inside of .then callback

      //In contrast, if throw error inside catch block breaks consumer's promise chain and will be handled by catch callback
  }
}
/*
badSmoothie()
  .then(val => console.log({val}))
  .catch(err => console.log({err}));
*/
```
Tricks

```js
//Have string of ids; retrieve string of ids from db; retrieve string of ids from db; resolve concurrently using promise.all
const fruits = ['peach', 'pineapple', 'strawberry'];
const smoothie1 = fruits.map(v => getFruit(v));//retrieve string of ids from db

const smoothie2 = fruits.map(async v => {
  const emoji = await getFruit(v) //won't pause function in context; needs trad for loop
  log(emoji)
  return emoji
});

//Use for loop in code

const fruitloop = async() => {
  for await (const emoji of smoothie1) {
    log(emoji)

  }
}
fruitloop();

//Using conditional
const fruitInspection = async () => {
  if (await getFruit('peach') === 'emo1') {
    console.log('looks peachy')
  }
}
fruitInspection()