The HTML `id` attribute is used to specify a unique id for an HTML element.
You cannot have more than one element with the same id in an HTML document.
##### The id attribute
The `id` attribute specifies a unique id for an HTML element. The value of the `id` attribute must be unique within the HTML document.
```html
<!DOCTYPE html>  
<html>  
<head>  
<style>  
#myHeader {  background-color: lightblue;  
  color: black;  
  padding: 40px;  
  text-align: center;}  
</style>  
</head>  
<body>  
  
<h1 id="myHeader">My Header</h1>  
  
</body>  
</html>
```

##### HTML bookmarks with ID and links
HTML bookmarks are used to allow readers to jump to specific parts of a webpage.
Bookmarks can be useful if your page is very long.
```html
<a href="#C4">Jump to Chapter 4</a>
<!--or-->
<a href="html_demo.html#C4">Jump to Chapter 4</a>

<h2 id="C4">Chapter 4</h2>
```
##### Using id in JS
