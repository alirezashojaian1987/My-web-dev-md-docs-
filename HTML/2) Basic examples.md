All HTML documents must start with a document type declaration: `<!DOCTYPE html>`.
The HTML document itself begins with `<html>` and ends with `</html>`.
The visible part of the HTML document is between `<body>` and `</body>`.

##### HTML headings
HTML headings are defined with the `<h1>` to `<h6>` tags.
`<h1>` defines the most important heading. `<h6>` defines the least important heading:
```html
<h1>This is heading 1</h1>  
<h2>This is heading 2</h2>  
<h3>This is heading 3</h3>
```

##### HTML paragraphs
HTML paragraphs are defined with the `<p>` tag.
```html
<p>This is a paragraph.</p>  
<p>This is another paragraph.</p>
```

##### HTML Links
HTML links are defined with the `<a>` tag:
```html
<a href="https://www.google.com">This is a link</a>
```
The link's destination is specified in the `href` attribute. 
Attributes are used to provide additional information about HTML elements.
You will learn more about attributes in a later chapter.

##### HTML images
HTML images are defined with the `<img>` tag.
The source file (`src`), alternative text (`alt`), `width`, and `height` are provided as attributes:
```html
<img src="w3schools.jpg" alt="W3Schools.com" width="104" height="142">
```

##### How to view HTML source?
Click CTRL+U in an HTML page, or right-click on the page and select "View Page Source". This will open a new tab containing the HTML source code of the page.

##### Inspect an HTML element
Right-click on an element (or a blank area), and choose "Inspect" to see what elements are made up of (you will see both the HTML and the CSS). You can also edit the HTML or CSS on-the-fly in the Elements or Styles panel that opens.
