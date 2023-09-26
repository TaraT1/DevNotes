---
id: 4zw3g50s4oglnuo64p44d27
title: DB
desc: ''
updated: 1724204501783
created: 1651166097624
---
# Databases

## Express Request Object

[Express dox](https://expressjs.com/en/api.html#req)
- `req.body` - used in POST/PUT requests
    - used to send sensitve data (form data)

- `req.params`- gets properties attached to URL i.e., named route params

- `req.query` - used for search, sort, filter, pagination
    - key = value
    

## Express Response Object

[Express Response Dox](https://expressjs.com/en/api.html#res)
- `res.render(view[, locals] [, callback])` - renders a view and sends the rendered html string to the client
    - locals is an object whose properties define local vars for the view
- `res.redirect([status,] path)` - Redirects to the URL derived from the specified pat
- `res.req` - holds reference to the request object that relates to the response object
- `res.send([body])` - sends http response
- `res.cookie(name, value [, options])` - sets cookie name to value. Value param may be string or object converted to json. Options param object has properties ranging from expires, maxAge, priority, domain, encode, etc.

# Router
- router object is an instance of middleware and routes

## Router Methods
- `router.METHOD(path, [callback, ...] callback)
    - router.get, router.post, etc.
- `router.param(name, callback)` - parameters of the callback function; req, res, next, value of the name parameter, name of the parameter