The HTML `<head>` element is a container for the following elements: `<title>`, `<style>`, `<meta>`, `<link>`, `<script>`, and `<base>`.

The `<head>` element is a container for metadata (data about data) and is placed between the `<html>` tag and the `<body>` tag.
HTML metadata is data about the HTML document. Metadata is not displayed on the page.
Metadata typically define the document title, character set, styles, scripts, and other meta information.

##### The HTML `<title>` element
The `<title>` element defines the title of the document. The title must be text-only, and it is shown in the browser's title bar or in the page's tab.
The `<title>` element is required in HTML documents!

The content of a page title is very important for search engine optimization (SEO)! The page title is used by search engine algorithms to decide the order when listing pages in search results.
The `<title>` element:
- defines a title in the browser toolbar
- provides a title for the page when it is added to favorites
- displays a title for the page in search engine-results

##### `<meta>` element
The `<meta>` element is typically used to specify the character set, page description, keywords, author of the document, and viewport settings.

The metadata will not be displayed on the page, but is used by browsers (how to display content or reload page), by search engines (keywords), and other web services.

Define the character set used:
```html
<meta charset="UTF-8">
```

Define keywords for search engines:
```html
<meta name="keywords" content="HTML, CSS, JavaScript">
```

Define a description of your web page:
```html
<meta name="description" content="Free Web tutorials">
```

Define the author of a page:
```html
<meta name="author" content="John Doe">
```

Refresh doc every 30 secs:
```html
<meta http-equiv="refresh" content="30">
```

Setting the viewport to make your website look good on all devices:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

##### `<base>` element
The `<base>` element specifies the base URL and/or target for all relative URLs in a page.
The `<base>` tag must have either an href or a target attribute present, or both.
There can only be one single `<base>` element in a document!
```html
<head>  
<base href="https://www.w3schools.com/" target="_blank">  
</head>  
  
<body>  
<img src="images/stickman.gif" width="24" height="39" alt="Stickman">  
<a href="tags/tag_base.asp">HTML base Tag</a>  
</body>
```