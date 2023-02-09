---
id: kmutrdb8h4tpnbtlxvs59zq
title: JS
desc: ''
updated: 1675360466469
created: 1664214557269
---
- clone Leon's full-stack-template or Binary Upload Boom
- !!! clone Leon's template
- modify

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