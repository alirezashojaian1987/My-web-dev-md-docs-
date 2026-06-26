The HTML `<p>` elements defines a paragraph.
A paragraph always starts on a new line, and browsers automatically add some white space (a margin) before and after a paragraph.
```html
<p> This is a paragraph.</p>
<p> This is another paragraph </p>
```

*!Note:* With HTML, you cannot change the display by adding extra spaces or extra lines in your HTML code.
The browser will automatically remove any extra spaces and lines when the page is displayed:
```html
<p>  
This paragraph  
contains a lot of lines  
in the source code,  
but the browser  
ignores it.  
</p>  
  
<p>  
This paragraph  
contains         a lot of spaces  
in the source         code,  
but the        browser  
ignores it.  
</p>
```

##### HTML horizontal rules
The `<hr>` tag defines a thematic break in an HTML page, and is most often displayed as a horizontal rule.
```html
<h1>This is heading 1</h1>  
<p>This is some text.</p>  
<hr>  
<h2>This is heading 2</h2>  
<p>This is some other text.</p>  
<hr>
```

*!Note:* The `<hr>` tag is an empty tag, which means that it has no end tag.

##### HTML line breaks
The HTML `<br>` element defines a line break.
Use `<br>` if you want a line break (a new line) without starting a new paragraph:
```html
<p>This is <br> a paragraph<br>with line breaks.</p>
```
*!Note:* The `<br>` tag is an empty tag, which means that it has no end tag.

##### HTML `<pre>` element
The HTML `<pre>` element defines preformatted text.
The text inside a `<pre>` element is displayed in a fixed-width font (usually Courier), and it preserves both spaces and line breaks:
```html
<pre>  
  My Bonnie lies over the ocean.  
  
  My Bonnie lies over the sea.  
  
  My Bonnie lies over the ocean.  
  
  Oh, bring back my Bonnie to me.  
</pre>
```
