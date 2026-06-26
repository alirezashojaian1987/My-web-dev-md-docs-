The CSS border properties allow you to specify the style, width, and color of an element's border.
#### Borders
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

#### Border width
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
#### CSS border color
The `border-color` property is used to set the color of the four borders.
```css
p.one{
	border-style: solid;  
	border-color: red;
}
```

#### CSS Border sides
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
#### CSS Rounded borders
The `border-radius` property is used to add rounded borders to an element:
```css
p{
	border: 2px solid red;
	border-radius:5px;
}
```

