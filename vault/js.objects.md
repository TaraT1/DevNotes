---
id: rbar2jbq5o5giyon8ylu4s5
title: Objects
desc: 'Class 22 of Leon; ref: javascript.info/object'
updated: 1719272933287
created: 1654630765740
---
# Objects
- store keyed colls of various data and more complex entities
- collection of properties (vars) and methods (funcs)
- represent attrs & behaviors of something used in prgm
- var attached to object - property
- func attached to object - method


## Creating objects
- {...} - object literal with optional list of properties (key: value pair)
    - key is property name, aka name or identifier
    - value can be anything

## Access property
- property values are accesssible using dot notation - ```obj.property```
- square brackets - ```obj["property"]```
    - for multiword properties, dot access doesn't work
    - much more powerful than dot notation and more cumbersome - use for more complex

## &c operators
- delete operator removes property - 
```delete obj.prop```
- multi-word property names must be quoted
- trailing or hanging comma is okay
    ```javascript
    let key = "likes birds";
    //same
    user[key] = true;
    ```
- check if prop w given key exists ```"key" in ob```
- iterate over object ```for (let key in obj)``` loop


### Physical object - stopwatch
```javascript
let stopwatch = {} //literal notation
stopwatch.currentTime = 12

stopwatch.tellTime = function(time) {
	console.log(`The current time is ${time}.`)
}

stopwatch.tellTime(stopwatch.currentTime)
```

## Objects
- Car factory

### Constructor 
- capitalize func name in constructor

```javascript
function MakeCar(carMake, carModel, carColor, numOfDoors){
    this.make = carMake
    this.model = carModel
    this.color =  carColor
    this.doors = numOfDoors
    this.honk = function(){
        alert(`beep beep`)
    }
    this.lock = function(){
        alert(`Locked ${this.doors} doors`)
}

let hondaCivic = new MakeCar('Honda', 'F1', 'Silver', 2)

let teslaRoadster = new MakeCar('Tesla', 'X', 'Black', 4)

console.log( teslaRodadster.doors.toString()) //prototypal inheritance from object global prototype

```

### prototypal inheritance in Js
- a prototype is another object used as fallback source of properties and methods
- checks self, checks constructor >>> prototype chain goes to global object prototype
- everything in Js is an object

## Class
- syntatical sugar that brings Js constructors in line with other languages
- classes are like templates for objects
- has prototypal inheritance
```javascript
class MakeCar {  //no parenths here
    constructor(carMake, carModel, carColor, numOfDoors){
        this.make = carMake
        this.model = carModel
        this.color = carColor
        this.doors = numOfDoors
    }
    honk(){
        alert('beep')
    }
    lock(){
        alert('click')
    }
}

let hondaCivic = new MakeCar('Honda', 'Civic', 'Silver', 4)
```

ref: [brocode js full course](https://www.youtube.com/watch?v=lfmg-EJ8gm4&t=15498s)

# Objects
- collection of related properties &/or methods

``` javascript
// SYNTAX
object = {
key: value,
function(){...}
}

// EXAMPLES
person1 = {
    firstName: "Yup",
    lastName: "Ya",
    saySomething: function() {
        console.log("t's up?")
        console.log(`My name is ${person1.firstName}`)
    }
}

person2 = {
    firstName: "Void",
    lastName: "City",
    saySomething: function() {
        console.log(`My name is ${this.firstName}`)
    }
}

console.log(person1.firstName)
console.log(person1.lastName)

person1.saySomething()
//
```
## this
- reference to object where THIS is used. Depends on immediate context i.e., `person.name = this.name`
- THIS keyword 
    - outside of object `.this` references window object `console.log(this)`
    - `.this` does not work with arrow functions within objects. `.this` references same scope as parent or window object if in a browser
    - Arrow functions don't have their own bindings to .this, arguments, or super, and should not be used as methods. Because the arrow function doesn't have a "this", it uses the parent's "this". "this" always points to the parent, and the parent of the person object is Window (if you're in a browser).
    
    ``` javascript
    const poison = 
        name: 'My Name'
        saySomething: () => { console.log(`My name is ${this.name}`) // .this references window /parent object 
    }
    ```
## Constructors
- reusable method for defining properties & methods of objects; helps with code reusability
``` javascript
functon Car(make, model, year, color) {
    this.make = make, //this assigns properties
    //...
    this.drive = function(){
        console.log(`You drive the ${this.model}) 
        }        
//create instance of object created from construction
const car1 = new Car("ford", "mustang", 2024, "blk")
const car2 = (...)

console.log(car1.make)
console.log(car1.model)
console.log(car1.year)

console.log(car2. ...)
```
## Classes
- ES6 feature that provides more structured and clean way to work with objects compared to traditional constructor functions 
- syntax: 
``` javascript
class ClassName {
    constructor(param1, param2)
        this.param1 = param1
        this.param2 = param2
}
    method() {
        //don't need function keyword inside of class
    }
```
``` javascript
class Product {
    constructor(name, price) {
        this.name = name
        this.price = price
    }
    
    displayProduct() { 
        console.log(`Product: ${this.name}`)
        console.log(`Price: ${this.price.toFixed(2)}`)
    }
}
const product1 = new Product("Shirt", 19.99)
const product2 = new Product("Pants", 19.50)

product2.displayProduct() //invokes displayProduct method
```
## Static
- keyword that defines properties or methods that belong to a class itself rather than the objects created from that class. (Class owns anything static, not the objects)
``` javascript
class MathUtil{
    static PI = 3.14159

    static getDiameter(radius){
        return radius * 2
    }
    static getCircumference(radius){
        return 2 * this.PI * radius
    }
    static getArea(radius){
        return this.PI * radius * radius
    }
}

console.log(MathUtil.PI)//3.14159 
console.log(MathUtil.getDiameter(10))//20
console.log(MathUtil.getCircumference(10))//62.8318
console.log(MathUtil.getArea(10)) //314.159

//Example 2
class User {
    static userCount = 0

    constructor(username){
        this.username = username
        User.userCount++
    }

    static getUserCount(){
        console.log(`There be ${User.usercount} dragons`)
    }

    sayHello(){
        conosle.log(`Dragon ${this.username} here`)
    }
}
const user1 = new User("Brand New")
const user2 = new User("Notso BrandNew")

console.log(user1.username) //Brand New
console.log(user1.userCount) //undefined - userCount belongs to class not object created from the class
console.log(User.userCount) //1
console.log(user2.username) //Notso BrandNew
console.log(User.userCount)// 2

user1.sayHello()
user2.sayHello()
console.log(User.getUserCount) //errors - reprints method
user.getUserCount() //There be 2 dragons
```

# Inheritance
- allows new class to inherit properties and methods from an existing class (parent -> child); 
- helps with code reusability

``` javascript
class Animal {
    alive = true
    eat() {
        console.log(`This ${this.name} eats`)
    }
    sleep() {
        console.log(`This ${this.name} zzzzz`)
    }
}
class Rabbit extends Animal {
    name = "rabbit"
}
class Fish extends Animal {
    name = "fish"
}
class Hawk extends Animal {
    name = "hawk"
}

const rabbit = new Rabbit()
const fish = new Fish()
const hawk = new Hawk()

console.log(hawk.alive) //true
hawk.eat //This hawk eats
hawk.sleep //This hawk zzzzz
```
## super
- keyword used in classes to call the constructor or access properties & methods of a parent (aka superclass)
```
this = this object
super = the parent
```
``` javascript
class Animal {
    constructor() {

    }

class Wabbeet extends Animal {

}
class Fish extends Animal {

}
 class Hawk extends Animal {
    
 }

}