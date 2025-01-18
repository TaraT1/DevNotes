---
id: pm7etsohbzt44q09gbni7jm
title: Continue
desc: ''
updated: 1738955392190
created: 1738954936776
---
`continue` statement terminates execution of the statement in the current iteration of the current or labeled loop. It continues execution of the loop with the next iteration
``` javascript
let text = ''
for(let i = 0; i < 10; i++) {
    if(i===3){
        continue
    }
    text += i
}

console.log(text) //'012456789'
```
Ref: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue
Contrast with `break` 