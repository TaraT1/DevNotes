---
id: 08q9teip0yyjkw20wo12vzx
title: Arrays
desc: ''
updated: 1673276243489
created: 1653422037610
---

# Arrays (toaster)
- data structure to store ordered collections
- array elements are numbered starting with 0 (zero indexing)
- have methods to manage order of elements
- can be created by a constructor or literal notation

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

```javascript
let bestColors = ['green','blue','yellow','black']
// for
for (let i = 0; i < bestColors.length; i++ ){ //works fastest, old browser compat
    console.log(bestColors[i])
}

// forEach using arrow function - array iterator - x: element; i: iterator
bestColors.forEach((x,i) => console.log(x)) //no function to collect 
```
### Comparison in Arrays
- don't use ==, <,> as they have no special treatment for arrays. They handle them as any objects.
- ```for...of``` loop can compare arrays item by item

### Other Array Methods
- built-in methods

#### Pull off methods
- shift - pulls from front of array
- pop - pulls from end of array

#### Add on methods
- unshift adds to front of array
- push - adds to end

# Built-in Methods for Arrays - Map, forEach
## Map
- runs for each element in the array and creates new array with same num of elements while forEach does not create new array
- map can take other functions
- syntax with arrow function: map((element) => { /* ... */ })
```javascript
//Ex 1
let nums = [10,20,30]

let robotNewArr = nums.map( n => n += 10 ) //will run 3x w 3 elements in nums array

//Values stored in robotNewArr
n => 10 += 10 // 20
n => 20 += 10 // 30
n => 30 += 10 // 40

//Ex 2
let months = ['Jan', 'Feb', 'mar']

let lowerCaseMonths = months.map( m => m.toLowerCase() )

console.log(lowerCaseMonths)
console.log(months)

//Ex 3
const materials = [
  'Hydrogen',
  'Helium',
  'Lithium',
  'Beryllium'
];

console.log(materials.map(material => material.length));
```
- original array is untouched

## Filter
- looks for element(s) that make(s) function return true, returns new arr
```let results = arr.filter(function(item, index, array))```

``` javascript
const fifteen = inventors.filter(function(inventor) {
    if(inventor.year >= 1500 && inventor.year <= 1599) {
    return true;
    }
});
//console.log(fifteen)
console.table(fifteen);    

//arrow: let funcName = (args) => exp
const fiftHun = inventors.filter( inventor => (inventor.year >= 1500 && inventor.year <= 1599))
    console.table(fiftHun);
```

## Sort
- Sorts arr in place, changing element orders
- function does the comparison

```javascript
const birth = inventors.sort(function(a, b){ //bubble sort, default is string
    if(a.year > b.year){
    return 1;
    } else {
    return -1;
    }
});
console.table(birth)

//ternary
const birthTern = inventors.sort((a, b) => a.year > b.year ? 1 : -1);
console.table(birthTern)
 ```   
## reduce/reduceRight
- arr.reduce and arr.reduceRight calculate single value based on array
```javascript
let value = arr.reduce(fn(accumulator, current value or item, index, array){
    //...
}, [initial]);    
//reduce as arrow function (*A)
return a.reduce((acc,c) => acc + c**2, 0) > b.reduce((acc,c) => acc + c**3, 0);

function getAverage(marks){
    return marks.reduce((acc, c) => acc + c) /marks.length
}

```
- accumulator result of previous fn call (initial)
- item - current array item
- index - position
- array - arr
- initial value

## Reverse string
```javascript
str.split('').reverse().join('')
- split turns string into array; ('delimiter')
- reverse can reverse individual letters
- join back together to get string

arrays: arr.reverse()
```
## slice
- extracts txt from one string and returns new string. Changes in one string do not affect other string
- syntax: slice(beginIndex[0], optional endIndex(not inclusive))
```javascript
let str = "The morn is upon us."
str.slice(-3, -1)//returns 'us.'
arr.slice(start,end)
arr.slice(start)
```

[[an-js.array-methods]]