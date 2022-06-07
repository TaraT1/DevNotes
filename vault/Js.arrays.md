---
id: o3v363hmz91lw3o4p38v5jf
title: arrays
desc: ''
updated: 1654137216800
created: 1653422037610
---

# Arrays
- data structure to store ordered collections
- array elements are numbered starting with 0 (zero indexing)
- have methods to manage order of elements
- can be created by a constructor or literal  notation

## Declaring arrays
- Array Constructor
```
let newArr = new Array()
```
- Literal Notation
```
let newArr = []
```
- Arrays are populated with elements, which can be of any type
- empty spaces leave empty element

## Array Indexing
- elements can be accessed by their index numbers
```
newArr = ['Zebra',,true,21 ]
console.log(newArr[0]) //Zebra
console.log(newArr[1]) //undefined
console.log(newArr[2]) //true
console.log(newArr[3]) //21
```
- elements can updated using index
```
newArr[1] = 'false'
```

- can overwrite whole arrays by assigning array to different array

## Array Length
- Determine how many elements in array
```
console.log(newArr.length)
```

## Array Iteration
- Iterates through array passing in value and index of each element

### for, forEach

```
let bestColors = ['green','blue','yellow','black']
// for
for (let i = 0; i < bestColors.length; i++ ){
    console.log(bestColors[i])
}

// forEach using arrow function - array iterator - x: element; i: iterator
bestColors.forEach((x,i) => console.log(x)) //no function to collect 

```

### Other Array Methods
- built-in methods

#### Pull off methods
- shift - pulls from front of array
- pop - pulls from end of array

#### Add on methods
- unshift adds to front of array
- push - adds to end

#### Map
- runs for each element in the array and creates new array


# Built-in Methods for Arrays - Map, forEach
## Map
```
let nums = [10,20,30]

let robotNewArr = nums.map( n => n += 10 ) //will run 3x w 3 elements in nums array

//Values stored in robotNewArr
n => 10 += 10 // 20
n => 20 += 10 // 30
n => 30 += 10 // 40

```
- map creates a new array
- map can take other functions

```
let months = ['Jan', 'Feb', 'mar']

let lowerCaseMonths = months.map( m => m.toLowerCase() )

console.log(lowerCaseMonths)
console.log(months)
```
- original array is untouched
