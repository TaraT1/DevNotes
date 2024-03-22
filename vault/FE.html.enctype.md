---
id: vlpbsao7vdmt5e1nurxizon
title: enctype
desc: ''
updated: 1711129689942
created: 1710181770998
---
Summary: Using form for updates routes (PUT, PATCH, POST), enctype matters.

`enctype` is the html form element that is used to submit the form to the server.

`application/x-www-form-urlencoded` is the initial default type.

What I used `multipart/form-data` allows file input elements to upload data. In my long suffering experience, it blocks changes to form fields.

`text/plain` is human-readable but not reliably interpreted by computer.

Referenced from the bible aka MDN https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/enctype