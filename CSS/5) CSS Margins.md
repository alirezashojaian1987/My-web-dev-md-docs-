#### Margins
The CSS margin properties are used to create space around elements, outside of any defined borders.

Margins define the distance between an element's border and the surrounding elements.

With CSS, you have full control over the margins. CSS has properties for setting the margin for each individual side of an element (top, right, bottom, and left), and a shorthand property for setting all the margin properties in one declaration.
##### Margin - individual sides
CSS has properties for specifying the margin for each side of an element:
+ `margin-top`
+ `margin-right`
+ `margin-bottom`
+ `margin-left`
All the margin properties can have the following values:
- auto - the browser calculates the margin
- length - specifies a margin in px, pt, cm, etc.
- % - specifies a margin in % of the width of the containing element
- inherit - specifies that the margin should be inherited from the parent element
```css
p{
	margin-top:100px;
	margin-left:200px;
}
```
##### The auto value
You can set the `margin` property to `auto` to horizontally center the element within its container.
The element will then take up the specified width, and the remaining space will be split equally between the left and right margins.
```css
div{
	width:300px;
	margin:auto;
	border: 1px solid red;
}
```

#### CSS Margin collapse
Margin collapse is when two margins collapse into a single margin.
Top and bottom margins of elements are sometimes collapsed into a single margin that is equal to the largest of the two margins.