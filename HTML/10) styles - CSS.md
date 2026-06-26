CSS stands for Cascading Style Sheets.
CSS saves a lot of work. It can control the layout of multiple web pages all at once.

##### Using CSS
CSS can be added to HTML docs in 3 ways
- **Inline** - by using the `style` attribute inside HTML elements
- **Internal** - by using a `<style>` element in the `<head>` section
- **External** - by using a `<link>` element to link to an external CSS file

##### Inline CSS
An inline CSS is used to apply a unique style to a single HTML element.
An inline CSS uses the `style` attribute of an HTML element.
```html
<h1 style="color:blue;">A Blue Heading</h1>  
  
<p style="color:red;">A red paragraph.</p>
```

##### Internal CSS
An internal CSS is used to define a style for a single HTML page.
An internal CSS is defined in the `<head>` section of an HTML page, within a `<style>` element.
```html
<!DOCTYPE html>  
<html>  
<head>  
<style>  
body {background-color: powderblue;}  
h1   {color: blue;}  
p    {color: red;}  
</style>  
</head>  
<body>  
  
<h1>This is a heading</h1>  
<p>This is a paragraph.</p>  
  
</body>  
</html>
```

##### External CSS
An external style sheet is used to define the style for many HTML pages.
To use an external style sheet, add a link to it in the `<head>` section of each HTML page:
```html
<!DOCTYPE html>  
<html>  
<head>  
  <link rel="stylesheet" href="styles.css">  
</head>  
<body>  
  
<h1>This is a heading</h1>  
<p>This is a paragraph.</p>  
  
</body>  
</html>
```

```css
body {  background-color: powderblue;}  
h1 {  color: blue;}  
p {  color: red;}
```

##### CSS padding
The CSS `padding` property defines a padding (space) between the text and the border.
```css
p{
	border:2px solid black;
	padding:30px;
}
```

##### CSS margin
The CSS `margin` property defines a margin (space) outside the border.
```css
p{
	border:2px solid black
	margin:50px;
}
```