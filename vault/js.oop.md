---
id: 1v50pg31z8xw91e6r2n8y86
title: OOP
desc: ''
updated: 1660184265820
created: 1654984200676
---

https://youtu.be/PFmuCDHHpwk 
- OOP - Object Oriented Programming - programming paradigm (vs. procedural programming) - C#, Java, Ruby, Python, Js, etc.
	- system, paradigm, set of rules to structure code that:
		○ makes easier to add new stuff
		○ makes it easier to read through what was already coded
		○ not afraid to make changes

## OOP 4 Pillars
Encapsulation
	- fusion of data and functionality into one object
	- process of storing functions (methods) with their associated data (properties) in one object
	- reason why: makes easier to add new stuff, read through what's already coded, fearlessly make changes

Abstraction
	- complex or unnecessary details are hidden
	- makes code more simple, predictable, and manageable
	- reason why: code is smaller and more manageable; can make changes without worrying

Inheritance
	- Create new objects based on old ones
	- make class from another class to share set of properties and methods
	- reason why: helps eliminate redundant code

Polymorphism
	- piece of code that automagically works with bunch of different objects instead of conditionals and switch cases
	- allows override method in every child class 
	- reason why: helps avoid if/else and switch cases; code is more reusable; helps support other pillars


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

`# OOP Leon Class 31
```javascript
class Animal {
    constructor(name){
        this.name = name
    }
    speak(){
        console.log(`${this.name} makes a sound`)
    }
}

class Dog extends Animal{
    constructor(name,breed){
        super(name)
        this.breed = breed
    }
}

let yoMama = new Dog('Yomama', 'pit')

