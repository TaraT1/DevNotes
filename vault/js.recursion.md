---
id: udpfqzo0cdiambfnkp63215
title: Recursion
desc: ''
updated: 1708964016852
created: 1684160101514
---
- programming technique in which the intention is to reduce the problem into smaller instances of the same problem until it is completely solved. e.g. function calls itself repeatedly
- .substr() - *DEPRECATED* returns portion of text received;
  syntax .substr(starting index, length (number of chars afterward optional)
- .substring() 
    ```javascript
    substring(indexStart)
    substring(indexStart, indexEnd (optional, excluded from returned substring))

    ```
```javascript
function reverseString(text) {
    if (text === ''){
        return ''
    } else {
        return reverseString(text.substr(1)) + text[0]
    }
}
```

- terminal case - case that ends recursion. (Check to see if empty string). Otherwise could be endless loop.
- ref scotch.io Ultimate Guide to js Algos
