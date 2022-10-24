---
id: omclh7oa9llj4rrtfwc2rrc
title: String
desc: ''
updated: 1666483090238
created: 1662597980670
---
From [Essential String Methods](https://levelup.gitconnected.com/essential-javascript-string-methods-f1841dad1961)

[MDN string documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

.charAt() 
str.charAt(index) returns str character at given index

```js
const sentence = 'Where is the focking letter?';
const index = 13;

console.log(`char @ index ${index} is ${sentence.charAt(index)}`);
//output: 'char @ index 13 is f'
```

.charCodeAt() returns unicode of char at specified index n a string
```js
str.charCodeAt(pos) //returns UTF-16 code
```

.concat() concatenates string args to the calling string, returns new string
```js
str.concat()

let str = Complete this

str.concat('sentence') //Complete this sentence
```

.includes() determines if substring is contained within larger string. Returns true or false
```js
str.includes(substr, pos)//optional pos is where to start searching
str.startsWith() //returns true or false
str.endsWith() //exact ending true. If not false
//optional 
```

.indexOf()
str.indexOf()(substr, pos) 
- looks for substr in str starting from optional pos (case sensitive)
- returns pos where match found or -1 if nothing found
```js
let str = 'Widget with id';

alert( str.index(Of('Widget') ); //0 - found at beginning
alert( str.index(Of('widget') ); //-1 - not found, case sensitive
```

.match() returns array of matching strings when matcing against regular expression like /[A-Z]/g
```js
const paragraph = 'The quick brown fox jumps over the lazy dog. It barked.';
const regex = /[A-Z]/g;
const found = paragraph.match(regex);

console.log(found);
// expected output: Array ["T", "I"]
```

.repeat() repeats string specified number of times
```js
let str = "Bon Jour!";

str.repeat(3) //Bon Jour!Bon Jour!Bon Jour!
```

.replace() replaces strings with new values
.replace(replaceVal, replaceWithVal)
- Input is string (replaces first occurence) or regex  (globally replace with g option).
- case sensitive 
```js
str.replace('iO', '<3') //<3
```

.search - search for specified value or reg exp, returns starting index of match if found or -1 if not found
```js
let str = 'match made in heaven'
str.search('heaven') //14
str.search('hell')// -1
```

.slice(begIndex[, endIndex]) return section of a string
- endIndex default is end of beginIndex, non-inclusive
- negative beginIndex slice backwards from end
```js
let str = 'match made in heaven'
str.slice(14, -1)//heaven
```

.split() takes separator to split apart string, returns array of sub-strings
.split(separator, limit)
```js
str.split(' ')
```

.substring() returns part of string between start and non-inclusive end indexes or to end of string
```js
let str = fuck;

str.substring(1,3) //'uc'
```

.toLowerCase() - returns new lowercased string (Js strings are immutable)
```js
str.toLowerCase()
```

.toUpperCase() returns new capitalized string (Js strings are immutable)


.trim() - retuns new string removing white space from beginning & end (works well for user input)

.trimStart() - trims whitespace from beginning of string

.trimEnd() - trims whitespace from end of string
