##### element
CSS element selector selects and style all elements with the specified element name.
*Example:*
```css
h1{
	border:2px solid green;
	background-color:beige;
}
p{
	background-color:yellow;
}
```

##### class
The CSS `.class` selector selects elements with a specific class attribute value.
To select all kinds of elements with a specific class, write a . character, followed by the class attribute value. 
```css
.myclass{
	background-color:yellow;
}
```
*!Note:* To select only one type of elements with a specific class, write the element name, then a period (.) character, followed by the class attribute value (look at Example 1 below).
```css
p.myclass{
	background-color:yellow;
}
```
##### id
The `id` selector uses the id attribute of an HTML element to select a specific element. The id of an element is unique within a page, so the id selector is used to select one unique element!
To select an element with a specific id, write a hash (#) character, followed by the id of the element.
```css
#para1{
	text-align:center;
	color:red;
}
```
*!Note:* id name cannot start with a number.

##### attribute
CSS attribute selectors are used to select and style HTML elements with a specific attribute value or both.

**CSS [attribute] selector**
The `[attribute]` selector is used to select elements with a specific attribute.
```css
a[target]{
	background-color:yellow;
}
```

**CSS [attribute="value"] selector**
The `[attribute="value"]` selector is used to select elements with a specific attribute with an exact value.
```css
a[target="_blank"]{
	background-color:yellow;
}
```

##### pseudo-class
A CSS pseudo-class is a keyword that can be added to a selector, to define a style for a special state of an element.
Common uses:
- Style an element when a user moves the mouse over it
- Style visited and unvisited links differently
- Style an element when it gets focus
- Style valid/invalid/required/optional form elements
- Style an element that is the first child of its parent
**Syntax:**
```css
selector:pseudo-class-name{
	CSS properties;
}
```

**Pseudo-classes used on links:**
+ `:link` styles unvisited links
+ `:visited` styles visited links
+ `:hover` styles a link on mouse over
+ `:active` styles an activated link
```css
/* unvisited link */  
a:link{
	color: #FF0000;
}  
  
/* visited link */  
a:visited{
	color:#00FF00;
}  
  
/* mouse over link */  
a:hover{
	color: #FF00FF;
}  
  
/* selected link */  
a:active{
	color:#0000FF;
}
```
*!Note:* hover must come after link and visited. active must come after hover. also you can use hover for div elements.

**:focus on input:**
```css
input:focus{
	background-color:yellow;
}
```

**disabled inputs:**
```html
<input type="text">
<br>
<input type="text" disabled>
```
```css
input:disabled{
	background-color: red;
	border:2px solid yellow;
}
```
This will apply changes to the inputs that are disabled.
*Note:* You can also mix this method with not:
```css
input:not(:disabled){
	background-color: red;
	border:2px solid yellow;
}
```

**nth-child(value)**
Applies changes to the nth element in a container. You can pass values like numbers, and also keywords like **even and odd** in the () so it will apply changes to the even or odd positioned elements.
```css
.container div:nth-child(2){
	color:white;
}

.container div:nth-child(even){
	font-weight:bold;
}
```

**first and last child**
```css
.container div:first-child{
	color:white;
}

.container div:last-child{
	color:purple;
}
```

**not**
It applies changes to all element except the one in not pseudo selector.
```css
.container *:not(p){
	color:purple;
}
```
##### pseudo element
[see here for all](https://www.w3schools.com/cssref/css_ref_pseudo_elements.php#:~:text=A%20CSS%20pseudo%2Delement%20is,before%20or%20after%20an%20element)
Difference between pseudo classes and pseudo elements are in :. first one has one and second one has two.

**::selection**
```css
.container p::selection{
	background-color:red;
}
```

**::first-letter and first-line**
```css
.container p::first-letter{
	font-size:34px;
	color:purple;
}
p::first-line{
	background-color:purple;
}
```

**before and after**
They apply changes right before or after an element.
```css
p::before{
	content='-';
}
```