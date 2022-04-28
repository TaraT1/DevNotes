---
id: 3lzxfs6wq3tp4g7onpy2jzw
title: html
desc: ''
updated: 1649992935327
created: 1649553281920
---

What are elements?
	designators for structure and content of a web page
	ex: headings, img, p, span, div
What are tags?
	<> which surround elements and attributes
What are attributes?
	provide more detail about elements
	ex: id (#) and class (.)
	format: <element="attribute">
	
# HTML Document Structure:
```html
<!DOCTYPE html> - signifies html5 version
<html lang="en"> - beginning of document
	<head> - top o' doc including metadata; not displayed on page;  links to external files, etc. 
		<meta charset="utf-8">
		<title>Something to Say</title> - doc title is displayed on title bar in browser
	</head>
	<body> - visible content within web page
		<h1>Say it Loud & Proud</h1>
	</body>
</html>
```
?Why are elements nested?

The W3C has built both HTML and CSS validators that will scan code for mistakes. 

???html <pre />  - preserves whitespace, old - non-responsive, not recommended 

html:
?root element
?children of html element 
head and body are where everything happens

Navigation
	<nav>
		<ul>
			<li>…</li>
			<li><a href="#">#</a>
		</ul>
	
	</nav>

Forms - used for user inputs
<form action="#" method="post">
	text, pw, phone, email, button (cf MDN)
	<input id="zebra" type="text">
	<label for="zebra">First Name:</label>
</form>

mobile has changed the 'net

progressive enhancement - 22M rural have no broadband access. Sites use light versions to accommodate limited broadband access
