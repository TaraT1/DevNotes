---
id: 125o2e5ety2b1pd18nxewjc
title: Storage
desc: Leon class 27
updated: 1656213478304
created: 1656190930074
---
- Local storage persists across browser sessions unless user clears memory
- Session storage persists just for that session. Gone after browser is closed.

## Local Storage Methods
``` javascript
//Put item into local storage
localStorage.setItem('key1', 'value1')

//Get item out of local storage
localStorage.getItem('key2', 'value2')

//Remove item in Local Storage
localStorage.removeItem('key', 'value2')

//Clear local storage
localStorage.clear()

//create btn that adds 1 to botScore stored in localStorage
//Determines whether or not botScore has history. If no history, 0. Otherwise, history persists with refresh
if(!var localStorage.getItem('botScore')){
    localStorage.setItem('botScore', 0)
}

document.querySelector('button').addEventListener('click', addAnothaOne)

function addAnothaOne(){
    let botScoreVal = Number(localStorage.getItem('botScore'))//accounts for stringiness of botScore
    botScoreVal += 1
    localStorage.setItem('botScore', botScoreVal)
}





```





