---
id: omclh7oa9llj4rrtfwc2rrc
title: String
desc: ''
updated: 1662599173193
created: 1662597980670
---
From [Essential String Methods](https://levelup.gitconnected.com/essential-javascript-string-methods-f1841dad1961)

[MDN string documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

.length returns number of characters

.trim() - removes white space from beginning & end (works well for user input)

.includes() determines if substring is contained within larger string. Returns true or false

.indexOf() returns index of substring within a string. If substring not contained: -1

.toUpperCase() capitalizes entire string

.toLowerCase() lower cases entire string

.replace() replaces strings with new values
- Input is string (replaces first occurence) or regex  (globally replace with g option). 

.slice(begIndex[, endIndex]) return section of a string
- endIndex default is end of beginIndex, non-inclusive
- negative beginIndex slice backwards from end

.split() takes separator to split apart string, returns array of strings

.repeat() repeats string specified number of times

.match() returns array of matching strings when matcing against regex

.charAt() returns str character at given index

.charCodeAt() returns unicode of char at specified index n a string


