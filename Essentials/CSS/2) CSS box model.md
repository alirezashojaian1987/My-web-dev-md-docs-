##### The CSS box model
Every box consists of four parts: content, padding, borders and margins.
Explanation of the different parts (from innermost part to outermost part):
- **Content** - The content of the box, where text and images appear
- **Padding** - Clears an area around the content. The padding is transparent
- **Border** - A border that goes around the padding and content
- **Margin** - Clears an area outside the border. The margin is transparent

The box model allows us to add a border around elements, and to define space between elements.
```css
div {
  width: 300px;  
  border: 15px solid green;  
  padding: 50px;  
  margin: 20px;
}
```

##### margin
The CSS margin properties are used to create space around elements, outside of any defined borders.
Margins define the distance between an element's border and the surrounding elements.
+ `margin-top`
+ `margin-right`
+ `margin-left`
+ `margin-bottom`

All the margin properties can have the following values:
- auto - the browser calculates the margin
- _length_ - specifies a margin in px, pt, cm, etc.
- _%_ - specifies a margin in % of the width of the containing element
- inherit - specifies that the margin should be inherited from the parent element
```css
p{
	margin-left:20px;
}
```

**The auto value**
You can set the `margin` property to auto to horizontally center the element within its container.
```css
div{
	width:300px;
	margin:auto;
	border:1px solid red;
}
```

**The inherit value**
You can set the `margin` inherit to let the margin be inherited from the parent element.
```css
div{
	border:1px solid red;
	margin-left:100px;
}

p.ex1{
	margin-left:inherit;
}
```
##### border
The CSS border properties allow you to specify the style, width, and color of an element's border.
###### Borders
The `border-style` property specifies what kind of border to display.
- `dotted` - Defines a dotted border
- `dashed` - Defines a dashed border
- `solid` - Defines a solid border
- `double` - Defines a double border
- `groove` - Defines a 3D grooved border. The effect depends on the border-color value
- `ridge` - Defines a 3D ridged border. The effect depends on the border-color value
- `inset` - Defines a 3D inset border. The effect depends on the border-color value
- `outset` - Defines a 3D outset border. The effect depends on the border-color value
- `none` - Defines no border
- `hidden` - Defines a hidden border
```css
p.dotted{
	border-style:dotted;
}
```

###### Border width
The `border-width` property specifies the width of the four borders.
The width can be set as a specific size (in px, pt, cm, em, etc) or by using one of the three pre-defined values: thin, medium, or thick:
```css
p.one{
	border-style: solid;  
	border-width: 5px;
}  
  
p.two{
	border-style: solid;  
	border-width: medium;
}  
  
p.three{
	border-style: dotted;  
	border-width: 2px;
}  
  
p.four{
	border-style: dotted;  
	border-width: thick;
}
```
###### CSS border color
The `border-color` property is used to set the color of the four borders.
```css
p.one{
	border-style: solid;  
	border-color: red;
}
```

###### CSS Border sides
In CSS, there are also properties for specifying each of the borders (top, right, bottom, and left):
+ `border-top-style`
+ `border-right-style`
+ `border-bottom-style`
+ `border-left-style`
```css
p{
	border-top-style: dotted;
	border-left-style: solid;
}
```
###### CSS Rounded borders
The `border-radius` property is used to add rounded borders to an element:
```css
p{
	border: 2px solid red;
	border-radius:5px;
}
```

##### padding
The CSS padding properties are used to generate space around an element's content, inside of any defined borders.

##### content
