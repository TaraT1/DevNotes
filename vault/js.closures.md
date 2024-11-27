---
id: 9i0vm098ljsp6ys0mjhcva3
title: Closures
desc: ''
updated: 1735917417550
created: 1735916511847
---
A closure is a function enclosed with references to its surrounding state (the lexical environment); gives a function access to its outer scope. Closures are created every time a function is   

ref: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures


## Lexical Scoping
Describes how a parser resolves variable names when functions are nested
- lexical refers  to location where var is declared to determine where var is available. 
- nested functions have access to vars declared in their outer 
- variables declared with var are either function-scoped or global-scoped
    - blocks with curly braces do not create scopes
- ES6: variables declared with let and const allow creation of block-scoped variables
    - blocks are treated as scopes with let and const
    - ES6 also introduced modules (introducing another kind of scope)