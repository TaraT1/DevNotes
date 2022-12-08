---
id: kmutrdb8h4tpnbtlxvs59zq
title: JS
desc: ''
updated: 1670517719857
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