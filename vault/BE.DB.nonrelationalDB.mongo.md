---
id: pavk5nyvisfr8bhg9yx0fku
title: mongo
desc: ''
updated: 1694645733770
created: 1693859150944
---
### _id and id

_id field is the primary field for every document

- is mandatory
- is automatically indexed in every collection
- id is an alias for _id

source: https://stackoverflow.com/questions/9694460/difference-between-id-and-id-fields-in-mongodb

### findOneAndUpdate
Syntax: `db.collection.findOneAndUpdate(filter, update)`
- filter document: selection criteria for the update find()
- update document; To use replacement `db.collection.findOneAndReplace()`
- example: https://codeforgeek.com/findoneandupdate-in-mongodb/
- ref: https://www.mongodb.com/docs/manual/reference/method/db.collection.findOneAndUpdate/

### findByIdAndUpdate