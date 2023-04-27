---
id: qn2lj7c23ufomwkjdi8in2q
title: preprocessor
desc: ''
updated: 1682706408176
created: 1675301098311
---
Explanation:
CSS preprocessors are programs that let one generate css from preprocessor's own uniue syntax
- most add features that don't exist in pure css
    - mixin, nesting selector, inheritance selector, etc.
    
Use:
install css compiler on web server or use to compile on dev env and upload compiled css file to web server

Example:
Sass, LESS, Stylus, PostCSS

source: https://developer.mozilla.org/en-US/docs/Glossary/CSS_preprocessor

source: 'tube Coder Coder: [Sass and BEM for beginners](https://www.youtube.com/watch?v=jfMHA8SqUL4&t=1134s)
- CSS processor - easier for devs to work with, has to be converted to css for browser (prepocessor)
- sass  Syntatically Awesome Style Sheets
    - no {} or ;
    - relies on indentation and new lines to differentiate style rules
    - file extension .sass
- scss
    - uses {} and ; 
    - file extnsion .scss

css compilers include VSCode and Gulp
- VSCode: search extensions for live sass compiler. Recommends Glenn Marks.
    command pallete  
    open settings, open settings json  
    add new lines at end b4}  
    "livesassCompile.settings.formats"...  
    change savePath from null to "/dist"  
    format: "expanded" or "compressed"

- sass partials