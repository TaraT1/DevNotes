---
id: p669krwb3vq2q81ckdfqn31
title: Authentication
desc: ''
updated: 1716152791187
created: 1695399712830
---

- Authentication - makes sure user is who they claim to be
- Authoriztion - govers what the user has access to

## ChatGPT Overview of Common Authentication Methods:  
- [Passport.js](https://www.passportjs.org/) with local strategy is suitable for smaller applications where auth is handled on own server
- JSON Web Tokens (JWT) - stateless auth mechanism commonly used to secure APIs. 
    - Upon successful auth, the server generates a token which is sent to client
    - the client includes the token in subsequent requests to access protected resources
    - suitable for building scalable and stateless apps
    - Libraries like jsonwebtoken are available in nodejs to implement jwt based auth
- OAuth2 - industry std protocol for auth. Allows users to log in using existing accounts on third-party services. [freecodecamp OAuth Dance](https://www.freecodecamp.org/news/how-to-dance-the-oauth-a-step-by-step-lesson-fd2364d89742/)
    - Libraries like passport-oauth2 can be used to implement in node ([freecodecamp intro to oauth using passport](https://www.freecodecamp.org/news/a-quick-introduction-to-oauth-using-passport-js-65ea5b621a/))
- Session based auth - user sessions are maintained on server side
    - session identifier such as local storage (cookie is not recommended) is sent to client and included in subsequent requests
    - commonly used in traditional web apps
    - Libraries like express-session in node are used in node for session mgt

## Considerations
- Consider security best practices like salting and hashing pwords
- protecting against common vulnerabilities lie cross-site scripting (xss) and cross-site request forgery (CSRF)
- implementing proper error handling
- user input validation
- https to encrypt communication between client and server to ensure data privacy and integrity

## [Passport.js](https://www.passportjs.org/)
Passport is middleware which implements auth on express based web apps
- provides over 500 strategies which are used to authenticate requests
- each strategy has its own npm pkg

## Implementing OAuth with passportjs/express from Raffy's nodejs notes project

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

- will need to get client id, client secret. From google: [Google&#39;s Developers Console](https://console.developers.google.com/)
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

## Mongo
Error: MongoServerError: E11000 duplicate key error collection  
fix: Remove index /unique requirement
 - mongo has indexing tab in collections

## Multiple auth strategies
- https://github.com/passport/express-3.x-http-basic-and-digest-example/blob/master/server.js

```
const express = require('express')
const passport = require('passport')
...
const db = require('./db')

//configure strategy1
passport.use(...)(...)

//configure strategy2
passport.use(...)(...)

//using OR, passport authenticate fails if no strategy returns success
passort.authenticate(['strategy1', 'strategy2']...
    res.json({ username: req.user.username, email: req.user.email[0].value}))
...


```
- [Multi-Provider OAuth 2 Auth](https://rrawat.com/blog/multi-provider-oauth2-nodejs)
- Traversy Storybooks ['tube](https://www.youtube.com/watch?v=SBvmnHTQIPY&list=PLillGF-RfqbZ2ybcoD2OaabW2P7Ws8CWu&index=32&t=3605s) [github](https://github.com/bradtraversy/storybooks)
 - [Implementing with AuthO](https://auth0.com/blog/create-a-simple-and-secure-node-express-app/)