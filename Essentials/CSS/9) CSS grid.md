##### Grid
The Grid Layout Module offers a grid-based layout system, with rows and columns.
The Grid Layout Module allows developers to easily create complex web layouts.
The Grid Layout Module makes it easy to design a responsive layout structure, without using `float` or positioning.

*Note:* You can also use the firefox tools when working with grid for a better grid lines view.

Create a grid container by setting the `display` property with a value of `grid` or `inline-grid`. All direct children of grid containers become grid items.
```css
display:grid;
```
Grid items are placed in rows by default and span the full width of the grid container.
```css
display:inline-grid;
```


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
    display: grid;
    grid-template-columns: auto auto auto;
    background-color: dodgerblue;
    padding:10px;
}
  
.container div{
    background-color: #f1f1f1;
    border:1px solid black;
    padding:10px;
    font-size: 30px;
    text-align: center;
}
```

**Explicit Grid**
Explicitly set a grid by creating columns and rows with the `grid-template-columns` and `grid-template-rows` properties.
```css
.wrapper{
    display: grid;
    grid-template-columns:100px 100px 100px;
    grid-template-rows: 100px 100px 100px;
}
  
.item{
    background-color: purple;
    display: flex;
    align-items: center;
    justify-content: center;
    border:2px solid black;
}
```

You can determine how many rows, columns and also the size for them you need.
*!Note:* You can also use `fr` as a unit to help creating flexible grid tracks. It represents a fraction of the available space in the grid container (works like Flexbox’s unitless values).
`fr` is calculated based on the remaining space when combined with other length values.
```css
grid-template-columns: 3rem 25% 1fr 2fr;
```
In this example, `3rem` and `25%` would be subtracted from the available space before the size of `fr` is calculated:  
`1fr = ((width of grid) - (3rem) - (25% of width of grid)) / 3`

**Minimum and maximum grid track sizes**
```css
grid-template-rows:minmax(100px, auto);
grid-template-columns:minmax(auto,50%) 1fr 3em;
```
The `minmax()` function accepts 2 arguments: the first is the minimum size of the track and the second the maximum size. Alongside length values, the values can also be `auto`, which allows the track to grow/stretch based on the size of the content.

**Repeating grid tracks**
Define repeating grid tracks using the `repeat()` notation. This is useful for grids with items with equal sizes or many items.
```css
grid-template-rows: repeat(4,100px);
grid-template-columns:repeat(3,1fr);
```
The `repeat()` notation accepts 2 arguments: the first represents the number of times the defined tracks should repeat, and the second is the track definition.
*!Note:*`repeat()` can also be used within track listings.
```css
grid-template-columns:30px repeat(3,1fr) 30px;
```

**Grid gaps(gutters)**
The `grid-column-gap` and `grid-row-gap` properties create gutters between columns and rows.
```css
grid-row-gap:20px;
grid-column-gap:5rem;
```

*!Note:* `grid-gap` is shorthand for `grid-row-gap` and `grid-column-gap`.
```css
grid-gap:100px 1em;
```

```css
grid-gap:2rem;
```
One value sets equal row and column gaps.

**Positioning items by grid line numbers**
Grid lines are essentially lines that represent the start of, the end of, or between column and row tracks.
Each line, starting from the start of the track and in the direction of the grid, is numbered incrementally starting from 1.

```html
<div class="item" id="item1">1</div>
```

```css
#item1{
    grid-row-start: 1;
    grid-row-end: 3;
    grid-column-start:1;
    grid-column-end: 3;
}
```

```css
#item1{
	grid-row-start:2;
	grid-row-end:3;
	grid-column-start:2;
	grid-column-end:3;
}
```
This 2-column by 3-row grid results in 3 column lines and 4 row lines. Item 1 was repositioned by row and column line numbers.

```css
grid-row:2;
grid-column:3/4;
```
`grid-row/column` is shorthand for `grid-row/column-start` and `grid-row/column-end`.

If one value is provided, it specifies `grid-row/column-start`.
If two values are specified, the first value corresponds to `grid-row/column-start` and the second `grid-row/column-end`, and must be separated by a forward slash `/`.

**Naming and positioning items by grid areas**
Grid areas can also be named with the `grid-template-areas` property. Names can then be referenced to position grid items.
```html
<div class="wrapper">
	<div class="items" id="item1">1</div>
	<div class="items" id="item2">2</div>
	<div class="items">3</div>
	<div class="items">4</div>
	<div class="items">5</div>
	<div class="items">6</div>
</div>
```

```css
.wrapper{
    display:grid;
    grid-template-areas:
        "header header"
        "content sidebar"
        "footer footer";
    grid-template-rows: 150px 1fr 100px;
    grid-template-columns: 1fr 200px;
}
  
.items{
    background-color: purple;
    border:2px solid rgb(148, 148, 148);
    display:flex;
    justify-content: center;
    align-items: center;
}
  
#item1{
    grid-row-start: header;
    grid-row-end: header;
    grid-column-start: header;
    grid-column-end: header;
    background-color: red;
}

#item2{
    background-color: aqua;
    grid-row:content;
    grid-column:content;	
}
```
Sets of names should be surrounded in single or double quotes, and each name separated by a whitespace.
Each set of names defines a row, and each name defines a column.

Grid area names can be referenced by the same properties to position grid items: `grid-row-start`, `grid-row-end`, `grid-column-start`, and `grid-column-end`.