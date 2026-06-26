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
This property is used to align the flex items when they do not use all available space on the main-axis (horizontally).
This property can have one of the following values:
- `center`:aligns the flex items in the center of the container
- `flex-start` (default):aligns the flex items at the beginning of the container (this is default)
- `flex-end`:aligns the flex items at the end of the container
- `space-around`:displays the flex items with space around them
- `space-between`:displays the flex items with space between them
- `space-evenly`:displays the flex items with equal space around them
```css
.flex-container{
	display:flex;
	justify-content: ;
}
```

##### align-items
This property is used to align the flex items when they do not use all available space on the cross-axis (vertically).
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
.flex{
    display:flex;
    align-items: flex-end;
    justify-content: center;
    height:400px;
    border:3px solid black;
    flex-direction: column;
}
  
.box{
    width:100px;
    height:100px;
    background-color: aquamarine;
    border:3px solid aqua;
}
```

##### flex-direction property
This property can have one of the following values:
- `row` (default)
- `column`
- `row-reverse`
- `column-reverse`
```css
.flex-container{
	display:flex;
	flex-direction:row;
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
```css
.flex-container{
	display:flex;
	flex-wrap:wrap;
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
When you shrink your web size, it also affects the size of elements inside, to avoid that, we use `flex-shrink`
```css
flex-shrink:0;
```
You can use it on elements, containers and... to avoid getting shrinked.

##### Flex-basis
