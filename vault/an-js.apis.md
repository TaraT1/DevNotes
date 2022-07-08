---
id: whjhdck8g1w25x3jux00dfi
title: Apis
desc: ''
updated: 1657245858410
created: 1655929860520
---
- simple interface for complex action
- restaurant menu  - interfaces with kitchen, wait staff, etc.
- Allows one thing to communicate with another w/o having to know how things are implemented
- url is interface
- fetch >>> API returns JSON object we can use within apps

``` javascript
fetch("url")//pattern for fetching from 
  .then(res => res.json())//parse resposne as json
  .then(data => {
    console.log(data)
  } )
  .catch(err => {
    console.log(`error ${err}`)
  });
```
	
Soln if data input has more than 1 word
```javascript
document.querySelector('button').addEventListener('click', getDrank)

function getDrank(){
  let drink = document.querySelector('input').value
  
  fetch(`https://www.thecocktaildb.com/api/json/v1/1/search.php?s=${drink}`)
  
  .then(res => res.json())
  .then(data =>{
    let i = 0
    console.log(data.drinks)  
    //cocktail name from api
    document.querySelector('h2').innerText = data.drinks[i].strDrink
    //cocktail photo from api
    document.querySelector('img').src = data.drinks[i].strDrinkThumb
    //cocktail instructions from api
    document.querySelector('h3').innerText = data.drinks[i].strInstructions

    i++

    if(!data.drinks[0]) i = 0

  })
  .catch(err => {
    console.log(`error ${err}`)
  });
}  








```
