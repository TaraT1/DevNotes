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