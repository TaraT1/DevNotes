---
id: omclh7oa9llj4rrtfwc2rrc
title: String
desc: ''
updated: 1665034009837
created: 1662597980670
---
From [Essential String Methods](https://levelup.gitconnected.com/essential-javascript-string-methods-f1841dad1961)

[MDN string documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

.charAt() returns str character at given index
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
++
.concat() concatenates string args to calling string, returns new string
```js
str.concat()

```

.includes() determines if substring is contained within larger string. Returns true or false
```js

```

str.indexOf()(substr, pos) 
- looks for substr in str starting from optional pos (case sensitive)
- returns pos where match found or -1 if nothing found
```js
let str = 'Widget with id';

alert( str.index(Of('Widget') ); //0 - found at beginning
alert( str.index(Of('widget') ); //-1 - not found, case sensitive

```


```js
indexOf(searchString)
indexOf(searhString, position)
str.indexOf()
```

.length returns number of characters
```js

```

.match() returns array of matching strings when matcing against regex
```js

```



.repeat() repeats string specified number of times
```js

```

.replace() replaces strings with new values
- Input is string (replaces first occurence) or regex  (globally replace with g option). 
```js

```

.search
```js

```

.slice(begIndex[, endIndex]) return section of a string
- endIndex default is end of beginIndex, non-inclusive
- negative beginIndex slice backwards from end
```js

```


.split() takes separator to split apart string, returns array of strings
```js

```

substr toLowerCase
```js

```


.toUpperCase() capitalizes entire string

.toLowerCase() lower cases entire string

.trim() - removes white space from beginning & end (works well for user input)










