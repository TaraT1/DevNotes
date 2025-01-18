---
id: 3c1pv6o689ndpx9yqm49iru
title: Break
desc: ''
updated: 1738955958562
created: 1738955754001
---
`break` statement terminates the current loop or `switch` statement and transfers program control to the statement following the terminated statement.

``` javascript
let i = 0

while (i < 6) {
    if(i===3) {
        break
    }
    i += 1
}

console.log(i)//3