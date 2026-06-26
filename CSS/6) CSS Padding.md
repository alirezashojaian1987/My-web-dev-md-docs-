The CSS padding properties are used to generate space around an element's content, inside of any defined borders.
##### Padding - Individual sides
CSS has properties for specifying the padding for each side of an element:
+ `padding-top`
+ `padding-right`
+ `padding-bottom`
+ `padding-left`
All the padding properties can have the following values:
- _length_ - specifies a padding in px, pt, cm, etc.
- _%_ - specifies a padding in % of the width of the containing element
- inherit - specifies that the padding should be inherited from the parent element
```css
div{
	padding-top: 50px;  
	padding-right: 30px;  
	padding-bottom: 50px;  
	padding-left: 80px;
}
```
##### Padding and element width
The CSS width property specifies the width of the element's content area. The content area is the portion inside the padding, border, and margin of an element (the box model).
So, if an element has a specified width, the padding added to that element will be added to the total width of the element. This is often an undesirable result.

Here, the `<div>` element is given a width of 300px. However, the actual width of the `<div>` element will be 350px (300px + 25px of left padding + 25px of right padding):
```css
div{
	width:300px;
	padding:25px;
}
```
##### Padding and box-sizing
The `box-sizing` property defines how the width and height of an element are calculated: should they include padding and borders, or not.

The `box-sizing` property can have the following values:
+ `content-box` : This is default. The width and height properties includes only the content (border and padding are not included)
+ `border-box` : The width and height properties includes content, padding and border
So, to keep the width at 300px, no matter the amount of padding, you can use the `box-sizing: border-box;` This causes the element to maintain its actual width; if you increase the padding, the available content space will decrease.

Use the box-sizing property to keep the width at 300px, no matter the amount of padding:
```css
div{
	width:300px;
	padding:25px;
	box-sizing:border-box;
}
```
