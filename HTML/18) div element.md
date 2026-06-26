The `<div>` element is used as a container for other HTML elements.
The `<div>` element is by default a block element, meaning that it takes all available width, and comes with line breaks before and after.
The `<div>` element has no required attributes, but `style`, `class` and `id` are common.

##### `<div>` as a container
The `<div>` element is often used to group sections of a web page together.
```css
div{
	background-color: gray;
}
```

```html
<div>  
  <h2>London</h2>  
  <p>London is the capital city of England.</p>  
  <p>London has over 9 million inhabitants.</p>  
</div>
```

##### Center align a `<div>` element
If you have a `<div>` element that is not 100% wide, and you want to center-align it, set the CSS `margin` property to `auto`.
```css
div{
	width:300px;
	margin:auto;
}
```

##### Aligning `<div>` elements side by side
The CSS `float` property was not originally meant to align `<div>` elements side-by-side, but has been used for this purpose for many years.

The CSS `float` property is used for positioning and formatting content and allows elements to be positioned horizontally, rather than vertically.
```css
.mycontainer {  width:100%;  
  overflow:auto;}  
.mycontainer div {  width:33%;  
  float:left;}
```

##### Inline-block
If you change the `<div>` element's `display` property from `block` to `inline-block`, the `<div>` elements will no longer add a line break before and after, and will be displayed side by side instead of on top of each other.
```css
div {  width: 30%;  
  display: inline-block;}
```

