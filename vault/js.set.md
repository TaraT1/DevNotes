---
id: gwxhtg7an9w87dpqwttkmqz
title: Set
desc: ''
updated: 1737343913537
created: 1718299051923
---
# Js.Set() (Javascript Set)
- set objects are collections of values. Value in the set may only occur once. Iterable, insertion order corresponds to the order in which each element was inserted into the set by add()
- Set() can only be constructed with new. Attempting to call it without new throws a TypeError.
- spec requires sets be implemented that on avg provide access times that are sublinear on number of elements in the collection. Could be represented as hash table (O(1)), search tree (O(log(N))) or any data structure as long as complexity is better than O(N)

## Map vs Set
Map in JavaScript behaves similarly to a hashmap, offering O(1) average-case time complexity for insertion, deletion, and lookup operations under optimal conditions. The choice between using a Map or a Set should be based on the specific requirements of your application, such as the need for unique values (Set) or the necessity to associate values with keys (Map).

## Leetcode, etc
https://leetcode.com/problems/contains-duplicate/
https://www.codewars.com/kata/57a5b0dfcf1fa526bb000118/train/javascript

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from omg Array.from() returns a shallow copy lol

[Union, intersection, difference, and more are coming to JavaScript ...](https://www.sonarsource.com/blog/union-intersection-difference-javascript-sets/#what-are-the-new-set-functions)

[replit: Javascript Set()](https://replit.com/@jmarthagodfrey/Javascript-Set?v=1)


- There are tradeoffs for storage in performance, etc for big-O

Set.size returns number of key:value pairs
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/size

https://www.sonarsource.com/blog/union-intersection-difference-javascript-sets/#what-are-the-new-set-functions

