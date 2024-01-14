---
id: 4ujc4lbp87d62nhk3vtmj8w
title: ejs
desc: ''
updated: 1738442058385
created: 1738438669431
---
Reference: [SO]{https://stackoverflow.com/questions/17014384/how-to-render-multiple-ejs-files-in-nested-form-in-node-js-and-express}

## Nesting Views
- `include` (`<% include header %>` &c)
- ejs-locals allows inserting any view by specifying path. ejs-locals allows passing extra vals to view 
    - https://github.com/RandomEtc/ejs-locals - not maintained
```js
res.render('index', {
                    title: 'title',
                    content: 'index',
                    data:rows
})
```
'index' contains
```html
<html>
    <head>
        <title><%= title %> </title>
    </head>
    <body>
        <p>
            <%- partial('index', {}) %>
        </p>
    </body>
</html>
```



## Access ejs data in form while using express 
Reference: [SO](https://stackoverflow.com/questions/36206919/how-do-i-access-ejs-data-in-a-form-while-using-express)
``` html
<form action="/clubreq" method="post">
    <% for (var i in clubreq){%>
        Club Name: <input type="text" name="clubname[]" value="<%= clubreq[i].clubname %>" /><br><br>
        Club Type: <input type="text" name="clubtype[]" value="<%= clubreq[i].type %>" /><br><br>
        <input type="submit" value="accept"/><br><br><hr>
    <%} %>
</form>
```
```javscript
app.post('/clubreq', function(req, res, next){
   // req.body object has your form values
   console.log(req.body.clubname);
   console.log(req.body.clubtype);
});
```