---
id: jle8vl3uvaaymr2ttgp58lj
title: naming-systems
desc: ''
updated: 1683165125663
created: 1683124941416
---
# CSS Naming Systems
## Overview
https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Organizing
- Object Oriented CSS (OOCSS) - separate css into reusable objects which can be used anywhere. Created by Nicole Sullivan. Good way to approach things in general
```css
/*base class extends patterns to accommodate for differences*/
.comment {
  display: grid;
  grid-template-columns: 1fr 3fr;
}

.comment img {
  border: 1px solid grey;
}

.comment .content {
  font-size: 0.8rem;
}

.list-item {
  display: grid;
  grid-template-columns: 1fr 3fr;
  border-bottom: 1px solid grey;
}

.list-item .content {
  font-size: 0.8rem;
}
```
```html
html uses base and extension class
<div class="media comment">
  <img src="" alt="" />
  <div class="content"></div>
</div>
<ul>
  <li class="media list-item">
    <img src="" alt="" />
    <div class="content"></div>
  </li>
</ul>



```
- Block Element Modifier (BEM) - characterized by extensive use of dashes and underscores in the CSS classes. https://getbem.com/naming/
    - block is a stand-alone entity (btn, menu, logo)
    - element is an item tied to the block it is in
    - modifier is a flag on a block or element that changes the styling or behavior
- Other common systems (can seem overly complex esp on smaller projects)
    - 
     [Scalable and Modular Architecture for CSS (SMACSS)](http://smacss.com/)
     - [ITCSS](https://itcss.io/)
     - (Atomic CSS -  ACSS)[https://acss.io/] (orig created by yahoo)

     ### Build Systems for CSS
     Most popular preprocessor is [Sass][https://sass-lang.com/]
     - preprocessors - run over raw files and turns them into stylesheet
     - postprocessors - takes finished stylesheet and does something to it, like optimizing so it runs faster
     
     Tools require dev env is able to run scripts. May be handled by code editors. Also can install CL tools  

     - defining vars. Allows defining all colors and fonts in project as settings then use var around the project. (Change once and done)
     ```css
        $base-color: #c6538c;

        .alert {
        border: 1px solid $base-color;
        }

        /*compiles as:*/
        .alert {
            border: 1px solid #c6538c
        }
    ```
### Compiling component stylesheets
- when using sass can have lots of small stylesheets, like having separate stylesheet for each component
-  sass partials can be compiled together and linked. Can be loaded into other stylesheets using @use

### Post processing for optimization
optimizes css by stripping out the unnecessary for production
    



     