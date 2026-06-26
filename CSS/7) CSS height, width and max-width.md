The CSS `height` and `width` properties are used to set the height and width of an element
The CSS `max-width` property is used to set the maximum width of an element.

The `height` and `width` properties are used to set the height and width of an element.
The height and width do not include padding, borders, or margins. It sets the height and width of the area inside the padding, border, and margin of the element.
##### CSS height and width values
The `height` and `width` properties can have the following values:
- `auto` - This is default. The browser calculates the height and width
- `length` - Defines the height or width in px, cm, em, etc.
- `%` - Defines the height or width in percent of the containing block
- `initial` - Sets the height or width to its default value
- `inherit` - The height or width will be inherited from its parent value
```css
div{
	height:200px;
	width 50%;
	background-color:powderblue;
}
```
*!Note:* Remember that the `height` and `width` properties do not include padding, borders, or margins! They set the height/width of the area inside the padding, border, and margin of the element!
##### CSS using max-width
The `max-width` property sets the maximum allowed width of an element. This prevents the width of an element to be larger than the `max-width` property value.
The `max-width` property can have the following values:
- `length` - Defines the maximum width in px, cm, etc.
- _`%`_ - Defines the maximum width in percent of the containing block
- `none` - This is default. Means that there is no maximum width
one problem with the `width` property can occur when the browser window is smaller than the width of the element. The browser then adds a horizontal scrollbar to the page. So, using `max-width` will improve the browser's handling on small windows.
```css
.div1{
	max-width: 500px;  
	background-color: powderblue;
}
  
.div2{
	width: 500px;  
	background-color: powderblue;
}
```
*!Note:* If you use both the `width` and `max-width` properties on the same element, and the value of the `width` is larger than the `max-width`; the `max-width` value will be used.
```css
.div1{
	width:100%;
	max-width:900px;
	background-color:powderblue;
}
```

