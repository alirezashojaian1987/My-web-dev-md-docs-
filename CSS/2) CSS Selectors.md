We can divide CSS selectors into five categories:

- Simple selectors (select elements based on name, id, class)
- Combinator selectors (select elements based on a specific relationship between them) 
- Psuedo-class selectors (select elements based on a certain state)
- Psuedo-elements selectors (select and style a part of an element)
- Attribute selectors (select elements based on an attribute or attribute value)
##### The CSS element selector
The element selector selects HTML elements based on the element name.
```CSS
p{
	text-align:center;
	color:red;
}
```
Here, all `<p>` elements on the page will be center-aligned, with a red text color.
##### The CSS id selector
The id selector uses the id attribute of an HTML element to select a specific element. The id of an element is unique within a page, so the id selector is used to select one unique element!
To select an element with a specific id, write a hash (#) character, followed by the id of the element.
```css
#para1{
	text-align:center;
	color:red;
}
```
*!Note:* An id name cannot start with a number.
##### The CSS class selector
The class selector selects HTML elements with a specific class attribute.
To select elements with a specific class, write a period (.) character, followed by the class name.
```css
.center{
	text-align:center;
	color:red;
}
```
You can also specify that only specific HTML elements should be affected by a class.
```css
p.center{
	text-align:center;
	color:red;
}
```
In the example above, only `<p>` elements with center class will be red and center-aligned.

HTML elements can also refer to more than one class.
```html
<p class="center large">This paragraph refers to two classes.</p>
```
##### The CSS universal selector
The universal selector( * ) selects all HTML elements on the page.
```css
*{
	text-align:center;
	color:blue;
}
```
##### The CSS grouping selector
```css
h1,h2,p{
	text-align:center;
	color:red;
}
```
