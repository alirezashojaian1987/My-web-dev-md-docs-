#### CSS backgrounds
The CSS background properties are used to add background effects for elements.
In these chapters, you will learn about the following CSS background properties:
- `background-color`
- `background-image`
- `background-repeat`
- `background-attachment`
- `background-position`
- `background` (shorthand property)
##### Background-color
The `background-color` property specifies the background color of an element.
```css
body{
	background-color:blue;
}
```
With CSS, a color is most often specified by:
- a valid color name - like "red"
- a HEX value - like "#ff0000"
- an RGB value - like "rgb(255,0,0)"
##### Opacity / Transparency
The `opacity` property specifies the opacity/transparency of an element. It can take a value from 0.0 - 1.0. The lower value, the more transparent:
```css
div{
	background-color:green;
	opacity:0.3;
}
```
*!Note:* When using the `opacity` property to add transparency to the background of an element, all of its child elements inherit the same transparency. This can make the text inside a fully transparent element hard to read.

If you do not want to apply opacity to child elements, like in our example above, use **RGBA** color values. The following example sets the opacity for the background color and not the text:
```css
div{
	background-color:rgba(0,128,0, 0.3); /* Green background with 30% opacity */
}
```

#### CSS background-image
The background-image property specifies an image to use as the background of an element.
By default, the image is repeated so it covers the entire element.
```css
body{
	background-image:url("pic.gif");
}
```

#### CSS background image repeat
##### Background-repeat
The `background-repeat` property sets if/how a background image will be repeated. By default, a background-image is repeated both vertically and horizontally.
##### background-repeat horizontally
```css
body{
	background-image:url("gradient_bg.png");
	background-repeat:repeat-x;
}
```
*Note:* To repeat an image only vertically, use `background-repeat:repeat-y;`
##### No-repeat
```css
body{
	background-image:url("image.png");
	background-repeat:no-repeat;
}
```

##### background-position
The `background-position` property is used to set the starting position of the background image.
By default, a background-image is placed at the top-left corner of an element.
```css
body{
	background-image:url("img.png");
	background-repeat:no-repeat;
	background-position:right-top;
}
```

#### CSS background-attachment
The `background-attachment` property specifies whether the background image should scroll or be fixed (will not scroll with the rest of the page):
```css
body{
    background-image: url("img_tree.png");  
	background-repeat: no-repeat;  
	background-position: right top;  
	background-attachment: fixed;
}
```

Specify that the background image should scroll with the rest of the page:
```css
body{
	background-image: url("img_tree.png");  
	background-repeat: no-repeat;  
	background-position: right top;  
	background-attachment: scroll;
}
```
