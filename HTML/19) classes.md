The HTML `class` attribute is used to specify a class for an HTML element.
Multiple HTML elements can share the same class.

##### The class attribute
The `class` attribute is often used to point to a class name in a style sheet. It can also be used by JavaScript to access and manipulate elements with the specific class name.
```html
<!DOCTYPE html>  
<html>  
<head>  
<style>  
.city {  background-color: tomato;  
  color: white;  
  border: 2px solid black;  
  margin: 20px;  
  padding: 20px;}  
</style>  
</head>  
<body>  
  
<div class="city">  
  <h2>London</h2>  
  <p>London is the capital of England.</p>  
</div>  
  
<div class="city">  
  <h2>Paris</h2>  
  <p>Paris is the capital of France.</p>  
</div>  
  
<div class="city">  
  <h2>Tokyo</h2>  
  <p>Tokyo is the capital of Japan.</p>  
</div>  
  
</body>  
</html>
```

```html
<!DOCTYPE html>  
<html>  
<head>  
<style>  
.note {  font-size: 120%;  
  color: red;}  
</style>  
</head>  
<body>  
  
<h1>My <span class="note">Important</span> Heading</h1>  
<p>This is some <span class="note">important</span> text.</p>  
  
</body>  
</html>
```

##### Multiple classes
HTML elements can belong to more than one class.
To define multiple classes, separate the class names with a space, e.g. `<div class="city main">`. The element will be styled according to all the classes specified.
```html
<!DOCTYPE html>
<html>
<head>
<style>
.city {
  background-color: tomato;
  color: white;
  padding: 10px;
} 

.main {
  text-align: center;
}
</style>
</head>
<body>

<h2>Multiple Classes</h2>
<p>Here, all three h2 elements belongs to the "city" class. In addition, London also belongs to the "main" class, which center-aligns the text.</p>

<h2 class="city main">London</h2>
<h2 class="city">Paris</h2>
<h2 class="city">Tokyo</h2>

</body>
</html>
```

##### Use of class in JS
