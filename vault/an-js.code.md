---
id: h2ge4wr81r78k7t2noh5ug9
title: Code
desc: ''
updated: 1659762104412
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

//Handle Capital Letters, Place result in DOM, add a check for humpday (Wed)

document.querySelector('#check').addEventListener('click', check)

function check() {

  const day = document.querySelector('#day').value.toLowerCase()

  if(day === "tuesday" || day === "thursday"){
    console.log("YOU HAVE CLASS")
  }else if( day === "saturday" || day === "sunday"){
    console.log("Its The Weekend")
  }else if( day === "wednesday") {
    console.log("Hump Day")
  }else{
    console.log("BORING")
  }
}

//Angry Parent - get data from form, button, place in DOM, html
document.querySelector('#yell').addEventListener('click', run)

function run() {
  const fName = document.querySelector('#firstName').value
  const fMidName = document.querySelector('#firstMiddle').value
  const lMidName = document.querySelector('#lastMiddle').value
  const lName = document.querySelector('#lastName').value

  //Add what you should be doing - conditionals go here
  document.querySelector('#placeToYell').innerText = `${fName} ${fMidName} ${lMidName} ${lName}`

  //Uses concatenation
  // document.querySelector('#placeToYell').innerText = fName + ' ' + fMidName + ' ' + ' ' + lMidName + ' ' + lName
}
	// HTML <h1>YOU DONE MESSED UP</h1>

	// 	<form>
	// 		<label for="firstName"> First Name: </label>
	// 		<input id="firstName" type="text" placeholder="First Name">
	// 		<label for="firstMiddle"> First Middle Name: </label>
	// 		<input id="firstMiddle" type="text" placeholder="First Middle Name">
	// 		<label for="lastMiddle"> Last Middle Name: </label>
	// 		<input id="lastMiddle" type="text" placeholder="Last Middle Name">
	// 		<label for="lastName"> Last Name: </label>
	// 		<input id="lastName" type="text" placeholder="Enter First Name">
	// 	</form>

	// 	<button id="yell" type="button" name="button">YELL</button>

	// 	<h2 id="placeToYell"></h2>
  
  //Hide elements in DOM on click
document.querySelector('#finalRose').addEventListener('click', hide)

function hide(){
	document.querySelector('#claire').style.display = 'none'
	document.querySelector('#sharleen').style.display = 'none'
}

// HTML
// <body>
// 	<header>
// 		<h1 id="finalRose">Final Rose</h1>
// 	</header>
// 	<section>
// 		<img id="claire" src="imgs/claire.jpg">
// 		<img id="nikki" src="imgs/nikki.jpg">
// 		<img id="sharleen" src="imgs/sharleen.jpg">
// 	</section>

// 	<script src="js/main.js"></script>
// </body>

//store dom element in variable for readability and DRY
const andi = document.querySelector('#andi')
const claire = document.querySelector('#claire')
const sharleen = document.querySelector('#sharleen')

document.querySelector('#andiNext').addEventListener('click', andiNext)
document.querySelector('#claireNext').addEventListener('click', claireNext)
document.querySelector('#sharleenNext').addEventListener('click', sharleenNext)

//insert hidden class (in html & css), add toggle
function andiNext(){
	claire.classList.add('hidden')
	sharleen.classList.add('hidden')
	andi.classList.toggle('hidden')
}

function claireNext(){
	sharleen.classList.add('hidden')
	andi.classList.add('hidden')
	claire.classList.toggle('hidden')
}

function sharleenNext(){
	claire.classList.add('hidden')
	andi.classList.add('hidden')
	sharleen.classList.toggle('hidden')
}

// HTML & CSS
// <section>
// 		<h1>The next Bachelorette should have been: </h1>

// 		<h2 id="andiNext">Andi</h2>
// 		<h2 id="claireNext">Claire</h2>
// 		<h2 id="sharleenNext">Sharleen</h2>
// 	</section>


// 	<section>
// 		<img id="claire" class="hidden" src="imgs/claire.jpg">
// 		<img id="andi" class="hidden" src="imgs/andi.jpg">
// 		<img id="sharleen" class="hidden" src="imgs/sharleen.jpg">
// 	</section>

//   .hidden{
// 	display: none;
// }

//3 Bachelor
const contestants = document.querySelectorAll('.contestant')

Array.from(contestants).forEach(element => element.addEventListener('click', checkForRose))

function checkForRose(click){
	if(click.target.classList.contains('.rose')){
		document.querySelector('#nikki').classList.toggle('hidden')
	}else{
		alert("Wrong!");
	}
}
// HTML
// <header>
// 		<h1>Who has the final rose?: </h1>

// 		<h2 class="contestant">Claire</h2>
// 		<h2 class="contestant rose">Nikki</h2>
// 	</header>

// 	<section>
// 		<img id="claire" class="hidden" src="imgs/claire.jpg">
// 		<img id="nikki" class="hidden" src="imgs/nikki.jpg">
// 	</section>

// function expression:
// ```
// const example = function(){
  
// }

//important to know. Check to see if works
function fizzBuzz(num){
    for(let i = 1; i <= num; i++){
        if (i % 3 === 0 && i % 5 === 0){
            console.log('FizzBuzz')
        }else if (i % 3 === 0){
            console.log('Fizz')
        }else if (i % 5 === 0){
            console.log('Buzz')
        }else{
            console.log(i)
        }
    }
}
fizzBuzz(15)

## Arrays
//code wars
function removeEveryOther(arr){
  return arr.filter(function(elem, index) {
    return index % 2 === 0;
  });
}

function removeEveryOther(arr){
  var newArr=[];
for (var i = 0; i < arr.length; i+=2){
  newArr.push(arr[i]);
  }
return newArr;
}

const removeEveryOther = arr => arr.filter((_, i) => !(i % 2));

//string fund codewars
function areYouPlayingBanjo(name) {
  return name + (name[0].toLowerCase() == 'r' ? ' plays' : ' does not play') + " banjo";
}
//Reverse string
function solution(str){
  return str.split('').reverse().join('');  
}
//reverse string w arrow function
const solution = str => str.split('').reverse().join('');

//Remove first & last
function removeChar(str) {
  return str.slice(1, -1);
}

//pattern for fetching from APIs
fetch("https://dog.ceo/api/breeds/image/random")
  .then(res => res.json())//parse response as json
  .then(data => {
    console.log(data)
  } )
  .catch(err => {
    console.log(`error ${err}`)
  });

//remove whitespace
function noSpace(x){
  return x.split(' ').join('')
  }

//Initialize full name, separate w .
function abbrevName(name){

    // code away
  let arrName = name.split(' ')
  return(arrName[0][0] + '.' + arrName[1][0]).toUpperCase()
}

//Example fetch using DnD5eAPI - place subclasses in ul (class 28)
document.querySelector('button').addEventListener('click', getFetch)

function getFetch(){
    const choice = document.querySelector('input').value
    const url = `https://www.dnd5eapi.co/api/spells/${choice}`

    fetch(url)
        .then(res => res.json())
        .then(data => {
            console.log(data.subclasses)
            data.subclasses.forEach(obj => {//loop thru arr 
                console.log(obj.name)//info from api

                //create li
                const li = document.createElement('li')
                //add txt to li
                li.textContent = obj.name
                //append li to ul
                document.querySelector('ul').appendChild(li)//how remove txt from dom (remove child)
            })
        })

        .catch(err => {
            console.log(`error ${err}`)
        });
}

//server code
const express = require('express')
const app = express()
const cors = require('cors')
const PORT = 8000

app.use(cors())

const rappers = {
    '21 savage':{
        'age': 29,
        'birthName':'Shéyaa Bin Abraham-Joseph',
        'birthLocation': 'London, England' 
    },
    'chance the rapper':{
        'age': 29,
        'birthName':'Chancelor Bennett',
        'birthLocation': 'Chicago, Illinois' 
    },
    'dylan':{
        'age': 29,
        'birthName':'Dylan',
        'birthLocation': 'Dylan' 
    }
}

app.get('/', (request, response)=>{
    response.sendFile(__dirname + '/index.html')
})

app.get('/api/:rapperName', (request,response)=>{
    const rappersName = request.params.rapperName.toLowerCase()
    if(rappers[rappersName]){
        response.json(rappers[rappersName])
    }else{
        response.json(rappers['dylan'])
    }
})

app.listen(process.env.PORT || PORT, ()=>{
    console.log(`The server is running on port ${PORT}! You better go catch it!`)
})
  
```

