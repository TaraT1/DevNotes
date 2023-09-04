---
id: nt7qeprlgw0khh6661s0og3
title: Banki
desc: ''
updated: 1664300245768
created: 1664244742134
---
## hoisting
- Explain: Hoisting moves function or variable declaration to the top of their scope using keybinding keywords let or const
- Use: allows calling on function or variable before declaring
- Example: With the event listener, the function component is hoisted since it is called before it is declared.

## synchronous and asynchronous functions - Needs more
Explain: 
- Synchronous functions run tasks to completion. Other tasks are blocked until synchronous tasks are finished
- Asynchronous functions run and execute operations while other tasks are in process. It allows code to run in parallel. Doesn’t have to wait for other tasks to be completed or processed. E.g. event loop; browser APIs setTimeout

Use: Async functions allow retrieving data without blocking other code from running due to the event loop

Example: Browser APIs like setTimeout rely on callbacks to execute once async operation completes. setTimeout code will be set aside to execute once callstack is empty while it waits in callback queue. 

## event loop
What is event loop? What is the difference between call stack and task queue

Explain: Js has runtime model based on the event loop, which is a single-threaded loop responsible for executing code, collecting and processing events, and executing queued sub-tasks. The event loop runs continuously
- Monitors the call stack has frames to execute. (LIFO - pankcake stack)
- Checks if task queue has callback functions codes to execute (FIFO - cafeterial like)

Use: The callback queue executes async operations which are carried out without blocking code.

Example: Web APIs (like setTimeout) are asynchronous and are sent to the callback queue. Event loop checks main stack. If empty, the callback function is dequeued and pushed onto the call stack to be executed

sources: https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop#runtime_concepts

![](/assets/images/2022-09-27-12-27-53.png)


