---
id: whjhdck8g1w25x3jux00dfi
title: Apis
desc: ''
updated: 1656007279794
created: 1655929860520
---
- simple interface for complex action
- restaurant menu  - interfaces with kitchen, wait staff, etc.
- Allows one thing to communicate with another w/o having to know how things are implemented
- url is interface
- fetch >>> API returns JSON object we can use within apps

``` javascript
fetch("https://dog.ceo/api/breeds/image/random")//pattern for fetching from 
  .then(res => res.json())//parse resposne as json
  .then(data => {
    console.log(data)
  } )
  .catch(err => {
    console.log(`error ${err}`)
  });
```
	

