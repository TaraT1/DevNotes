---
id: kwxhpdw3vulbdrpwznhrytu
title: Emailonly
desc: ''
updated: 1713468773556
created: 1713464038925
---
## Email Only /Magic Link Authentication
[Reference WDS](https://www.youtube.com/watch?v=b6qHfPdv4Y8&t=29s)  

## Passwordless Auth Step-By-Step
1. User registers with email
2. Store email in db
3. To login user enters email in login form
4. Server creates unique token for the user
5. Send email with link containing unique token
6. User clicks on link
7. Server verifies token. (Can be stored as cookie or session)
8. User is logged in 

``` javascript
//server.js usihg jwt
const dotenv = require("dotenv)
dotenv.config()

const express = require("express")
const jwt = require("jsonwebtoken")
const { sendMagicLinkEmail } = require("./mailer")

const app = express()
app.use(express.urlencoded({ extended: true }))

const USERS = [//test db
    {
        id: 1,
        email: "checkBabyCheck@123.com",
        name: "Check"
    }
]
//routes
app.post("/login", async (req, res) => {
    const user = Users.find(u => u.email === req.body.email)
    
    if (user != null) {
        try {
            const token = jwt.sign({ userId: user.id}, process.env.JWT_SECRET, {
                expiresIn: "1h",
            })
            await sendMagicLinkEmail({ email: user.email, token }) //email service (has free tier)
        }  catch(error) {
            return res.send("Error logging in. Please try again.")
        }
    }
    res.send("Check your email to finish logging in")
})

app.get("/verify", (req, res) => {
    const token = req.query.token
    if (token == null) return res.sendStatus(401)
    
    try{
        const decodedToken = jwt.verify(token, process.env.JWT_SECRET)
        const user = USERS.find(u => u.id === decodedToken.userId)
        res.send(`Authed as ${user.name}`)
    } catch (error) {
        res.sendStatus(401)
    }
})

app.listen(2121)

//Generate crypto key using js
crypto.subtle
  .generateKey(
    {
        name: "HMAC",
        hash: { name: "SHA-256" },
    },
    true,
    ["sign", "verify"] 
  )
  .then(key => {
    crypto.subtle.exportKey("jwk", key).then(exported => {
        console.log(exported.k)
    })
  })

//mailer.js
const SendGridMailer= require("@sendgrid/mail")
sendGridMailer.setApiKey(process.env.SEND_GRID_API_KEY)

function sendMagicLinkEmail({ email, token }) {
    return sendGridMailer.send({
        to: email,
        from: process.env.FROM_EMAIL,
        subject: "Finish Logging In",
        html: `<a href="http://localhost:2121/verify?token=${token}">Log In</a>`,
    })
}
module.exports = {
    sendMagicLinkEmail,
}

```
Views
``` html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=devive-width, initial-scale=1.0" />
    <title>MagicLink Baby</title> 
  </head>
  <body>
    <form method="POST" action="http://localhost:2121/login">
        <label for="email">Email</label>
        <br />
        <input type="email" name="email" id="email" />
        <br />
        <br />
        <button type="submit">Log In</button>
    </form>
  </body>
</html>

```
- Can store authenticated user in session using cookies
- cookie/session auth tut