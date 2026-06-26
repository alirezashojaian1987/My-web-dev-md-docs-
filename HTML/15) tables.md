HTML tables allow web developers to arrange data into rows and columns.
#### Tables
##### Define an HTML table
```html
<table>  
  <tr>  
    <th>Company</th>  
    <th>Contact</th>  
    <th>Country</th>  
  </tr>  
  <tr>  
    <td>Alfreds Futterkiste</td>  
    <td>Maria Anders</td>  
    <td>Germany</td>  
  </tr>  
  <tr>  
    <td>Centro comercial Moctezuma</td>  
    <td>Francisco Chang</td>  
    <td>Mexico</td>  
  </tr>  
</table>
```

##### Table cells
Each table cell is defined by a `<td` and a `</td>` tag.
td stands for table data.
```html
<table>  
  <tr>  
    <td>Emil</td>  
    <td>Tobias</td>  
    <td>Linus</td>  
  </tr>  
</table>
```

*Note:* A table cell can contain all sorts of HTML elements: text, images, lists, links, other tables, etc.

##### Table rows
Each table row starts with a `<tr>` and ends with a `</tr>` tag. `tr` stands for table row.
```html
<table>  
  <tr>  
    <td>Emil</td>  
    <td>Tobias</td>  
    <td>Linus</td>  
  </tr>  
  <tr>  
    <td>16</td>  
    <td>14</td>  
    <td>10</td>  
  </tr>  
</table>
```

##### Table headers
`th` stands for table header.
```html
<table>  
  <tr>  
    <th>Person 1</th>  
    <th>Person 2</th>  
    <th>Person 3</th>  
  </tr>  
  <tr>  
    <td>Emil</td>  
    <td>Tobias</td>  
    <td>Linus</td>  
  </tr>  
  <tr>  
    <td>16</td>  
    <td>14</td>  
    <td>10</td>  
  </tr>  
</table>
```
By default, the text in `<th>` elements are bold and centered, but you can change that with CSS.

##### HTML `<caption>` tag
The `<caption>` tag defines a table caption.
The `<caption>` tag must be inserted immediately after the `<table>` tag.
```html
<table>  
  <caption>Monthly savings</caption>  
  <tr>  
    <th>Month</th>  
    <th>Savings</th>  
  </tr>  
  <tr>  
    <td>January</td>  
    <td>$100</td>  
  </tr>  
</table>
```

##### HTML `<colgroup>` tag
The `<colgroup>` tag specifies a group of one or more columns in a table for formatting.
```html
<table>  
  <colgroup>  
    <col span="2" style="background-color:red">  
    <col style="background-color:yellow">  
  </colgroup>  
  <tr>  
    <th>ISBN</th>  
    <th>Title</th>  
    <th>Price</th>  
  </tr>  
  <tr>  
    <td>3476896</td>  
    <td>My first HTML</td>  
    <td>$53</td>  
  </tr>  
</table>
```

##### HTML `<thead>, <tbody>, <tfoot>` tag
```html
<table>  
  <thead>  
    <tr>  
      <th>Month</th>  
      <th>Savings</th>  
    </tr>  
  </thead>  
  <tbody>  
    <tr>  
      <td>January</td>  
      <td>$100</td>  
    </tr>  
    <tr>  
      <td>February</td>  
      <td>$80</td>  
    </tr>  
  </tbody>  
  <tfoot>  
    <tr>  
      <td>Sum</td>  
      <td>$180</td>  
    </tr>  
  </tfoot>  
</table>
```

#### Table borders
HTML tables can have borders of different styles and shapes.
##### How to add border
To add a border, use the CSS `border` property on `table`, `th`, and `td` elements:
```css
table,th,td{
border: 1px solid black;
}
```

*!Note:* To avoid having double borders like in the example above, set the CSS `border-collapse` property to `collapse`.
```css
table,th,td{
border:1px solid black;  
border-collapse: collapse;
}
```

##### Style table borders
If you set a background color of each cell, and give the border a white color(the same as the document background), you get the impression of an invisible border:
```css
table,th,td{
border:1px solid white;  
border-collapse:collapse;
}
  
th,td{
background-color:#96D4D4;
}
```

##### Round table borders
With the `border-radius` property, the borders get rounded corners:
```css
table,th,td{
border:1px solid black;  
border-radius:10px;
}
```

##### Dotted table borders
With the `border-style` property, you can set the appearance of the border.
The following values are allowed:
+ dotted
+ dashed
+ solid
+ double
+ groove
+ ridge
+ inset
+ outset
+ none
+ hidden
```css
th,td{
	border-style:dotted;
}
```

##### Border color:
```css
th,td{
	border-color:red;
}
```

#### Table sizes
HTML tables can have different sizes for each column, row or the entire table.
Use the `style` attribute with the `width` or `height` properties to specify the size of a table, row or column.

##### Table width
```html
<table style="width:100%">  
  <tr>  
    <th>Firstname</th>  
    <th>Lastname</th>  
    <th>Age</th>  
  </tr>  
  <tr>  
    <td>Jill</td>  
    <td>Smith</td>  
    <td>50</td>  
  </tr>  
  <tr>  
    <td>Eve</td>  
    <td>Jackson</td>  
    <td>94</td>  
  </tr>  
</table>
```
*Note:* Using a percentage as the size unit for a width means how wide will this element be compared to its parent element, which in this case is the `<body>` element.

##### Table column width
```html
<table style="width:100%">  
  <tr>  
    <th style="width:70%">Firstname</th>  
    <th>Lastname</th>  
    <th>Age</th>  
  </tr>  
  <tr>  
    <td>Jill</td>  
    <td>Smith</td>  
    <td>50</td>  
  </tr>  
  <tr>  
    <td>Eve</td>  
    <td>Jackson</td>  
    <td>94</td>  
  </tr>  
</table>
```

##### Table row height
```html
<table style="width:100%">  
  <tr>  
    <th>Firstname</th>  
    <th>Lastname</th>  
    <th>Age</th>  
  </tr>  
  <tr style="height:200px">  
    <td>Jill</td>  
    <td>Smith</td>  
    <td>50</td>  
  </tr>  
  <tr>  
    <td>Eve</td>  
    <td>Jackson</td>  
    <td>94</td>  
  </tr>  
</table>
```

#### Table headers
HTML tables can have headers for each column or row.
Table headers are defined with `th` elements. Each `th` element represents a table cell.

##### Vertical table headers
To use the first column as table headers, define the first cell in each row as a `<th>` element.
```html
<table>  
  <tr>  
    <th>Firstname</th>  
    <td>Jill</td>  
    <td>Eve</td>  
  </tr>  
  <tr>  
    <th>Lastname</th>  
    <td>Smith</td>  
    <td>Jackson</td>  
  </tr>  
  <tr>  
    <th>Age</th>  
    <td>94</td>  
    <td>50</td>  
  </tr>  
</table>
```

##### Align table headers
By default, table headers are bold and centered.
```css
th{
	text-align:left;
}
```

##### Header for multiple columns
You can have a header that spans over two or more columns.
To do this, use the `colspan` attribute on the `<th>` element:
```html
<table>  
  <tr>  
    <th colspan="2">Name</th>  
    <th>Age</th>  
  </tr>  
  <tr>  
    <td>Jill</td>  
    <td>Smith</td>  
    <td>50</td>  
  </tr>  
  <tr>  
    <td>Eve</td>  
    <td>Jackson</td>  
    <td>94</td>  
  </tr>  
</table>
```

##### Table caption
use `<caption>` tag to add a caption to a table.

#### Table padding & spacing
HTML tables can adjust the padding inside the cells, and also the space between the cells. 
##### Cell padding
Cell padding is the space between the cell edges and the cell content.
By default the padding is set to 0.
To add padding on table cells, use the CSS `padding` property:
```css
th,td{
	padding: 15px;
}
```
U can add padding to only specific sides as well:
```css
th,td{
	padding-top:10px;
	padding-bottom:20px;
	padding-left:30px;
	padding-right:40px;
}
```

##### Cell spacing
Cell spacing is the space between each cell.
By default the space is set to 2 pixels.
To change the space between table cells, use the CSS `border-spacing` property on the `table` element:
```css
table{
	border-spacing:30px;
}
```

#### Table colspan & rowspan
HTML tables can have cells that span over multiple rows & columns

##### Colspan
To make a cell span over multiple columns, use the `colspan` attribute:
```html
<table>  
  <tr>  
    <th colspan="2">Name</th>  
    <th>Age</th>  
  </tr>  
  <tr>  
    <td>Jill</td>  
    <td>Smith</td>  
    <td>43</td>  
  </tr>  
  <tr>  
    <td>Eve</td>  
    <td>Jackson</td>  
    <td>57</td>  
  </tr>  
</table>
```

##### Rowspan
To make a cell span over multiple rows, use the `rowspan` attribute:
```html
<table>  
  <tr>  
    <th>Name</th>  
    <td>Jill</td>  
  </tr>  
  <tr>  
    <th rowspan="2">Phone</th>  
    <td>555-1234</td>  
  </tr>  
  <tr>  
    <td>555-8745</td>  
</tr>  
</table>
```

#### Table styling
##### Zebra stripes
If you add a background color on every other table row, you will get a nice zebra stripes effect. To style every other table row element, use the `:nth-child(even/odd)` selector like this:
```css
tr:nth-child(even){
	background-color:blue;
}
```

```css
td:nth-child(even),th:nth-child(even){
	background-color:blue;
}
```

##### Horizontal dividers
If you specify borders only at the bottom of each table row, you will have a table with horizontal dividers.

Add the `border-bottom` property to all `tr` elements to get horizontal dividers:
```css
tr{
	border-bottom:1px solid black;
}
```

##### Hoverable table
Use the `:hover` selector on `tr` to highlight table rows on mouse over:
```css
tr:hover{
	background-color:green;
}
```

#### Colgroup
