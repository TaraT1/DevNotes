---
id: u1ntlp6f1lvv09r11nof8d0
title: Loops
desc: ''
updated: 1654060075935
created: 1654059940402
---

# Loops
- repeat an action x number of times
- Js loop types include for, while, do
- each type offers a different way to determine start and end points of a loop
- reference https://github.com/thejsway/thejsway/blob/master/manuscript/chapter04.md
- loops are used to repeat a series of statements
- iteration - each repetition the code runs
- body - code block associated with a loop

## While loop
- repeats code while certain condition is true
- condition of while loop must eventually become false to avoid risk of infinite loop
- use when number of times code should run is not known (like when depending on user interaction)
```
//While loop
while (condition) {
  //code to run while condition is true
  //increment counter
}

let count = 0

while(count < 5){
  console.log(count)
  count++
}

```

## For loop
- updating counter of a for loop inside body is a bad idea - loop will iterate twice
- for loop is best choice when  know in advance # times loop is to run
- loop counter - var used during initialization, condition, and final expression; often named i
```
//for loop
for (initialization; condition; final expression) {
  //code to run while condition is true
}

for (let i = 1; i < 5; i++ ){
  console.log(i)
}
```
- initialization - happens once, sets initial value of loop counter
- condition - evaluated before loop runs; if true, code runs; if false, code doesn't run
- final expression - evaluated after loop runs; often updates counter
 Loops
