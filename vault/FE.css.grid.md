---
id: 54qjqs539iba8657mroqw8s
title: grid
desc: ''
updated: 1683164469734
created: 1653948910962
---
- notes from Traversy Meida CSS Grid Crash Course 2022, 'tube  
Flexbox was first. 

- CSS Grid for overall layout 
- flexbox for inner layout

- Grid 2 dimensional layouts, while Flex is one dimensional - either row or column

## Grid Containers & Grid Items
- grid container holds grid items, which are direct children of grid containers

grid-template-columns: 1fr //fraction, %  
grid-template-rows:  
gap (row, column)  
vh - viewport height  

```css
body {
    font-family:'
    font-size: ;
    <!-- height: 100vh; -->

    display: grid;
    grid-template-areas:
        'header header header'
        'nav content sidebar'
        'nav footer footer'
    grid-template-columns: 1fr 4fr 1fr;
    grid-template-rows: 80px 1fr 70px;
}
```
Sandbox from frontendmentor.io
    
    

## Flex & Grid Examples
c.f. D:\Programming\experiments\responsive card  
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout  
- [tube for grid](https://youtu.be/sKFW3wek21Q) 
- [code for grid tut](https://github.com/kevin-powell/dynamic-grid-layout)
- KP Learn CSS Grid the easy way ('tube)