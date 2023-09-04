---
id: pogmxvdud885qagqs0l04zu
title: For
desc: ''
updated: 1684159625058
created: 1684156300400
---
## for statement
~ creates a loop to be executed
~ syntax
``` javascript
for (initialization; condition; afterthought) {
    ...
}

//example
for (let i=0; i < 9; i++) {
    console.log(i)
}


## for...of
~ executes loop that operates on a sequence of values sourced from an iterable object like arrays, strings, map, set, nodelist, etc   
~ each loop operation on a value is called an iteration. The loop iterates over the iterable.
~ Iterable has `@@iterator()` method that returns iterator and repeatedly calls resulting iterators `next()` to produce sequence of values to be assigned to variable
~ syntax
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

```

## for...in / for...of
~ iterates over enumerable string properties of an object.  (for...of iterates over values an iterable object defines to be iterated over)
- in-string
