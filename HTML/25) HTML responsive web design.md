Responsive web design is about creating web pages that look good on all devices!

A responsive web design will automatically adjust for different screen sizes and viewports.
##### Setting the viewport
To create a responsive website, add the following `<meta>` tag to all your web pages:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
This will set the viewport of your page, which will give the browser instructions on how to control the page's dimensions and scaling.
##### Responsive images
Responsive images are images that scale nicely to fit any browser size.
If the CSS `width` property is set to 100%, the image will be responsive and scale up and down:
```html
<img src="img_girl.jpg" **style="width:100%;">
```
Notice that in the example above, the image can be scaled up to be larger than its original size. A better solution, in many cases, will be to use the `max-width` property instead.
If the `max-width` property is set to 100%, the image will scale down if it has to, but never scale up to be larger than its original size:
```html
<img src="img_girl.jpg" style="**max-width:100%;**height:auto;">
```

##### Show different images depending on browser width
The HTML `<picture>` element allows you to define different images for different browser window sizes.
Resize the browser window to see how the image below changes depending on the width:
```html
<picture>  
  <source srcset="img_smallflower.jpg" media="(max-width: 600px)">  
  <source srcset="img_flowers.jpg" media="(max-width: 1500px)">  
  <source srcset="flowers.jpg">  
  <img src="img_smallflower.jpg" alt="Flowers">  
</picture>
```
##### Responsive text size
The text size can be set with a "vw" unit, which means the "viewport width".
That way the text size will follow the size of the browser window:
```html
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>

<h1 style="font-size:10vw;">Responsive Text</h1>

<p style="font-size:5vw;">Resize the browser window to see how the text size scales.</p>

<p style="font-size:5vw;">Use the "vw" unit when sizing the text. 10vw will set the size to 10% of the viewport width.</p>

<p>Viewport is the browser window size. 1vw = 1% of viewport width. If the viewport is 50cm wide, 1vw is 0.5cm.</p>

</body>
</html>
```
*Note:* Viewport is the browser window size. 1vw = 1% of viewport width. If the viewport is 50cm wide, 1vw is 0.5cm.
##### Media queries
In addition to resize text and images, it is also common to use media queries in responsive web pages.

With media queries you can define completely different styles for different browser sizes.
###### Example
```html
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
* {
  box-sizing: border-box;
}

.left {
  background-color: #2196F3;
  padding: 20px;
  float: left;
  width: 20%; /* The width is 20%, by default */
}

.main {
  background-color: #f1f1f1;
  padding: 20px;
  float: left;
  width: 60%; /* The width is 60%, by default */
}

.right {
  background-color: #04AA6D;
  padding: 20px;
  float: left;
  width: 20%; /* The width is 20%, by default */
}

/* Use a media query to add a break point at 800px: */
@media screen and (max-width: 800px) {
  .left, .main, .right {
    width: 100%; /* The width is 100%, when the viewport is 800px or smaller */
  }
}
</style>
</head>
<body>

<h2>Media Queries</h2>
<p>Resize the browser window.</p>

<p>Make sure you reach the breakpoint at 800px when resizing this frame.</p>

<div class="left">
  <p>Left Menu</p>
</div>

<div class="main">
  <p>Main Content</p>
</div>

<div class="right">
  <p>Right Content</p>
</div>

</body>
</html>

```

