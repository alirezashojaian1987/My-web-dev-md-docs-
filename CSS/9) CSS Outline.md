#### Outline
##### Outline
An outline is a line that is drawn around elements, OUTSIDE the borders, to make the element "stand out".
CSS has the following outline properties:
+ **outline-style** - Specifies the style of the outline
+ **outline-color** - Specifies the color of the outline
+ **outline-width** - Specifies the width of the outline
+ **outline-offset** - Adds space between the outline and the edge/border of an element
##### The outline-style property
- `dotted` - Defines a dotted outline
- `dashed` - Defines a dashed outline
- `solid` - Defines a solid outline
- `double` - Defines a double outline
- `groove` - Defines a 3D grooved outline
- `ridge` - Defines a 3D ridged outline
- `inset` - Defines a 3D inset outline
- `outset` - Defines a 3D outset outline
- `none` - Defines no outline
- `hidden` - Defines a hidden outline
```css
p.dotted {outline-style: dotted;}  
p.dashed {outline-style: dashed;}  
p.solid {outline-style: solid;}  
p.double {outline-style: double;}  
p.groove {outline-style: groove;}  
p.ridge {outline-style: ridge;}  
p.inset {outline-style: inset;}  
p.outset {outline-style: outset;}
```

#### CSS Outline width
##### Outline width
The **outline-width** property specifies the width of the outline, and can have one of the following values:
- `thin` (typically 1px)
- `medium` (typically 3px)
- `thick` (typically 5px)
- A specific size (in px, pt, cm, em, etc)
```css
p {  padding: 5px;  
  outline-style: solid;  
  outline-color: green;}  
  
p.ex1 {  outline-width: thin;}  
  
p.ex2 {  outline-width: medium;}  
  
p.ex3 {  outline-width: thick;}  
  
p.ex4 {  outline-width: 8px;}
```

#### CSS Outline color
##### Outline color
The **outline-color** property is used to set the color of the outline.
The color can be set by:
- name - specify a color name, like "red"
- HEX - specify a hex value, like "#ff0000"
- RGB - specify a RGB value, like "rgb(255,0,0)"
- HSL - specify a HSL value, like "hsl(0, 100%, 50%)"
- invert - performs a color inversion (which ensures that the outline is visible, regardless of color background)

#### CSS Outline offset
##### Outline offset
The **outline-offset** property adds a space between an outline and the edge/border of an element. The space between an element and its outline is transparent.

The following example specifies an outline 15px outside the border edge:
```css
p{
	margin: 30px;  
	padding: 5px;  
	border: 1px solid black;  
	outline: 3px solid red;  
	outline-offset: 15px;
}
```

The following example shows that the space between an element's border and its outline is transparent:
```css
p{
	margin: 30px;  
	padding: 5px;  
	background: yellow;  
	border: 1px solid black;  
	outline: 3px solid red;  
	outline-offset: 15px;
}
```

The following example shows the use of an outline-offset with a negative value, now the outline will be placed inside the border edge:
```css
p{
	margin: 30px;  
	padding: 5px;  
	background: yellow;  
	border: 1px solid black;  
	outline: 3px solid red;  
	outline-offset: -5px;
}
```

