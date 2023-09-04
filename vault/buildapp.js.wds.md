---
id: 2djyd9rub8uxdo6cugk4bn8
title: Wds
desc: ''
updated: 1685469985894
created: 1685222749195
---
## Overview
- install dependencies
- setup server
- setup controllers
- setup views
- setup models
# Project Setup (Server, etc)
- Using wds
``` bash
npm init -y #-y defaults params to yes; 
# In package.json change main: from index.js to server.js

# Install dependencies
npm i express ejs express-ejs-layouts
# i: install; express: server; ejs: templating; express-ejs-layouts: can create layout file for html. Adds to pkg.json and creates lock

# Setup Dev Env
npm i --save-dev nodemon #restarts server after code changes
```

## Modify scripts for run server commands
Modify package.json:  
```bash
"scripts": { #dont need test line
    "start": "node server.js",
    "devStart": "nodemon server.js"
    }, #...
```
### Commands to invoke:
``` bash
npm run start #prod
npm run devStart #dev
```

## Setup server.js
``` javascript
const express = require('express')
const app = express()
const expressLayouts = require('express-ejs-layouts')

//configure express app
app.set('view engine', 'ejs')
app.set('views', __dirname + '/views')
app.set('layout', 'layouts/layout')
app.use(expressLayouts)
app.use(express.static('public'))

app.listen(process.env.PORT || 2121)
```
## Config
.env
database.js

## Controller /Route 
- Routes instead of controllers in node.js express land.
``` javascript
//imports
const express = require('express')
const router = express.Router()

//configure
router.get('/', (req, res) => {
    res.send('Hey baaaaby')
})
    
//export
module.exports = router

//connect route to server
//server.js: 
//...
const indexRouter = require('./routes/index')
//... 
app.use('/', indexRouter)
```
## Views
folder structure:  
views  
  /layouts (templates)  
    layout.ejs  
    index.ejs  
  /partials  
    errorMessage.ejs
    footer.ejs  
    header.ejs  
  /view1  
    crud.ejs  
    __form_fields.ejs  
    


## Models
``` javascript
const mongoose = require("mongoose");

const ProviderSchema = new mongoose.Schema({
    name: {
        type: String,
        required: true,
    },
    specialization: {
        type: String,
        required: false,
    },
    createdAt: {
        type: Date,
        required: true,
        default: Date.now,
    },
});

module.exports = mongoose.model("Provider", ProviderSchema);`
```









