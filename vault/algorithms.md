---
id: y2xzpakn8cmjtrwy7e5ftrl
title: Algorithms
desc: ''
updated: 1715377599619
created: 1714068959019
---

Resources: 
- [Mayanwolfe Ultimate Guide to Js Algos Course 10.12.22]
(https://www.twitch.tv/mayanwolfe)
- [Codevolution Js Algos](https://www.youtube.com/playlist?list=PLC3y8-rFHvwiRYB4-HHKHblh3_bQNJTMa) [code](https://replit.com/@Codevolution/JavaScript-Algorithms#index.js)
- js.ds&a  [[DS&A|js.ds&a]] 
- [Big-O Cheat Sheet](https://www.bigocheatsheet.com/) 

## Big-O Notation
- describes complexity of an algorithm using algebraic terms
- expressed in terms of input
- focuses on bigger picture without getting caught up in details


## Big-O Time Complexity
- Linear time complexity
    - O(n) - Linear
    - as size of input increases, the time complexity also increases
    - ex: loops
- Constant Time Complexity
    - O(1) - Constant
    - Irrespective of value of n, expression is executed once
- Quadratic Time Complexity
    - O(n^2) - Quadratic
- Cubic Time Complexity
    - O(n^3) - Cubic
- Logarithmic Time Complexity
    - O(logn) - Logarithmc
    - input size reduces by half every iteration 
    

## Big-O Space Complexity
- Constant Space complexity
    - O(1) - constant
    - algo does not need extra memory or the memory needed does not depend on input size (constant space complexity)
    - ex: sorting algos. Sort within array w/o using additonal arrays
    
- Linear Space Complexity
    - O(n) - Linear
    - Extra space needed grows as input size grows
    
- Logarithmic Space Complexity
    - O(logn) - logarithmic
    - extra space needed grows but not at the same rate as the input size
    
## Big-O Complexity of Objects, Arrays, & Methods
### Objects
- object - collection of key value pairs; not ordered
- insert - O(1) (constant)
- Remove - O(1)
- Access - O(1)
- Search - O(n) (linear)
- Object.keys() - O(n)
- Object.values() - O(n)
- Object.entries() - O(n)

### Arrays
- array - ordered collection of values; start at index [0] and increment by 1
- insert/remove at end - O(1)
- indert/remove at beginning - O(n). (b/c index has to be reset for every remiaing element in the array)
- access - O(1)
- searching - O(n)
- push/pop - O(1)
- shift / unshift / concat / slice / splice - O(n)
- forEach / map / filter / reduce - O(n)

## Big-O Guide
[Know Thy Complexities](https://www.bigocheatsheet.com/)
- Calculation not dependent on input size - O(1)
- 1 loop - O(n)
- 2 nested loops - O(n^2)
- input size reduced by half - O(logn)

## Math Algorithms
### Fibonacci sequence
- Problem: given a number n, find the first n elements of the Fibonacci sequence
    - fibonacci sequence is a sequence in which each number is the sum of the two preceding ones
        - fibonacci(2) = [0,1]
        - fibonacci(3) = [0,1,1]
        - fibonacci(7) = [0,1,1,2,3,5,8]
        
    ```javascript
    function fibonacci(n) {
        const fib = [0,1]
        
        for(let i = 2; i <  n; i++){ // Note: i < 2 >>> NaN
            fib[i] = fib[i-1] + fib[i-2]
        }
        return fib
    }
    ```
    - Big-O = O(n) (linear) - the number of times n increases, the number of times expression for fib[i] increases
    - [[#recursion]]

### Factorial of a Number
- Problem: given integer n, find factorial of that int
    - in mathematics, the factorial of a non-negative integer (n!) is the product of all positive integers <= n    
    - factorial(0) = 1 ???
    - factorial(4) = 4*3*2*1 = 24
    - factorial(5) = 5*4*3*2*1 = 120
    ``` javascript
    function factorial(n) {
        let result = 1
        for(let i=1; i <= n; i++ ) {
            result = result * i
        }
        return result
    }
    console.log(factorial(0))
    console.log(factorial(4)) //24
    console.log(factorial(5)) //120
    ```
### Test for Prime Number
- Problem: integer greater than 1 that is not the produt of 2 natural numbers (numbers used for counting and ordering)
    - isPrime(5) = true( 1*5 or 5*1 )
    - isPrime(4) = false ( 1*4 or 2*2 or 4*1)
```javascript
function isPrime(n){
    if(n < 2){ // every num is divisible by 1
        return false
    }
    for(let i=2; i < n; i++){
        if(n % i === 0) {
            return false
        }
        return true
    }
}
console.log(isPrime(1)) //false
console.log(isPrime(5)) //true
console.log(isPrime(2)) //false
```
- Big-O: O(n) - Linear - as input increases, time complexity increases
### Test for Prime Number Optimized
- ints larger than sqrt can be eliminated. Whenever n=a*b one of the two factors is <= sqrt of n. For a composite number, there will be a divisor less than or equal to sqrt
```javascript
function isPrimeOptimized(n){
    if(n<2){
        return false
    }
    for(let i=2; i<= Math.sqrt(n); i++) {
        if(n%i === 0){
            return false
        }
    }
    return true
}
console.log(isPrime(1)) //false
console.log(isPrime(5)) //true
console.log(isPrime(2)) //false
```
## Recursion
Recursion is a problem solving technique where the solution depends on solutions to smaller instances of the same problem
- Function calls itself
- Recursive solutons need to have a base case -- a condition to terminate the recursion
- Recursion may simplify solving a problem, but it does not always translate to a faster solution
- Tips
    - Breakdown problem into smaller versions of same problem
    - figure  out a case for recursion

### Recursive Fibonacci Sequence
```javascript
function recursiveFibonacci(n){
    //Fn = F(n-1) + F(n-2)
    if(n < 2){
        return n
    }
    return recursiveFibonacci(n-1) + recursiveFibonacci(n-2)
}
console.log(recursiveFibonacci(2)) // [0,1]
console.log(recursiveFibonacci(3)) // [0,1,1]
console.log(recursiveFibonacci(7)) // [0,1,1,2,3,5,8]
```
- Big-O = O(2^n) (quadratic)
- [[#fibonacci-sequence]]

### Recursive Factorial of a Number
```javascript
function recursiveFactorial(n){
    //n! = n * (n-1)!
    if(n === 0){ //base case
        return 1
    }
    return n * recursiveFactorial(n-1)
}
console.log(recursiveFactorial(0)) //1
console.log(recursiveFactorial(1)) //1
console.log(recursiveFactoral(5)) //120
```
- Big-O=O(n)
- [[#factorial-of-a-number]]

## Search Algorithms
### Linear Search
Problem: Given aray of 'n' elements and target element of t, find the index of t in the array. Return -1 if target element is not found
- Start at first element of array and move towards the last
- Check if element is equal to target element
- if element found, return index of element
- if element not found, return -1
```
function linearSearch(arr, t){
    for(let i = 0; i < arr.length; i++){
        if(arr[i] === t) {
            return i
        }
    }
    return -1
}
console.log(linearSearch([-5, 2, 10, 4, 6], 10)) //2
console.log(linearSearch([-5, 2, 10, 4, 6], 6)) //4
console.log(linearSearch([-5, 2, 10, 4, 6], 20)) //-1
```
- Big-O = O(n); linear time complexity

### Binary Search
Problem: Given sorted aray of 'n' elements and target element of t, find the index of t in the array. Return -1 if target element is not found
- if arr is empty >>> return -1
- if arr has elements, find middle element in the array
- if middle element = target, return middle index
- if target < middle element binary, search left half of array
- if target > middle element binary, search right half of array
```
function binarySearch(arr, target){
    let leftIndex = 0
    let rightIndex = arr.length - 1

    while(leftIndex <= rightIndex) {
        let middleIndex = Math.floor((leftIndex + rightIndex) / 2)
        if(target === arr[middleIndex]){
            return middleIndex
        }
        if(target < arr[middleIndex]) {
            rightIndex = middleIndex - 1
        }
        if(target > arr[middleIndex]){
            leftIndex = middleIndex + 1
        }
    }
    return -1

}

console.log(binarySearch([-5, 2, 4, 6, 10], 10)) //4
console.log(binarySearch([-5, 2, 4, 6, 10], 6)) //3
console.log(binarySearch([-5, 2, 4, 6, 10], 20)) //-1
```
- Big-O=O(logn) - Within while loop, the input size is reduced by half