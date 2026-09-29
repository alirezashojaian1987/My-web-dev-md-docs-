##### CSS Flexbox
Flexbox is a layout model for arranging items (horizontally or vertically) within a container, in a flexible and responsive way.

Flexbox makes it easy to design a flexible and responsive layout, without using float or positioning.
```html
<body>
	<div class="container">
		<div>item1</div>
		<div>item2</div>
		<div>item3</div>
		<div>item4</div>
		<div>item5</div>
	</div>
</body>
```

```css
*{
    box-sizing: border-box;
    margin:0;
    padding:0;
}
  
.container{
    display: flex;
    background-color: dodgerblue;
}
  
.container div{
    background-color: #f1f1f1;
    margin:10px;
    padding:20px;
    font-size: 24px;
}
```
##### CSS Flexbox components
A flexbox always consists of:
+ **A flex container:** The parent (container) element, where the `display` property is set to `flex` or `inline-flex`. 
+ **One or more flex items:** The direct children of the flex container automatically becomes flex items
##### CSS flex container
The flex container element can have the following properties:
- `display` - Must be set to `flex` or `inline-flex`
- `flex-direction` - Sets the display-direction of flex items
- `flex-wrap` - Specifies whether the flex items should wrap or not
- `flex-flow` - Shorthand property for `flex-direction` and `flex-wrap`
- `justify-content` - Aligns the flex items when they do not use all available space on the main-axis (horizontally)
- `align-items` - Aligns the flex items when they do not use all available space on the cross-axis (vertically)
- `align-self` is for one item only
- `align-content` - Aligns the flex lines when there is extra space in the cross axis and flex items wrap
##### Justify-content
The `justify-content` is used to align the flex items when they do not use all available space on the main-axis (horizontally).
This property can have one of the following values:
- `center`:aligns the flex items in the center of the container
- `flex-start` (default):aligns the flex items at the beginning of the container (this is default)
- `flex-end`:aligns the flex items at the end of the container
- `space-around`:displays the flex items with space around them
- `space-between`:displays the flex items with space between them
- `space-evenly`:displays the flex items with equal space around them
```html
<body>
	<div class="container">
		<div>1</div>
		<div>2</div>
		<div>3</div>
		<div>4</div>
		<div>5</div>
		<div>6</div>
		<div>7</div>
		<div>8</div>
		<div>9</div>
	</div>
</body>
```

```css
.container{
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    background-color: dodgerblue;
}
  
.container div{
    background-color: #f1f1f1;
    width: 100px;
    margin: 10px;
    padding: 10px;
    text-align: center;  
    font-size: 30px;
}
```

##### align-items
The `align-items` property is used to align the flex items when they do not use all available space on the cross-axis (vertically).
This property can have one of the following values:
- `center`:aligns the flex items in the middle of the container
- `flex-start`:aligns the flex items at the top of the container
- `flex-end`:value aligns the flex items at the bottom of the container
- `stretch`:value stretches the flex items to fill the container (this is equal to "normal" which is default)
- `baseline`:aligns the flex items at the baseline of the container
- `normal` (default)
```css
.flex-container{
	display: flex;  
	height: 200px;  
	align-items: center;
}
```

**Example of align-self:**
```html
<div class="flex">
	<div class="box">1</div>
	<div class="box">2</div>
	<div class="box">3</div>
	<div class="box">4</div>
	<div class="box">5</div>
	<div class="box" style="align-self: center;">6</div>
</div>
```

```css
.container{
    height:200px;
    display: flex;
    align-items: baseline;
    background-color: dodgerblue;
}
  
.container div{
    background-color: #f1f1f1;
    width: 100px;
    margin: 10px;
    padding: 10px;
    text-align: center;  
    font-size: 30px;
}
```

**align-self**
The `align-self` property specifies the alignment for the selected item inside the flexible container.
```css
align-self:center;
```
##### flex-direction property
This property can have one of the following values:
- `row` (default)
- `column`
- `row-reverse`
- `column-reverse`
```css
*{
    box-sizing: border-box;
    margin:0;
    padding:0;
}
  
.container{
    display: flex;
    flex-direction: column;
    background-color: dodgerblue;
}
  
.container div{
    background-color: #f1f1f1;
    width: 100px;
    margin: 10px;
    padding: 10px;
    text-align: center;  
    font-size: 30px;
}
```

*Example:* Sometimes u want all your elements on a website to be centered horizontally, here's how you can do it:
```css
body{
	display:flex;
	flex-direction:column;
	align-items:center;
}
```

##### gap
`gap` property defines a space between the elements so you probably won't need to use margin.
```css
div{
	display:flex;
	justify-content:center;
	align-items:center;
	gap:20px;
}
```
**row-gap & column-gap:**
You can also define gaps only for row or column:
```css
div{
	display:flex;
	justify-content:center;
	align-items:center;
	row-gap:20px;
}
```

##### flex-wrap and grow
The `flex-wrap` property specifies whether the flex items should wrap or not, if there is not enough room for them on one flex line. This actually helps to make your `flex-box` responsive.
This property can have one of the following values:
- `nowrap` (default)
- `wrap`
- `wrap-reverse`

The `nowrap` value specifies that the flex items will not wrap (this is default)

The `wrap` value specifies that the flex items will wrap if necessary
```css
*{
    box-sizing: border-box;
    margin:0;
    padding:0;
}
  
.container{
    display: flex;
    flex-wrap: wrap;
    background-color: dodgerblue;
}
  
.container div{
    background-color: #f1f1f1;
    width: 100px;
    margin: 10px;
    padding: 10px;
    text-align: center;  
    font-size: 30px;
}
```

**flex-grow**
When there is empty space for a defined flex container, flex grow for an item can help us fill that remaining gap.
```css
.flex{
    display:flex;
    align-items: center;
    justify-content: flex-start;
    border:3px solid black;
    width:100%;
}
  
.box{
    width:50px;
    height:100px;
    background-color: aquamarine;
    border:3px solid aqua;
}
```

```html
<div class="flex">
	<div class="box">1</div>
	<div class="box">2</div>
	<div class="box" style="flex-grow: 1;">3</div>
	<div class="box">4</div>
	<div class="box">5</div>
	<div class="box">6</div>
</div>
```
Now the item3's size fills the gap.
*!Note:* Remember that using `flex-grow` for two or more items, the remaining space is divided equally for them.
##### Flex-shrink
When you shrink your web size, it also affects the size of elements inside, to avoid that, we use `flex-shrink`. The default value is 1. 
```css
flex-shrink:0;
```
You can use it on elements, containers and... to avoid getting shrinked.