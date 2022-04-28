---
id: 0chrl1iq0vv8tx2919bk63a
title: css
desc: ''
updated: 1649993352212
created: 1649553303701
---

CSS - cascading style sheets. Terms are selectors, properties, and values
-selectors designate which element(s) or attribute value (id or class value) are targeted to apply styles
	-ex: p {…}
-properties determine styles applied to element
	ex with syntax 
	p {
		color: …;
		font-size: …;
		width: …;
		height: …;
	}
-values determine behavior of properties
	p {
		color: red;
		font-size: 16px;
	}
	
Selectors
-type selectors target elements by their element type  <div> <p> <span>, etc.
	div {…}
-class selectors target based on class attribute; can use same class attribute across multiple elements (.)
	css: 
	.experimental {..}
	
	html:
	<div class="experimental"> … </div>
	<p class="experimental"> … </p>
-id selectors provide more precision; target one element at a time; can only be used once on per page (#)
	css:
	#special {…}
	
	html:
	<div id="special">…</div>
	
?What is best practice for including css on a webpage
format for separate css file

	html:
	<head>
		<link rel="stylesheet" href="main.css">
	</head>
	
??What do CSS resets respond to?
Eric Meyer’s reset - popular and adapted for html5
Normalize.css - sets common styles for common elements

In Practice…

https://learnlayout.com  web.archive.org
?In CSS, what does box-sizing do?
What are the 3 forms to use? box-sizing, typescript or webscript?, moz
Below standardizes sizing more intuitievly
	* {
		-webkit-box-sizing: border-box;
		-moz-box-sizing: border-box;
		-box-sizing: border-box;
	}
When reading technical material, do it hands-on, make active learning.

CSS - cascade style sheet
When is it acceptable for css to be inline?
	-Email
	-style blocks in head (amazon above fold to gain ms)

Use separate CSS file
	<link rel="stylesheet" href="css/style.css">

CSS Syntax
p {
	color: red;
	font-weight: bold;
}
-rule is the whole
-p selector
-set of declarations (2) in declaration block
-in declaration property and value

rules, selector, properties

Cascade - what comes below can override what comes above 

Color: word, hex (#FF0000), rgb (255,0,0,1), hsl (0, 100%, 50%, 1)

Font-family
google fonts

Format
Why load font before css file?

html
<head>
	<link href ="https://fonts.googleapis.com/…" rel="stylesheet">
</head>

css
p {
	font-family: 'Source Sans Pro', 'Helvetica' sans-serif;
}
-Why multiple fonts? 
	for fall-back 
	
fonts from google: fonts.google.com
-select different weights (e.g. 300, 400, 700)

Reference mdn for styling

Selecting By Relationship
parent child - section p {
direct child - parent > child (direct descendant) - section > p {

sibling 
-direct: p + p

css relationships

id . 1x use in doc
class # multiple elements at same time

Specificity
inline style: 1000 points - high can get got
ids: 100 points
class: 10 points
tag: 1 point

DRY

!important - overrides cascade. Only usecase: Temporary troubleshooting

Selecting by Relationship
-parent>child - direct
-parent child

Selecting by relationship
-p+p - previous sibling + next sibling; selects element that is next sibling

2:38:00 HW: rhino w highest level of specificity

Box model
Horizontal padding border
Vertical padding border

Layout w CSS
Floats
Typically modern: flex box and grid
-floats movement up and in direction
-Size

3:01:00
*{
	box-sizing: border-box;
} /*ignore border sizing*/

header,footer{
	height…;
	clear: both;
