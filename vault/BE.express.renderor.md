---
id: 71b41s6cjf4ggy9re7g1spb
title: renderor
desc: ''
updated: 1694655864226
created: 1694645860831
---
## Express Render and Redirect
`res.redirect('/some-url')` method sends response to client instructing it to redirect to a different URL. The client sends a new request to the URL. The server responds after processing the request. 
- Often used when want to move user to another page aft completing actions like login, form submission, sign-up
- verify and filter before incluing user input in redirect path. Attacks can redirect user to dangerous 'sites  

`res.render('view', {data: data})`method generates html on the server and delivers it to the client dynamically using template engine (ejs, pug, handlebars, etc)
- `res.render(view [, locals] [, callback])`
    - `view` is file path of view file to render
    - `locals`are properties of an object that define local vars for the view
    - `callback` function - returns any possible errors and rendered string
- constructs the page on the server side and sends it, rather than changing the content of the page on the client side
- avoid including user input in the view path. (Attackers may be able to access file system)

### Reference
https://dev.to/mochafreddo/understanding-resredirect-and-resrender-in-expressjs-usage-and-security-measures-2k60