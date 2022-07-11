---
id: rbar2jbq5o5giyon8ylu4s5
title: Objects
desc: 'Class 22 of Leon; ref: javascript.info/object'
updated: 1657219148415
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
