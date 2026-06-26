An HTML iframe is used to display a web page within a web page.
##### Iframe syntax
The HTML `<iframe>` tag specifies an inline frame.
An inline frame is used to embed another document within the current HTML document.
```html
<iframe src="_url_" title="_description_"></iframe>
```

Use the `height` and `width` attributes to specify the size of the iframe.
The height and width are specified in pixels by default:
```html
<iframe src="demo_iframe.htm" height="200" width="300" title="Iframe Example"></iframe>
```

##### Iframe - Remove the border
By default, an iframe has a border around it.
To remove the border, add the `style` attribute and use the CSS `border` property:
```html
<iframe src="demo_iframe.htm" style="border:none;" title="Iframe Example"></iframe>
```
With CSS, you can also change the size, style and color of the iframe's border.

