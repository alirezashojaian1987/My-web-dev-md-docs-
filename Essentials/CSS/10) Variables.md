The **var()** function is used to insert the value of a CSS variable. CSS variables have access to the DOM, which means that you can create variables with local or global scope, change the variables with JavaScript, and change the variables based on media queries.

**Declaring a variable:**
CSS variables can have a global or local scope.
Global variables can be accessed through the entire document, while local variables can be used only inside the selector where it is declared.

To create a global variable, declare it inside the `:root` selector. The `:root` selector matches the document's root element.

To create a local variable, declare it inside the selector that is going to use it.
A CSS variable name must begin with two dashes (--) and is case sensitive!

**Syntax**
```css
:root{
	--primary_color:green; /*can be rgb,hex,colorname,...*/
}

.container{
	background-color:var(--primary_color);
}
```