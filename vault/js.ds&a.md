---
id: 3kqsaly41wz3amyuczdy1uc
title: DS&A
desc: '100devs'
updated: 1747358320179
created: 1666456198768
---
[Scotch.io Ultimate Algorithms Course](http://web.archive.org/web/20210616161653/https://scotch.io/courses/the-ultimate-guide-to-javascript-algorithms)
https://scotch.io/courses/the-ultimate-guide-to-javascript-algorithms

Resources:

- [Mayanwolfe Ultimate Guide to Js Algos Course 10.12.22](https://www.twitch.tv/mayanwolfe)
- [Codevolution Js Algos](https://www.youtube.com/playlist?list=PLC3y8-rFHvwiRYB4-HHKHblh3_bQNJTMa)
- [Know Thy Complexities](https://www.bigocheatsheet.com/)
- [Types of Asymptotic Notations in Complexity Analysis of Alogorithms](https://www.geeksforgeeks.org/types-of-asymptotic-notations-in-complexity-analysis-of-algorithms/)

A library for books is like data with the need for effectively storing data and showing relationships like genre, author, fiction/non-fiction, etc. Data is organized/structured efficiently using various techniques (departments, catalogs, shelves, etc.)

## Data Structure

- organized way of storing data for use by computer processes
- pattern of collecting and organizing data for performing various operations correctly and efficiently.

### vars and scope

- let (with scope and mutability) and const;
- naming provides meaning and contextualizes the data

### arrays

container object used to hold a list of items usually of the same type (like list of pages numbered in ascending order for easy nav)

### objects

- store collection of related data or functionality in key-value pairs
- Compared to arrays they are designed to hold more complex entities of varying types
- data structures ought to hold and manipulate data in a meaningful way that keeps relationship between them
  **The best data structures consume minimal resources while storing data in a meaningful way for various operations.**
- Key points to consider are if relationship is preserved and data is easily accessible

## Algorithms

well defined computational procedures that take input and produce output

Properties

- input - 0 or more externally provided
- output - 1 or more
- correctness - every step
- definiteness - finiteness

Considerations for efficiency:

- time complexity (execution time of an operation)
- amount of time taken by an algorithm to run as a function of input size
- space complexity (memory usage of an operation)
  - amount of memory taken by an algorithm to run as a function of input size

## SWE's responsibility

Modern apps are data-driven: accept, store, process, and output data. SWE's responsibility to create models of problem domain so data is organized and manipulated in consistent manner.

## Purpose of Data Structures

- help organize data meaningfully
- Abstract Data Types are designed to create a logical description of how data is viewed and the operations that can be carried out on them
- Data Encapsulation - ADTs allow handling data more efficiently - allows for focus on what data represents and not how constructed. Ex: Array, List, Map, Queue, Set, Stack, Table, Tree, Vectors

## Purpose of Algorithms

- help manipulate data efficiently
- proper use, examiniation of different problem-solving techniques, pattern recognition allowing for knowledge transfer and understanding across various domains and problem sets.

## Algorithmic Efficency

- priori analysis - theorectical evaluation. Factors such as processor speed are assumed to be constant, not impacting algorithmic implementation
  - Asymptotic notation is std of expressing algo in terms of time and space complexity.
    - Most common is David Knuth's Big O Notation. aka upper bound of an algorithm or worst case complexity indicates func won't exceed or take more than specific time to execute irrespective of value of input(n); uses algebraic terms
      - expressed in terms of the input
      - focuses on the bigger pic w/o getting caught up in minute details
    - Omega Notation - best case complexity
    - Theta Notation - average case complexity
- posteriori analysis - practical evaluation carried out by implemention and observation of time taken and memory consumed

## 100devs

- A data structure is an organized way of storing data. It is a pattern of collecting and organizing data for performing various operations correctly and efficiently
- An algorithm is the steps one takes to solve a problem
- Thinking through appropriate algorithms is how to efficiently solve problems

  - space - how much memory is used
  - time - how many operations executed per input
- Use Big-O Notation to determine efficiency of solutions

  - mathematically describes the complexity of algo in terms of time and space
  - provides rough estimates
- Common Complexities (MIT's CS curriculum are online)

  - O(1) - Order 1, Constant Time

    - for all inputs only one operation required
    - Example: access element in array

    ```js
    const nums = [1,2,3,4,5]
    const firstNum = nums[0]
    ```
  - O(N) - Order n, Linear, Linear Scaling

    - for all inputs to algo, there will be one operation per input
    - as size of input increases, the time complexity also increases
    - example: looping through array of numbers

    ```js
    const nums = [1,2,3,4,5]
    let sum = 0
    for(let num of nums){
        sum += num
    }
    ```

    - sum nums in arr. Each number is added to running sum (1 operation per input)
    - Gauss' Sum - sum function for sorted contiguous array of integers
      ```js
      const sumContiguousArray = function(arr){
          //get last item
          const lastItem = arr[arr.length - 1]
          //Gauss' trick
          return lastItem * (lastItem + 1) / 2 //constant time
      }
      const nums = [1,2,3,4,5]
      const sumOfArray = sumContiguousArray(nums)
      ```
  - O(N^2) - Quadratic 
  ref: https://jarednielsen.com/big-o-quadratic-time-complexity/

    - The number of operations algo performs scales in proportion to the *square* of the input. (Quadratic means squaring the root. (*quadrus* is latin for square))
    - example: nested for loops, bubble sort algo

    ```js
    const hasDupes = function(nums){
        for(let i = 0; i < nums.length; i++>){
            const thisNum - nums(i)
            for(let j = 0; j < 0; j++){
                if(j !== i){
                    const otherNum = nums[j]
                }
            }
            if(otherNum === thisNum) return true
        }
        return false }

    const nums = [1,2,3,4,5]
    hasDupes(nums) //true
    ```
  - O(LOG N) - logarithmic time
  - algo is proportional to the logarithm of the input size; log10 1000 = 3 (log of 1000 to base 10)

    - can be efficient especially with large amts of inputs
    - example: divide and conquer, binary search algo
  - for small # of inputs, linear complexities could maybe be better

    - optimize for readability rather than efficiency
    - rough estimates
  - ** commit to memory **
  - !!! N is input

  Max & Min Bids

  ```js
  // brute force nested for loops O(n^2)
  // Quadratic works at first, would slow down app significantly
  const findMaxBid = function(bids){
      let maxBid = bids[0],
      let minBid = bids[0]
  for(let i = 0; i < bids.length; i++>){
      for(let j = 0; j < bids.length; i++>){
          if(bids[i] > bids[j] && bids[i] > maxBid) {
              maxBid = bids[i]
          }
      }
  }
  return [minBid, maxBid]
  }

  const allBids = [2,,3,1,4,5,5]
  console.log(findMaxBid(allBids))

  // more efficient approach would be running min and max loops separately --> 
  //finding max bid
  const findMaxBid = function(bids){
   let maxBid = bids[0]   
   for(let i = 0; i < bids.length; i++){
      if(bids[i] > maxBid){
          maxBid = bids[i]
      }
   }
   return maxBid
  }
  //find min bid
  const findMinBid = function(bids){
      let minBid = bids[0]
      for(let i=0; i < bids.length; i++>){
          if(bids[i] < minBid){
              minBid = bids[i]
          }
      }
      return minBid
  }

  const allBids[1,2,7,3,4,5,5]
  console.log(findMinBid(allBids))

  //2 linear loops O(n) --> 2n (quadratic to linear)

  ```
- If data was already sorted, approach and complexity can change
- arrays are objects that have length properties

## Js Method Complexities

- .pop()

  - removes last item from array
  - O(1) constant time
- .shift()

  - changes index of every element
  - O(n) linear
- .length

  - access property of object
  - O(1) constant
- .forEach, map, reduce

  - higher order funcs that take in callback lead to other complexities

[[algorithms#math-algorithms]]

## Frontend Masters, Bianca Gandolfo

https://frontendmasters.com/courses/practical-algorithms/introducing-space-time-complexity/
With respect to input size and assuming worst case scenarios:

- space complexity - how much memory is used
- time complexity - how we reason about the speed of an algo; how many primitive operations

Big pic estimation, so drop non-significant nums that are not in major time-space complexity

| slow     | ---         | to     | ---       | fast        |
| -------- | ----------- | ------ | --------- | ----------- |
| constant | logarithmic | linear | quadratic | exponential |
| O(1)     | O(logn)     | O(n)   | O(n^2)    | O(k^n)      |

- Sometimes need tradeoffs
- For logn solns, it grows and then tapers off
- Time complexity not so key when data set small: focus on readability
- Implement for space-time complexity when data set is large and  performance lags. Avoid pre-optimization

Function with multiple expressions
- Not inside of loop: add together. Ex: constant time: 1+1+1
- Inside of loop: multiply by n. Ex: linear: n * n * n (also depends on methods used inside of loop)

O(logn) Logarithmic time
- different bases (base 10, bAse 2)
- As input increases, # of operations that need to be done decrease by fraction (divide by base (/bAse2 or /basen))

N Log N - linear & logarithmic: nlog n

- have linear, cutting in half

### Complexity of Common Operations

| Complexity          | Operation                              |
| ------------------- | -------------------------------------- |
| O(1) Constant       | running statement, math, lookups, saving(in js)           |
| O(logn) Logarithmic | Loop that cuts problem in half for every iteration |
| O(n) Linear         | Looping through vals of an arr         |
| O(n^2) Quadratic    | Double nested loops                    |
| O(n^3)              | Triple nested loops                    |

- Be mindful of what is n. What is the data set that's growing?
- If data set of more than 1 length, will need to take in to consideration

## Space Complexity

- Space taken up in memory - how much more space taking up? creating new arrs?
- Making new data structure? how often in comparison to input
- Consider call stack. Recursion takes up space in memory

### Asymptotic Notations

- [Types of Asymptotic Notations in Complexity Analysis of Algoorithms](https://www.geeksforgeeks.org/types-of-asymptotic-notations-in-complexity-analysis-of-algorithms/)
- Big-O - represents the upper bound of running time of an algo; worst-case time complexity
- Omega - represents the lower bound of algo's time complexity; provides best case complexity
- Theta - Used for analyzing average case complexity of an algorithm

`str.length` - constant time; object lookup in js

## Faster Algorithms
- breadcrumbs method - keeping track of things already seen; caching
```javascript
//O(n^2). Comparing 2 loops 
const isUnique = (arr) => {
  let result = true

  for(let i=0; i < arr.length; i++) {
    console.log(`~~~ OUTER LOOP ~~~ i === ${i}`)

    for(let j= 0; j < arr.length; j++) {
      console.log(`~~~ OUTER LOOP ~~~ j === ${j}`)
      if(i !== j && arr[i] === arr[j]) {
        result = false
      }
    }
  }
  return result
}
console.log(isUnique([1,2,3]) === true)
console.log(isUnique([1,1,3]) === false)

//breadcrumb method - caching; keeping track of things, can do property lookup; turns quadratic time complexity to linear
isUnique = (arr) => {
  const breadcrumbs = {}
  let result = true;

  for(let i=0; i < arr.length; i++) {
    console.log(`~~~ LOOP ~~~ i === ${i}`)
    if (breadcrumbs[arr[i]]) {
      result = false
    } else {
      breadcrumbs[arr[i]] = true
    }
}

return result
}

console.log(isUnique([1,2,3]) === true)
console.log(isUnique([1,1,3]) === false)
```
### Unique Sort Exercise
- https://frontendmasters.com/courses/practical-algorithms/unique-sort-exercise/
```javascript
const uniqSort = function (arr) {
  const breadcrumbs = {}//key of object is string (json.stringify, map)
  const result = []
  for (let i=0; i < arr.length; i++) {
    if(!breadcrumbs(arr[i])) {//Lookup - not saving
      results.push(arr[i])
      breadcrumbs[arr[i]] = true
    }
  }
  return result.sort((a,b) => a-b)
}
uniqSort([4,2,2,3,2,2,2]) //[2,3,4]
```
### Caching
- saving something into array or object
- U: Optimization technique storing frequently accessed data so subsequent requests can be served quickly
- ex: Storing and accessing http requests & responses (browser execution environment) 

factorial: n!
- 5! = 5*4*3*2*1
- calculate recursive function 
  - factorial(35)
  - factorial (36) = factorial (35) * 36
  - caching takes up more space

### Memoization
- caching value that function returns. Can significantly reduce processing time
  - Memoization is a type of caching
  - closures
  - higher-order functions operate on other functions  by taking them as arguments or returning them
  - https://www.geeksforgeeks.org/javascript-memoization/
  - https://www.freecodecamp.org/news/memoization-in-javascript-and-react/
```javascript
//write function times10. Takes n multiplies n * 10
//Use object to cache results of times10
const cache = {}
const times10 = (n) => {n*10}
const memoTimes10 = n => {
  if(n in cache) {
    return cache[n]
  } else {
    let result = times10(n)
    cache[n] = result //Object caches results of times10; Note: [] not . - n is var
    return result
  }
}
//memoTimes(9) >>> { 9: 90}
```
### Closure
- function that retains access to outer function's variables
  - inner function remembers environment
  - enables private variables
  - enables preserving state between function calls
  - lexical scoping defines scope of a variable by the position of that variable declared in the source code
```javascript
//Memoize with closure - Uses closure to return function that can be called later
const memoizedClosureTimes10 = () => {
  let cache = {} //private to function scope
  return n => {
    if(n in cache) {
      return cache[n]
    } else {
      console.log('Calculating')
      let result = n*10
      cache[n] = result
      return result
    }
  }
}
```
## Recursion
Recursion is when a function calls itself to solve a problem by breaking it down into smaller subproblems
- technique, mindset
- Elegant soln to keep code DRY (do not repeat yourself) as opposed to WET (we enjoy typing /write everything twice)
- Ex: base case, recursive cases that continue until base case is reached
- looping - recursion can always be implemented as a loop. Sometimes it is simpler to use recursion
- tail call optimization - allows some funcs to be called without growing the call stack
### Steps for Recursion
1. Identify base case
2. Identify recursive case(s)
3. Set return where appropriate
4. Write procedure for each cast that brings input closer to base case

```javascript
var callMyself = function() {
  if() {
  //base case
  return
  } else {
    //recursive case
    callMyself()
  }
  return
}

//Looping with Recursion
const loopNTimes = n => {
  console.log('n===', n)
  if(n <= 1){
    return 'complete'
  } 
  return loopNTimes(n-1)
}

loopNTimes(3)

```
## Factorial
- multiplication of result * next consecutive value `result *= i`
```javascript
function computedFactorial(num) {// with loop; iterative solution
  var result = 1

  for(var i = 2: i < num; i++) {
    result *= i
  }
  return result
  /*
  result = 1 * 2 (2)
  result = 2 * 3 (6)
  result = 6 * 4 (24)
  result = 24 * 5 (120)
  => 120
  */
}

function computedFactorial(num) { 
  //base case
  if(num === 1) {
    console.log('Here lies the base case')
    return 1
  } else {
    console.log(`return ${num} * computedFactorial{num-1})`
  }

  //recursive case

  //return

}

```
## Common Patterns for Recursion
### Wrapper function
```javascript
function wrapperFnLoop(start,end) {//closure with recursion
  function recurse(i) {
    console.log(`looping from ${start} until ${end}`)

    if(i<end){
      recurse(i+1)
    }
  }
recurse(start)
}

function MemoFnLoop(i,end) {
  console.log(`looping from ${i} until ${end}`
  if(i<end) {
    MemoFnLoop(i+1, end)
  }
}
MemoFnLoop(1,3)
```

### Accumulator
- technique: as build soln, keep passing it
```javascript
function joinElements(array, joinString) {
    //['s', 'cr', 't cod', ' :) :)'], 'e')

    function recurse(index, resultSoFar) {
      resultSoFar += array[index] //'secret cod'

      if(index === array.length -1) { //base case
        return resultSoFar
      } else {
        return recurse(index + 1, resultSoFar + joinString)
      }//2, 'secret'... - accumulating; incrementing index; getting closer 
    }
    return recurse(0, '')
}
    joinElements(['s', 'cr', 't cod', ' :) :)'], 'e')

function joinElementsIteratively(array, joinString) {
  let resultSoFar = ''

  for(let i = 0; i <= array.length -1; i++) {
    resultSoFar += array[i] + joinString
  }

  return resultSoFar + array[array.length - 1]
}

joinElementsIteratively(['s', 'cr', 't cod', ' :) :)'], 'e') //secret code :) :)
```


