#### Links
Links are found in nearly all web pages. Links allow users to click their way from page to page.
*!Note:* A link does not have to be text. A link can be an image or any other HTML element!

##### HTML links - syntax
The HTML `<a>` tag defines a hyperlink. It has the following syntax:
```html
<a href="url">link text</a>
```
`href` attribute indicates the link's destination.
```html
<a href="https://www.google.com/">This is a link for Google</a>
```

##### HTML links - The target attribute
By default, the linked page will be displayed in the current browser window. To change this, you must specify another target for the link.
The `target` attribute specifies where to open the linked document.

The `target` attribute can have one of the following values:
- `_self` - Default. Opens the document in the same window/tab as it was clicked
- `_blank` - Opens the document in a new window or tab
- `_parent` - Opens the document in the parent frame
- `_top` - Opens the document in the full body of the window
```html
<a href="https://www.google.com/" target="_blank">This is a link</a>
```

##### HTML links - Use an image as a link
To use an image as a link, just put the `<img>` tag inside the `<a>` tag:
```html
<a href="default.asp">  
<img src="smiley.gif" alt="HTML tutorial" style="width:42px;height:42px;">  
</a>
```

##### Link to an Email address
Use `mailto:` inside the `href` attribute to create a link that opens the user's email program(to let them send a new email):
```html
<a href="mailto:someone@example.com">Send email</a> 
```

##### Button as a link
To use an HTML button as a link, you have to add some JavaScript code.
JavaScript allows you to specify what happens at certain events, such as a click of a button:
```html
<button onclick="document.location='default.asp'">HTML Tutorial</button>
```

#### HTML links different colors
An HTML link is displayed in a different color depending on whether it has been visited, is unvisited, or is active.
By default, a link will appear like this(in all browsers):
- An unvisited link is underlined and blue
- A visited link is underlined and purple
- An active link is underlined and red

You can change the link state colors, by using CSS.
```css
a:link{
	  color: green;  
	  background-color: transparent;  
	  text-decoration: none;}  
  
a:visited {  color: pink;  
  background-color: transparent;  
  text-decoration: none;}  
  
a:hover {  color: red;  
  background-color: transparent;  
  text-decoration: underline;}  
  
a:active {  color: yellow;  
  background-color: transparent;  
  text-decoration: underline;}  
```

##### Link buttons
A link can also be styled as a button, by using CSS:
```css
a:link, a:visited {  background-color: #f44336;  
  color: white;  
  padding: 15px 25px;  
  text-align: center;  
  text-decoration: none;  
  display: inline-block;}  
  
a:hover, a:active {  background-color: red;}
```

#### HTML links - Create bookmarks
HTML links can be used to create bookmarks, so that readers can jump to specific parts of a web page. Bookmarks can be useful if a web page is very long.

*Example:*
First, use the `id` attribute to create a bookmark:
```html
<h2 id="C4">Chapter 4</h2>
```
Then add a link to the bookmark("Jump to chapter 4"), from within the same page:
```html
<a href="#C4">Go to chapter 4</a>
```

