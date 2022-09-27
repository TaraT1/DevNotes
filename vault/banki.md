---
id: nt7qeprlgw0khh6661s0og3
title: Banki
desc: ''
updated: 1664248285632
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
what is event loop

what is difference between call stack and task queue