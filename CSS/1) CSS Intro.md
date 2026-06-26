CSS is the language we use to style a Web page.
- CSS stands for Cascading Style Sheets
- CSS describes how HTML elements are to be displayed on screen, paper, or in other media
- CSS saves a lot of work. It can control the layout of multiple web pages all at once
- External stylesheets are stored in CSS files
```css
body {  background-color: lightblue;}  
  
h1 {  color: white;  
  text-align: center;}  
  
p {  font-family: verdana;  
  font-size: 20px;}
```

##### CSS syntax
A CSS rule consists of a selector and a declaration block:
```css
h1{
	color:blue;
	font-size:12px;
}
```
The selector points to the HTML element you want to style.`h1`

The declaration block contains one or more declarations separated by semicolons. `color:blue;` or `font-size:12px;`

Each declaration includes a CSS property name(`color` or `font-size`) and a value(`blue`, `12px`), separated by a colon.
Multiple CSS declarations are separated with semicolons, and declaration blocks are surrounded by curly braces.