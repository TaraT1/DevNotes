---
id: zrpr93jzt37u951pd9lu4er
title: FE
desc: ''
updated: 1683943122462
created: 1682960943219
---
## Template for making 'site  
- ? sass /scss
- vite probably more useful when start dealing with React  

### Teachers' Tools
- Coder Coder: gulp and browswersync (livesync), scss
    - Jess uses gulp to compile sass (with functions, mixins, nesting styles) to css. Browsers can't read sass. VSCode livesass extension not support new sass rules.
    - instead of using gulp, can set watch on sass. e.g. input.scss `sass --watch input.scss output.css`
    - lots of recos for vite from tweet
- Kevin Powell: uses <mark>vite and sass</mark>
    - w/o sass: 'tube: [Build a responsive with html and css](https://www.youtube.com/watch?v=h3bTwCqX4ns&list=PL4-IK0AVhVjNDRHoXGort7sDWcna8cGPA)  
        - [github fem Manage Landing Page](https://github.com/kevin-powell/fem-manage-landing-page-part-1)
    - github 
        - Starter with vite: https://github.com/kevin-powell/website-starter-template-v2
        - Starter for larger with vite, sass: https://github.com/kevin-powell/demo-starter-template-with-sass
            - fem: frontend mentor
        - Dynamic grid layout tut
            - [tube for grid](https://youtu.be/sKFW3wek21Q) 
            - [code for grid tut](https://github.com/kevin-powell/dynamic-grid-layout)
- web dev simplified: 

### Simple Starter CSS
[kev pow, Stop over-engineering css](youtube.com)
```css
html{
    color-scheme: light dark; /*system determines*/
}

body {
    font-family: system-ui;
    font-size: 1:125;
    line-height: 1.5;
}

main {
    width: min(70ch, 100% - 4 rem); /*70ch: 70 characters wide*/
    margin-inline: auto;
}

img, svg, video {
    max-width: 100%
    display: block;
}
```css






### Resource
c.f. [[FE.css.naming]]  
[[ARIA]]  
c.f. examples in codepen  
[flaviocopes](flaviocopes.com) (javascript?)  
[Sara Soueidan](https://www.sarasoueidan.com/)