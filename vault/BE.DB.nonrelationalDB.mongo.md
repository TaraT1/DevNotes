---
id: pavk5nyvisfr8bhg9yx0fku
title: mongo
desc: ''
updated: 1725821848710
created: 1693859150944
---
[Learning Resource from MongoDB](https://learn.mongodb.com/)
## MongoDB Schema Design
Ref: mongodb [Schema Design Best Practices](https://www.youtube.com/watch?v=leNCfU5SYR8)
- Schema dzn is critical for improving performance and scalability of db
- no rules, process, or prescribed algo. Design schema that will work well with app
  - how store data
  - query performance
  - using reasonable amount of hardware
- Approaches: Embed vs Reference 

- embedding /nesting - saving data the way use; join
  - Method: [Mongo Nested Doc](https://www.youtube.com/watch?v=hjsCd3sy0Ns)
    - Embedded or nested json object OR array of documents
    ```javascript
    db.books.insertOne([ //can also use insertMany for inserting multiple documents
      {title: "title1", author: "author1", pages: 100, genres: ["genre1"], 
      reviews: [ {name: "namerev1", body: "rev1"}, {name: "namerev2", body: "rev2"} ], }
      ])
    ```
    
  - pro: retrieve data w single query. 
    - Avoids expense of joins or $lookup. (Joins are expensive time and memory wise)
    - Update all data w sgl atomic operation; is ACID compliant
  - con: large dox === more overhead
    - 16MB doc size limit per doc
- Reference - reference other dox from within another doc
  - allows for smaller dox while keeping refs to other data not as actively used
  - less likely to reach 16MB limit
  - no duplication of data. Normalizing or avoiding duplication of data is not a big concern
  - Avoids accessing infrequently accessed data
  - Con: 2 queries or $lookup required to retrieve all data
  
### Types of Relationships
- 1 to 1: using key-value pair
- 1 to Few: Embedded or nested object
- 1 to Many: Reference preferred 
- 1 to Squillions - e.g. server farm log files - unbounded amt of data per machine, reverse object id lookup
- Many to Many - Embed in each model. 2 way reference for 2 separate collections

### Recommendations for Schema Dzn
- Favor embedding unless compelling reason not to
- Needing to access object on its own is compelling reason
- Avoid joins and $lookups unless they can provide better schema dzn
- arrays should not grow without bound. Use reverse referencing in separate document
- how model data depends on application's data access patterns

### Schema Validation
[WDS Mongoose crash Course](https://www.youtube.com/watch?v=DZBGEVgL2eE&t=838s)
- Schema validation only works with create() or save(). Other methods work directly on the mongodb database (findByIdAndUpdate, etc.) Workaround: findById, then use save()

### Hybrid
- outlier pattern: overflow

## MongoDB
Refs: 
- Modeling: https://university.mongodb.com/course...
- 6 Rules of Thumb for MongoDB Schema Design: Part 1: https://www.mongodb.com/blog/post/6-r...
- Data Model Design: https://docs.mongodb.com/manual/core/...
- Data Model Examples and Patterns: https://docs.mongodb.com/manual/appli...
- Building with Patterns: A Summary: https://www.mongodb.com/blog/post/bui...
- 'tube:  wds MongoDB Crash Course
- cheatsheet: webdevsimplified.com/mongodb-cheat-sheet.html

### req, res
req: 
- req.params - gets properties attached to named route params (URL)
- req.body - used in PUT/POST txns, i.e., for forms
- req.query - sort, filter, search, pagination

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

## Mongoose
- Mongoose is an Object Data Modeling (ODM) library for MongoDB and Javascript. 
- It manages relationships between data, provides schema validation, and is used to translate between objects in code and the representation of those objects in MongoDB. 
- Reference: https://www.geeksforgeeks.org/mongoose-vs-mongodb/
- reference for learning: 'tube: wds Mongoose Crash Course - Beginner Through Advanced
- It is a wrapper around mongodb that works in nodejs
- cheatsheet: webdevsimplified.com/mongodb-cheat-sheet.html

### Dates
- schema dzn: createdAt, updatedAt: ( {schema...}, {timestamps: true} )
Mongoose will then set createdAt when the document is first inserted, and update updatedAt whenever you update the document using save(), updateOne(), updateMany(), findOneAndUpdate(), update(), replaceOne(), or bulkWrite(). [mongoose dox for timestamps](https://mongoosejs.com/docs/timestamps.html)

### Concepts
- Schema - defines structure of data. E.g. User has name, email, etc
- Model - Schema in actual form that can be used
- Query -  query against db

## Errors and (Hopefully) Fixes
Errors arise with authentication and validation because of different methods needed in handling different objects. Check for null or undefined values.

### App Structure and pkgs (Node)
The most important part of the order is to have passport.initialize() and passport.session() come after your express-session configuration.
```javascript
const session = require('express-session')

passport.initialize()
passport.session()

//also need body parser
app.use(bodyParser.json());
app.use(bodyParser.urlencoded({ extended: false }));

app.use(session({ secret: 'keyboard cat' }));
```

### Mongo Object IDs
- mongo object and javascript object 
- findById vs findOne
- `await Model.find({user: req.user.???})`
    - User.user._id - Leon uses microsftId
    - `const stories = await Story.find({ user: req.user.id })` - Traversy

``` javascript
/Traversy
//POST
req.body.user = req.user.id
await Story.create(req.body)
//GET
const stories = await Story.find({})
    .populate('user')
//GET /:id
if (story.user._id != req.user.id && story.status == 'private') {
      res.render('error/404')
    } else {
      res.render('stories/show', {
        story,
      })
    }
// edit // @route   GET /stories/edit/:id
router.get('/edit/:id', ensureAuth, async (req, res) => {
  try {
    const story = await Story.findOne({
      _id: req.params.id,
    }).lean()

    if (!story) {
      return res.render('error/404')
    }

    if (story.user != req.user.id) {
      res.redirect('/stories')
    } else {
      res.render('stories/edit', {
        story,
      })
    }
  } catch (err) {
    console.error(err)
    return res.render('error/500')
  }
})
//PUT
router.put('/:id', ensureAuth, async (req, res) => {
try {
let story = await Story.findById(req.params.id).lean()

if (!story) {
    return res.render('error/404')
}
   if (story.user != req.user.id) {
      res.redirect('/stories')
    } else {
      story = await Story.findOneAndUpdate({ _id: req.params.id }, req.body, {
        new: true,
        runValidators: true,
      })

router.delete('/:id', ensureAuth, async (req, res) => {
  try {
    let story = await Story.findById(req.params.id).lean()

    if (!story) {
      return res.render('error/404')
    }

    if (story.user != req.user.id) {
      res.redirect('/stories')
    } else {
      await Story.deleteOne({ _id: req.params.id })
      res.redirect('/dashboard')
    }
  } catch (err) {
    console.error(err)
    return res.render('error/500')
  }
})

// @desc    User stories
// @route   GET /stories/user/:userId
router.get('/user/:userId', ensureAuth, async (req, res) => {
  try {
    const stories = await Story.find({
      user: req.params.userId,
      status: 'public',
    })
      .populate('user')
      .lean()

    res.render('stories/index', {
      stories,
    })
  } catch (err) {
    console.error(err)
    res.render('error/500')
  }
})

```
## Mongo Methods and Operators
### Insert
- insertOne
- insertMany

### Find
- find
- findOne

### Operators 
- Filters
  - $gt - greater than /$gte - greater than or equal to
  - $lt - lesser than / $lte - less than or equal to 
  - $or - [{ rating: 7}, {rating: 9}] //return objects with rating of 7 or 9
  - $in - find documents within stated range 
  - $nin - find documents not in array of values
  - $all - Get all within array of values
- Document Modifiers
  - $set - allows setting of as many fields as want in document
  - $inc - increment - can be positive or decrement - negative - db.books.updateOne({_id: ObjectId("...")}, {$inc: {pages: 2}}) //or {$inc: {pages: -2}}
  - $push - push items or values to array
  - $pull - take items or values out of array 
  - $each - takes array as value, allows to push several values
```javascript
//Mongo Doc
_id: ObjectId("...")
title: "title1"
author: "author1"
rating: 9
pages: 250
genres: Array
  0: "fantasy"
  1: "magic"
reviews: Array
  0 Object
    name: "nameIt"
    body: "lovely"
  1 Object
    name: "namenameIt"
    body: "lovelylovely"


db.books.find({ rating: {$gt: 6}}) //greater than, non-inclusive
db.books.find({ rating: {$lt: 6}}) //less than db.books.find({ rating: {$lte: 7}}) //less than or equal to; gte: greater than or equal to
db.books.find({ rating: {$gte: 7}, author: 'authorQ'}) //Additional filter 
//Filters
db.books.find({$or: [{pages: {$lt: 300}}, {pages: {$gt: 400}} ] })
db.books.find({ rating: {$in: [7,8,9] }})
db.books.find({ rating: {$nin: [7,8] }})
```
### Querying within array
genres: ["fantasy", "magic"] (array)
``` javascript
db.books.find({genres: "fantasy"}) //finds documents containing "fantasy"
db.books.find({genres: ["fantasy", "match"]} ) //finds documents where it's exact match 
db.books.find({genres: {$all: ["fantasy", "sci-fi"]}})
```
### Querying within Nested Objects
db.books.find({"reviews.name": "nameIt"}) //Using .notation, put property name in quotations; returns object 1

### Populate
https://dev.to/paras594/how-to-use-populate-in-mongoose-node-js-mo0
- Replaces path in document with documents from other collections
- define refs in schema and mongoose uses refs to look for docs in other collection
  - if no docs found, returns null
  - can chain populate method for populating multiple fields
  - if 2 populate methods populate same field, second populate overrides first one

### Aggregate
https://learn.mongodb.com/learn/course/mongodb-aggregation/lesson-1-introduction-to-mongodb-aggregation/learn  

https://www.digitalocean.com/community/tutorials/how-to-use-aggregations-in-mongodb
- Mongo's query mechanism doesn't allow grouping or transforming data returned from queries. Thus options for performing meaningful data analysis with mongo's query mechanism is limited.
- MongoDB provides aggregation operations through aggregation pipelines - series of operations that process data documents sequentially
- [How to Create Queries in mongodb](https://www.digitalocean.com/community/tutorials/how-to-create-queries-in-mongodb)

#### Aggregation Pipelines
- built as sequential series of declarative data processing operations known as stages
- each stage inspects and transforms documents as they pass through pipeline and feed into subsequent stages for further processing
- Stages can perform operations on data like filtering, sorting, transforming, grouping
- analogy: restaurant kitchen preparing vegetables

### Delete
- deleteOne({_id: ObjectId("...")})
- deleteMany
  ```javascript
  db.books.deleteMany({author: "author1"}) //deletes books with author author1
  ```

### Update
- updateOne() - db.books.updateOne({_id: ObjectId("...")}, {$set: {rating: 8}})
- updateMany() - db.books.updateMany({author: "author2" }, {$set: {author: "auteur"}})