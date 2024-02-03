---
id: 3kqsaly41wz3amyuczdy1uc
title: DS&A
desc: '100devs'
updated: 1708011449942
created: 1666456198768
---
[Scotch.io Ultimate Algorithms Course](http://web.archive.org/web/20210616161653/https://scotch.io/courses/the-ultimate-guide-to-javascript-algorithms)
https://scotch.io/courses/the-ultimate-guide-to-javascript-algorithms

Resource: [Mayanwolfe Ultimate Guide to Js Algos Course 10.12.22]
(https://www.twitch.tv/mayanwolfe)

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

Properties:

- input - 0 or more externally provided
- output - 1 or more
- correctness - every step
- definiteness
- finiteness

Considerations for efficency:

- time complexity (execution time of an operation)
- space complexity (memory usage of an operation)

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
  - Asymptotic notation is std of expressing algo in terms of time and space complexity. Most common is David Knuth's Big O Notation. aka upper bound of an algorithm or worst case indicates func won't exceed or take more than specific time to execute irrespective of value of input(n)
- posteriori analysis - practical evaluation carried out by implemention and observation of time taken and memory consumed

## 100devs

- A data sctructure is an organized way of storing data. It is a pattern of collecting and organizing data for performing various operations correctly and efficiently
- An algorithm is the steps one takes to solve a problem
- Thinking through appropriate algorithms is how to efficiently solve problems

  - space - how much memory is used
  - time - how many operations executed per input
- Use Big-O Notation to determine efficiency of solutions

  - mathematically describes the complexity of algo in terms of time and space
  - provides rough estiamtes
- Common Complexities (MIT's CS curriculum are online)

  - O(1) - Order 1, Constant Time

    - for all inputs only one operation required
    - Example: access array

    ```js
    const nums = [1,2,3,4,5]
    const firstNum = nums[0]
    ```
  - O(N) - Order n, Linear, Linear Scaling

    - for all inputs to algo, there will be one operation per input
    - operation for each input
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
          return lastItem * (lastItem + 1) / 2
      }
      const nums = [1,2,3,4,5]
      const sumOfArray = sumContiguousArray(nums)
      ```
  - O(N^2) - Quadratic

    - example: nested for loops

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
        return false
    }

    const nums = [1,2,3,4,5]
    hasDupes(nums) //true
    ```
  - O(LOG N) - logarithmic time

    - as you loop, operations are halved
    - can be efficient especially with large amts of inputs
    - example: divide and conquer
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

## Js Complexities

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
