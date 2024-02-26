---
id: sbplfukuz9vf98jun8wlz9f
title: Methods
desc: ''
updated: 1709148651324
created: 1708962175624
---
## String

- .substring() 
    ```javascript
    substring(indexStart)
    substring(indexStart, indexEnd (optional, idx excluded from returned substring))
    ```
    - if indexStart > indexEnd: returns 
 - .slice()
    ```javascript
    slice(indexStart)
    slice(indexStart, indexEnd (optional, idx to exclude from returned substring))
    ```
    - if indexStart > indexEnd: returns empty string

- .substr() - *DEPRECATED* returns portion of text received;
  syntax .substr(starting index, length (number of chars afterward optional))
```javascript
function reverseString(text) {
    if (text === ''){
        return ''
    } else {
        return reverseString(text.substr(1)) + text[0]
    }
}
```
 ### regex
- `.match()` - retrieves result of matching a string against a regular expression; returns array of matches  
- can convert non regexp to regexp with `new RegExp(regexp)`  
- gi flags - global and ignore case

## Array Methods
- `.reduce()` = executes reducer callback function of each element of array. Final result of running reducer across all elements is a single val
- syntax: .reduce(accumulator, currentValue, index)
- reference [MDN: reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)