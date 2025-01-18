---
id: pogmxvdud885qagqs0l04zu
title: For
desc: ''
updated: 1724890571152
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

## for...of Loop

https://www.javascripttutorial.net/javascript-for-of/  
- executes loop that operates on collections rather than all objects. (for...of executes on a sequence of values sourced from an iterable object like arrays, strings, map, set, nodelist, etc)
- each loop operation on a value is called an iteration. The loop iterates over the iterable.
- Iterable has `@@iterator()` method that returns iterator and repeatedly calls resulting iterators `next()` to produce sequence of values to be assigned to variable
- variable: property of the iterable object is assigned to the variable. (The variable is declared using let, const, or var.)
- syntax:
```javascript
for (declareVar of iterable){
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
### Array destructuring with for...of - access index of elements
To access index of array elements inside the loop, for...of with entries() array method 
- array.entries() method returns [index, element] in each iteration
```javascript
let colors = ['red', 'green', 'blue']

for (const [index, color] of colors.entries()) {//uses array destructuring to assign result of entries() method to index and color vars
    console.log(`$color is at index ${index}`)
}
/*output  
red is at index 0
green is at index 1
blue is at index 2
*/
```
### in-place object destructuring with for...of
```javascript
const ratings = [
    {user: 'Khadija', score: 3},
    {user: 'Destiny', score: 5},
    {user: 'John', score: 2} 
]
 let sum = 0

 for(const {score} of ratings){
    sum += score
 }

console.log(`total scores: ${sum}`)//output: Total scores: 10
```
Notes:  
- ratings is array of objects
- `for(const {score} of ratings)` uses object destructuring to assign score property of current iterated element to the score variable


## for...in Loop

https://www.javascripttutorial.net/javascript-for-in/  

- iterates over enumerable (countable) properties of an object 
    - including going up the prototype chain and enumerating inherited properties 
- for...in ignores non-iterable elements like undefined
- Avoid using for...in to iterate over array elements, especially when index order is important. 
- syntax: `for(variable in object)` - access value of each property with `object[property]`
- mnemonic: foreign object

```javascript
const object = { a: 1, b: 2, c: 3 }

for (const property in object){
   console.log(`${property}: ${object[property]}`) //access value of each property with `object[property]`
}

//expected output:
//'a: 1'
//'b: 2'
//'c: 3'
```

## forEach
https://www.javascripttutorial.net/javascript-array-foreach/  

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
