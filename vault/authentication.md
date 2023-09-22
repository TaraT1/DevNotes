---
id: p669krwb3vq2q81ckdfqn31
title: Authentication
desc: ''
updated: 1695587019467
created: 1695399712830
---
Refs: https://www.freecodecamp.org/news/a-quick-introduction-to-oauth-using-passport-js-65ea5b621a/  
https://www.freecodecamp.org/news/how-to-dance-the-oauth-a-step-by-step-lesson-fd2364d89742/

Implementing authentication with js/express from Raffy's nodejs notes project
```js
//** Add packages to app.js/server.js
//after connectDB
const session = require("express-session");
const passport = require("passport"); //auth
const MongoStore = require("connect-mongo");

//Setup session stored in mongo (MongoStore)
app.use(session{...})
//Configure /Initialize passport around port
app.use(passport.initialize())
app.use(passport.session())

//Add authentication route w other routes

//** Add new .js route in routes (auth.js)
const express = require('express');
const router = express.Router(); 
const passport = require('passport');  
const GoogleStrategy = require('passport-google-oauth20').Strategy;

//passportjs.org ref. Strategy. Raffy uses passport-google-oauth20 strategy



module.exports - router;
```
- will need to get client id, client secret. From google: [Google's Developers Console](https://console.developers.google.com/)
- look up how to create a new project 
- select project > dashboard > api overview > credentials > create credential (OAuth client id)
- configure consent screen 
```
user type: external
app name
support email
app home page...

auth js origins 
localhost

auth redirect uris
localhost/google/callback

select project 
from dashboard > api overview > create credentials
OAuth client > configure consent screen
Create OAuth Client id
- User Type: external
App info, domain... save
Credentials: OAuth > web app
authorized js origiins uRI
authorized redirect uris; localhost/google/callback

create oauth client id. get client secret
```