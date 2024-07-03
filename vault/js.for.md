---
id: pogmxvdud885qagqs0l04zu
title: For
desc: ''
updated: 1719935903600
created: 1684156300400
---
## for statement

~ creates a loop to be executed as long as condition is met
~ syntax

```javascript
for (initialization; condition; final expression) {
    ...
}

//example
for (let i=0; i < 9; i++) {
    console.log(i)
}
```

## for...of

- executes loop that operates on collections rather than all objects. (for...of executes on a sequence of values sourced from an iterable object like arrays, strings, map, set, nodelist, etc)
- each loop operation on a value is called an iteration. The loop iterates over the iterable.
- Iterable has `@@iterator()` method that returns iterator and repeatedly calls resulting iterators `next()` to produce sequence of values to be assigned to variable
- syntax

```javascript
for (variable of iterable){
    ...
}

//example
const iterable = [10, 20, 30]

for (let value of iterable) {
    value += 1
    console.log(value)
}
// 11
// 21
// 31

//another example
function reverseString(text){
    let result = ''
  
    for(let char of text){
        result = char + result
    }
    return result
}

reverseString(yxt2)//2txy
```

## for...in

- iterates over enumerable (countable) properties of an object 
- syntax: `for(variable in object)`

```javascript
const object = { a: 1, b: 2, c: 3 }

for (const property in object){
   console.log(`${property}: ${object[property]}`) 
}

//expected output:
//'a: 1'
//'b: 2'
//'c: 3'
```

## forEach

~ array method executes function once for each array element
~ expects synchronous function (does not wait for promises)
~ always returns undefined and is not chainable

```javascript
const arr = ['a', 'b' 'c']

arr.forEach((element) => console.log(element))

//output: 
//'a'
//'b'
//'c'
```
