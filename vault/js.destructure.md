---
id: zldxloelz5qv3t7mhjqkeoo
title: Destructure
desc: ''
updated: 1662325558936
created: 1662324483581
---
Destructuring assignment is a js expression that makes it possible to unpack values from arrays, or properties from objects, into distinct vars
- data can be extracted and assigned to vars
- lefthand side defines which val should be unpacked from sourced var

```javascript
//array destructuring
[x, y, ...restof] = [10, 20, 30, 40, 50];
console.log(x); // 10
console.log(y); // 20
console.log(restof); // [30, 40, 50]

//object destructuring
({ x, y} = { x: 10, y: 20 });
console.log(x); // 10
console.log(y); // 20
```


Resource: [FCC Destructuring](https://www.freecodecamp.org/news/array-destructuring-in-es6-30e398f21d10/)

- simplified method of extracting multiple properties from an array
- takes the structure and deconstructs it into its own constituent parts through assignments
- uses syntax like array literals, uses position
- can't use numbers, since can't be var names

```javascript
var [first, second, third] = ["Laide", "Gabriel", "Jets"];

//with destructuring
var first = "Laide",
    second = "Gabriel",
    third = "Jets";

var thing = ["Table", "Chair", "Fan"];
var [a,b,c] = thing;

console.log(a); //Table
console.log(b); //Chair
console.log(c); //Fan
```

- if # of vars passed to destructuring array > elements in the array >>> unmapped vars are undefined
- if # of vars passed to destructuring array < elements in the array >>> elements w/o vars are left -- no errors

## Destructuring Returned Arrays

- works for all iterables

```javascript
function runners(){
    return ["Sandra", "Ola", "Chi"];
}

var [a,b,c] = runners();
console.log(a); //Sandra
console.log(b); //Ola
console.log(c); //Chi
```

- Default Value can be assigned to a var if no val or undefined (fallback)
- can ignore some values

## Rest Parameter and Spread Syntax

- ... operator (ES6)
  - Rest Parameter

    - left-hand side in destructuring
    - used to map remaining elements in array that have not been mapped to the rest var
    - Throws SyntaxError if not last
  - Spread syntax

    - appears on right-hand side in destructuring
    - takes all other elements in the array which have no var mapped to them and maps it to rest var

## Other Aspects of Destructuring

- Interchanging or Swapping Vars
- Nested Array Destructuring
- Multiple Array Destructuring
