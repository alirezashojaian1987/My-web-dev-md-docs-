##### `<code>` for computer code
The HTML `<code>` element  is used to define a piece of computer code. The content inside is displayed in the browser's default monospace font.
```html
<pre>  
<code>  
x = 5;  
y = 6;  
z = x + y;  
</code>  
</pre>
```
*!Note:* Notice that the `<code>` element does NOT preserve extra whitespace and line-breaks.
To preserve extra whitespace and line-breaks, you can put the `<code>` element inside a `<pre>` element
##### `<samp>` for program output
The HTML `<samp>` element is used to define sample output from a computer program. The content inside is displayed in the browser's default monospace font.
```html
<p>Message from my computer:</p>  
<p><samp>File not found.<br>Press F1 to continue</samp></p>
```
##### `<kbd>` for keyboard input
The HTML `<kbd>` element is used to define keyboard input. The content inside is displayed in the browser's default monospace font.
```html
<p>Save the document by pressing <kbd>Ctrl + S</kbd></p>
```

##### `<var>` for variables
The HTML `<var>` element  is used to define a variable in programming or in a mathematical expression. The content inside is typically displayed in italic.
```html
<p>The area of a triangle is: 1/2 x <var>b</var> x <var>h</var>, where <var>b</var> is the base, and <var>h</var> is the vertical height.</p>
```

