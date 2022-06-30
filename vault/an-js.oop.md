---
id: ni8kebskl2y4ijz8c6163z9
title: Oop
desc: ''
updated: 1654989192929
created: 1654984200676
---

https://youtu.be/PFmuCDHHpwk 
- OOP - programming paradigm (vs. procedural programming)
-C#, Java, Ruby, Python, Js, etc.

## OOP 4 Pillars
- Encapsulation - group related vars & funcs together; 
    - Benefit: reduces complexity and increases reusability
Abstraction - Simpler interface, Benefit:
    - reduce complexity & isolate impact of changes
Inheritance -  Define generic object and have other objects inherit properties and methods
    - Benefit: mechanism allowing eliminate redunant code.
Polymorphism - many forms; technique allowing eliminate if...else or swtich/case statements
    - Benefit: refactor switch-case statements


```javascript
//procedural - lots of parameters. Fewer params means ease of maint
let baseSal = 30_000;
let overtime = 10;
let rate = 20;

function getWage(baseSal, overtime, rate){
    return baseSal + (overtime * rate);
}

//OOP way
let employee = {
    baseSal: 30_000,
    overtime: 10,
    rate: 20,
    getWage: function() {
        return this.baseSal + (this.overtime * this.rate);
    }  
};
employee.getWage():


// Factory function
function createCircle(radius) {
    return {
        radius,
        draw: function() {;
            console.log('draw');
        }
    };
}
const createCircle(1);

// Constructor Function - this keyword and new keyword
function Circle(radius){
    this.radius = radius;
    this.draw = function(){
        console.log('draw');
    }
}
const another = new Circle(1); // without new operator, points to global object window




```

- Every object has constructor properties that refereces the function used to create object
```javascript
new String();//'', "",``
new Boolean();//true, false
new Number();//1, 2, 3,...

Circle.call({}, 1);
Circle.apply({}, [1,2,3]); //apply method can pass vals to another arr
```

## Value Types v. Reference Types
Value Types (primitives)
- number, string, bool, symbol, undefined, null

Reference Types
- object, function, array

- Primitives are copied by their value
- Objects are copied by their reference

## Adding/Removing Properties
- Bracket notation - useful for special characters and spaces
- . notation
- delete keyword
    ``` delete circle['location']; //or circle.location;

## Iteration
- Iterate members in object with for in loop
- Object.keys - get all keys in object
- in operator provides property or method of object if exists

```javascript
function Circle(radius){
    this.radius = radius;
    this.draw=function() {
    }
}

const circle = new Circle(10);

for (let key in circle) { //Iterate members in object with for in loop
    if (typeof circle[key] !== 'function')
    console.log(key, circle[key]);
}

const keys = Object.keys(circle);
console.logs(keys);

if ('radius' in circle){
    console.log('Circle has radius');
}
```
## Abstration - hide details, expose only essentials
