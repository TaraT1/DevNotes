---
id: h2ge4wr81r78k7t2noh5ug9
title: Useful Js Examples 
desc: ''
updated: 1651440417947
created: 1651440384940
---
## Useful Js
  ``` javascript
  //event listener - mouse enter, double click 
  document.querySelector('#check').addEventListener('click', functionToRun)

  document.getElementById('purple').onclick = makePurple
  
  //functions to make color => white
  function makePurple() {
      document.querySelector('body').style.backgroundColor = 'rgba(241,63,247,1)' 
      document.querySelector('body').style.color = 'white'
  }
  //query selector - pulls data out of DOM
  let assignedVar = document.querySelector('#day').value
  
//place text in DOM
document.querySelector('h2').innerText
  
//Enter input
const input = document.querySelector('#myInput');
input.addEventListener('keyup',function(e){
    if (e.keyCode === 13) {
    alert('hi');
  }  
});

