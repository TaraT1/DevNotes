---
id: fn7w66mw1ngsahg131pph1p
title: Array Methods
desc: ''
updated: 1674675791625
created: 1662672427860
---
From [Js Array Methods from Web Dev Simplified](https://youtu.be/R8rmfD9Y5-c)
```javascript

const items = [
    {name: 'Bike',      price: 100},
    {name: 'TV',        price: 200},
    {name: 'Album',     price: 10},
    {name: 'Book',      price: 5},
    {name: 'Phone',     price: 500},
    {name: 'Computer',  price: 1000},
    {name: 'Keyboard',  price: 25},
]

//.filter(); returns new arr
//arrow func: filter((element, index, array) => {/* ... */} )

const filtered = items.filter((item) => {
    return item.price <= 100 //returns Bike, Album, Book, Keyboard detail 
})

//.map() takes one arr, converts to new arr which will be slightly diff
const itemNames = items.map((item) {
    return items.price
})
console.log(itemNames)

function invert(array) {
   return array.map(x => x * -1);
}

const invert = array => array.map(x => -num);

//.find() - find single item in array; returns first item that returns true
const foundItem = items.find((item) => {
    return item.name === 'Book'
})
console.log(foundItem)

//.forEach does not return anything - loops
items.forEach((item) => {
    console.log(item.name) //returns name (price) in each record
})

//.some() returns true if one item is true or false if not
const hasInexpensiveItems = items.some((item) => {
    return item.price <= 100
})

console.log(hasInexpensiveItems)

//.every() - every item to return true
const hasInexpensiveItems = items.every((item) => {
    return item.price <= 1000
})
console.log(hasInexpensiveItems)//returns true


//.reduce() does operation on array; takes acc, item, initial
const total = items.reduce((currentTotal, item) => {
    return item.price + currentTotal
}, 0)

console.log(total) //adds cumulative total

//.includes()
const items = [1,2,3,4,5]

const includesTwo = items.includes(2)

console.log(includesTwo) //if not 2, false

```

From [javascript.info](https://javascript.info/array-methods)
```javascript
//.splice()
```

A cheat sheet of array methods:

    To add/remove elements:
        push(...items) – adds items to the end,
        pop() – extracts an item from the end,
        shift() – extracts an item from the beginning,
        unshift(...items) – adds items to the beginning.
        splice(pos, deleteCount, ...items) – at index pos deletes deleteCount elements and inserts items.
        slice(start, end) – creates a new array, copies elements from index start till end (not inclusive) into it.
        concat(...items) – returns a new array: copies all members of the current one and adds items to it. If any of items is an array, then its elements are taken.

    To search among elements:
        indexOf/lastIndexOf(item, pos) – look for item starting from position pos, return the index or -1 if not found.
        includes(value) – returns true if the array has value, otherwise false.
        find/filter(func) – filter elements through the function, return first/all values that make it return true.
        findIndex is like find, but returns the index instead of a value.

    To iterate over elements:
        forEach(func) – calls func for every element, does not return anything.

    To transform the array:
        map(func) – creates a new array from results of calling func for every element.
        sort(func) – sorts the array in-place, then returns it.
        reverse() – reverses the array in-place, then returns it.
        split/join – convert a string to array and back.
        reduce/reduceRight(func, initial) – calculate a single value over the array by calling func for each element and passing an intermediate result between the calls.

    Additionally:
        Array.isArray(value) checks value for being an array, if so returns true, otherwise false.

Please note that methods sort, reverse and splice modify the array itself.


The every() method tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value. 
- syntax: element, index, array

```javascript
smallEnough = (a, l) => a.every(e => e <= l)

function smallEnough(a, limit){
  return a.every(x => x <= limit);
}
```

[[js.arrays]]