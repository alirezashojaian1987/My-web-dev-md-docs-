HTML attributes provide additional information about HTML elements.
- All HTML elements can have **attributes**
- Attributes provide **additional information** about elements
- Attributes are always specified in **the start tag**
- Attributes usually come in name/value pairs like: **name="value"**

For example, we've seen The `<a>` tag, which defines a hyperlink. The `href` attribute specifies the URL of the page the link goes to.

##### src attribute
The `<img>` tag is used to embed an image in an HTML page. The `src` attribute specifies the path to the image to be displayed:
```html
<img src="img_girl.jpg">
```

##### The width and height attributes
The `<img>` tag should also contain the `width` and `height` attributes, which specify the width and height of the image (in pixels):
```html
<img src="img_girl.jpg" width="500" height="600">
```

##### Style attribute
The `style` attribute is used to add styles to an element, such as color, font, size, and more.
```html
<p style="color:red;">This is a red paragraph.</p>
```

##### The lang attribute
You should always include the `lang` attribute inside the `<html>` tag, to declare the language of the Web page. This is meant to assist search engines and browsers.
```html
<!DOCTYPE html>  
<html lang="en">  
<body>  
...  
</body>  
</html>
```

##### The title attribute
The `title` attribute defines some extra information about an element.
The value of the title attribute will be displayed as a tooltip when you mouse over the element:
```html
<p title="I'm a tooltip">This is a paragraph.</p>
```

