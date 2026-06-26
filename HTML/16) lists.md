#### Lists
HTML lists allow us to group a set of related items in lists.
##### Unordered lists
An unordered list starts with the `<ul>` tag. Each list item starts with the `<li>` tag.
The list items will be marked with bullets (small black circles) by default:
```html
<ul>
	<li>coffee</li>
	<li>Tea</li>  
	<li>Milk</li>
</ul>
```

*Note:* You can also choose list item marker. The CSS `list-style-type` property is used to define the style of the list item marker. It can have one of the following values:
```css
<ul style="list-style-type:disc;">  
  <li>Coffee</li>  
  <li>Tea</li>  
  <li>Milk</li>  
</ul>
```
**Values you can use:**
+ disc
+ circle
+ square
+ none
##### Ordered lists
An ordered list starts with the `<ol>` tag. Each list item starts with the `<li>` tag. The list items will be marked with numbers:
```html
<ol>  
	<li>Coffee</li>  
	<li>Tea</li>  
	<li>Milk</li>  
</ol>
```

*Note:* You can also change the type of the list marker.
```html
<ol type="1">  
  <li>Coffee</li>  
  <li>Tea</li>  
  <li>Milk</li>  
</ol>
```

**Values you can choose:**
+ "1"
+ "A"
+ "a"
+ "I"
+ "i"

##### Control list counting
By default, an ordered list will start counting from 1. If you want to start counting from a specified number, you can use the `start` attribute:
```html
<ol start="50">  
  <li>Coffee</li>  
  <li>Tea</li>  
  <li>Milk</li>  
</ol>
```
##### Description lists
A description list is a list of terms, with a description of each term.
The `<dl>` tag defines the description list, the `<dt>` tag defines the term (name), and the `<dd>` tag describes each term:
```html
<dl>  
  <dt>Coffee</dt>  
  <dd>- black hot drink</dd>  
  <dt>Milk</dt>  
  <dd>- white cold drink</dd>  
</dl>
```

##### Horizontal list with CSS
```html
<!DOCTYPE html>  
<html>  
<head>  
<style>  
ul {  list-style-type: none;  
  margin: 0;  
  padding: 0;  
  overflow: hidden;  
  background-color: #333333;}  
  
li {  float: left;}  
  
li a {  display: block;  
  color: white;  
  text-align: center;  
  padding: 16px;  
  text-decoration: none;}  
  
li a:hover {  background-color: #111111;}  
</style>  
</head>  
<body>  
  
<ul>  
  <li><a href="#home">Home</a></li>  
  <li><a href="#news">News</a></li>  
  <li><a href="#contact">Contact</a></li>  
  <li><a href="#about">About</a></li>  
</ul>  
  
</body>  
</html>
```