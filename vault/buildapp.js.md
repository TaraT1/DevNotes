---
id: kmutrdb8h4tpnbtlxvs59zq
title: JS
desc: ''
updated: 1738448764156
created: 1664214557269
---
New Ref: [perplexity for arr of objects](https://www.perplexity.ai/search/for-a-crud-app-using-mongodb-e-uJ6bGzBWQ865mWn004S9Hw)

- clone Leon's full-stack-template or Binary Upload Boom
- !!! clone Leon's template
- modify Update deps

I think clone is the way to go. I think writing from scratch with copy paste...

clone =>>> copy/paste

Know when to copy paste what - MayanWolfe

.env: Run db...
With DB_STRING add user:pword after @cluster...mongodb.net/<database_name>?...

## Controllers
A controller is a callback function that corresponds to the router to handle requests
- convention to name controller the same as route it's handling

[Resource](https://lo-victoria.com/build-a-rest-api-with-nodejs-routes-and-controllers)

todo scratch build - Mayanwolfe FS CRUD
## Install nodejs
```javascript
npm init
npm install express mongoose ejs dotenv cors
npm install nodemon --save-dev
```
produces package.json file, etc.

## Dependencies
dotenv
ejs
express
method-override
mongodb
mongoose
morgan
passport.js

devDependencies
cross-env
nodemon


## env vars
port
db connection

## views
for ejs files to display to users

## public for static files

## models
database schemas

# Delete
Avoid using get in routes for delete
- search engines crawl get routes for indexing. Using a tag to delete, search engine will delete
```javascript
router.get('/:id', (req, res) => {
    res.send('Show' + req.params.id)
})

//Delete needs method override. Doing with form
router.delete('/:id', (req, res) => {
    res.send('Delete ' + req.params.id)
})
```

# Dir Structure
## Config
.env
database.js

## Routes
(webdevsimplified)
```javascript
const express = require('express')
const router = express.Router()
const Author = require('..models/author')
const Book = require('..models/book')

router.get('/', async (req, res) => {
    let searchOptions = {}
    if (req.query.name != null && req.query.name !== '') {
        searchOptions.name = new RegExp(req.query.name, 'i')
    }
    try {
        const authors = await Author.find(searchOptions)
        res.render('authors/index', {
            authors: authors,
            searchOptions: req.query
        })
    } catch {
        res.redirect('/')
        }
        })

//New Author Route
router.get('/new', async (req, res) => {
    res.render('authors/new', {author: new Author() })
})
//Create Author Route
router.post('/', async (req, res) => {
    const author = new Author({
        name: req.body.name
    })
    try {
        const newAuthor = await author.save()
        res.redirect(`authors/${newAuthor.id}`)
    } catch {
        res.render('authors/new', {
            author: author,
            errorMessage: 'Error creating Author'
        })
    }
})

//?? what is this get for?; after this are edits
router.get('/:id', async (req, res) => {
  try {
    const author = await Author.findById(req.params.id)
    const books = await Book.find({ author: author.id }).limit(6).exec()
    res.render('authors/show', {
      author: author,
      booksByAuthor: books
    })
  } catch {
    res.redirect('/')
  }
})






```
## Routes & Controllers
(100devs)
routes
```
const express = require('express')
const router = express.Router()
const todosController = require('../controllers/todos')
//+const {ensureAuth} = require('../middleware/auth')

router.get('/', todosController.getTodos)
router.post('/createTodo', todosController.createTodo)

//...

```
controller object syntax
```javascript
// todo-mvc-auth
const Todo = require('../models/Todo')

module.exports = {
    getTodos: async (req, res) => {
        console.log(req.user)
        try{
            const todoItems = await Todo.find({userId:req.user.id})//{db object}; Note db commands
            const itemsLeft = await Todo.countDocuments({userId:req.user.id, completed: false})
            res.render('todo.ejs', {todos: todoItems, left: itemsLeft, user: req.user})
        }catch(err){
            console.log(err)
        }
    },
    createTodo: async (req, res) => {
        try {
            await Todo.create({todo: req.body.todoItem, completed: false, userId: req.user.id })
            console.log('Todo has been added')
            res.redirect('/todos')
        }catch(err){
            console.log(err)
        }
    },
    //...
    
}//module.exports

```

Good ref: [mdn Express Framework](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs)
### Route Syntax
express.Router object
```js
// wiki.js - Wiki route module

const express = require("express");
const router = express.Router();

// Home page route - /URL, callback function (req, res)
router.get("/", function (req, res) {
  res.send("Wiki home page");
});

// About page route
router.get("/about", function (req, res) {
  res.send("About this wiki");
});

module.exports = router;

//To use router in app file:
const wiki = require(".wiki.js");
//...
app.use("/wiki", wiki);

```
### middleware function
routes have req, res. Middleware callbacks access req, res, next
```js
const midware = function (req, res, next){
    //...
    next()//for next middleware func
}

//for all routes & verbs
app.use(midware)
//for specific route
app.use("/route", midware)
//for specific http verb
app.get("/", midware)
```
Can declare route handler middleware functions separately and the set as callback or declare callback function when used

- Routes forward supported requests and info encoded in req URLs to controller funcs
- Controller functions get req from models, create html page, return to user in browser
- Views or templates render data from controller

![](/assets/images/MVC routes.jpg){max-width: 400px, display: block, margin: 0 auto}

### Dates
- From momentjs, [Alternatives to momentjs](https://momentjs.com/docs/#/-project-status/recommendations/)
    - momentjs.com - not recommend to use going forward. Legacy project in maintenance mode. 
        - built on previous era of js ecosystem
        - [ref](https://momentjs.com/docs/#/-project-status/)
- Modify date object from db. Format it in the controller of the get request for server-side formatting
- for ejs, send formatted date in a variable to ejs
### res.render vs res.redirect 
Ref: https://dev.to/mochafreddo/understanding-resredirect-and-resrender-in-expressjs-usage-and-security-measures-2k60
- Redirect: redirects to an endpoint. (Typically used for routing it seems)
- Render: returns the ejs template itself
 ### Contact Forms
 - [netlify forms](https://www.netlify.com/platform/core/forms/)
 - [formspree](https://formspree.io)
