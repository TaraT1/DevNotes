---
id: pavk5nyvisfr8bhg9yx0fku
title: mongo
desc: ''
updated: 1717599080673
created: 1693859150944
---
## MongoDB
- reference: 'tube:  wds MongoDB Crash Course
- cheatsheet: webdevsimplified.com/mongodb-cheat-sheet.html

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

