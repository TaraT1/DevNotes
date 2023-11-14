---
id: 6l4mferx9i6uw0fp4gn3trd
title: date
desc: ''
updated: 1711396415547
created: 1711395937955
---
ref: [mdn Date]( https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)  
With mongodb, node, ejs, Bs5  
    - FE: `<%= dateField.toISOString().slice(0, 10) %>`

[WDS Mongoose crash Course](https://www.youtube.com/watch?v=DZBGEVgL2eE&t=838s)
## Date in Mongo Schema
 ```javascript
  createdAt: {
    type: Date,
    immutable: true,
    default: () => Date.now,
  },
  updated: {
    type: Date,
    default: () => Date.now,
  },
```
 - Another way to add createdAt and updatedAt, is to just add a second argument to Schema( ), an object with a property timestamps set to true! 

 [[BE.nonrelationalDB.mongo]]