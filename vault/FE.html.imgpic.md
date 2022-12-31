---
id: a6vva61wdq6ui1w754cpm6j
title: imgpic
desc: ''
updated: 1673235142777
created: 1673233087372
---
## When to Use img 
<img> is used to add single inner image as part of specific content
- Semantically meant to be used inside of container like <p> where displayed image is needed so text is better understood

## When to Use background image
The CSS background-image property is used for stylistic or decorative content.
- icons, background patterns, and other decorative images
- c.f. FE.css.backgroundimage

## When to use figure
<figure> connects text to one or more pictures.
- used with <figcaption>
    - gives additional informatin about images
- meant to be used outside of containers like <p>

```html
<figure>
  <img src="pic1.jpg" alt="Pic1" >
  <img src="pic2.jpg" alt="Pic2" >
  <figcaption>Pictures made by X </figcaption>
</figure>
```

## When to Use picture
<picture> is used for responsiveness and media queries
- meant to be used as standalone object outside of containers like <p>

```html
<picture>
  <source media="(min-width:650px)" srcset="animal_big.jpg">
  <source media="(min-width:465px)" srcset="animal_small.jpg">
  <img src="animal_default.jpg" alt="Animal">
</picture>
```


[refs](https://www.js-craft.io/blog/when-to-use-the-img-figure-or-picture-html-tags/)