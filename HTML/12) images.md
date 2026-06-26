#### Images
Images can improve the design and the appearance of a web page.
```html
<img src="url" alt="Alternate text">
```

##### Image size - width and height
You can use the `style` attribute to specify the width and height of an image.
```html
<img src="imga.jpg" alt="A pic" style="width:500px;height:600px;">
```
U can also use the `width` and `height` attributes.

##### Image floating
Use the CSS `float` property to let the image float to the right or to the left of a text:
```html
<p><img src="smiley.gif" alt="Smiley face" style="float:right;width:42px;height:42px;">  
The image will float to the right of the text.</p>  
  
<p><img src="smiley.gif" alt="Smiley face" style="float:left;width:42px;height:42px;">  
The image will float to the left of the text.</p>
```

#### Image map

#### HTML background images
To add a background image on an HTML element, use the HTML `style` attribute and the CSS `background-image` property:
*Example:*
Add a background image on a `<p>` element:
```html
<p style="background-image: url('img_.jpg');">
```
You can also specify the background image in the `<style>` element, in the `<head>` section:
```html
<style>  
body{
	background-image: url('img_girl.jpg');
}
</style>
```
*!Note:* If the background image is smaller than the element, the image will repeat itself, horizontally and vertically, until it reaches the end of the element, to avoid that we can set the `background-repeat` property to `no-repeat`.
```html
<style>  
body{  
	background-image: url('example_img_girl.jpg');  
    background-repeat: no-repeat;
}  
</style>
```

##### Background cover
If you want the background image to cover the entire element, you can set the `background-size` property to `cover.`
Also, to make sure the entire element is always covered, set the `background-attachment` property to `fixed:`
This way, the background image will cover the entire element, with no stretching (the image will keep its original proportions):
```html
<style>  
body{
	background-image: url('img_girl.jpg');  
	background-repeat: no-repeat;  
    background-attachment: fixed;  
    background-size: cover;
}  
</style>
```
*Note:* If you want the background image to stretch to fit the entire element, you can set the `background-size` property to `100% 100%`.

#### HTML `<picture>` element
The HTML `<picture>` element allows you to display different pictures for different devices or screen sizes.
The `<picture>` element contains one or more `<source>` elements, each referring to different images through the `srcset` attribute. This way the browser can choose the image that best fits the current view and/or device.
Each `<source>` element has a `media` attribute that defines when the image is the most suitable.
```html
<picture>  
  <source media="(min-width: 650px)" srcset="img_food.jpg">  
  <source media="(min-width: 465px)" srcset="img_car.jpg">  
  <img src="img_girl.jpg">  
</picture>
```
*!Note:* Always specify an `<img>` element as the last child element of the `<picture>` element. The `<img>` element is used by browsers that do not support the `<picture>` element, or if none of the `<source>` tags match.

##### When to use the picture element?
There are 2 main purposes for the `<picture>` element:
1. **Bandwidth**
   If you have a small screen or device, it is not necessary to load a large image file. The browser will use the first `<source>` element with matching attribute values, and ignore any of the following elements.
2. **Format support**
   Some browsers or devices may not support all image formats. By using the `<picture>` element, you can add images of all formats, and the browser will use the first format it recognizes, and ignore any of the following elements.
   ```html
   <picture>  
  <source srcset="img_avatar.png">  
  <source srcset="img_girl.jpg">  
  <img src="img_beatles.gif" alt="Beatles" style="width:auto;">  
  </picture>
    ```

