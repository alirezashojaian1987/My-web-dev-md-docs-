As for styling in HTML, we use a separate file named CSS instead of using `<style>` tag in html doc. For JS we need to do this as well.
Just before the body end tag, use the `<script>` tag like this:
```html
<script src="./filename.js"></script>
```
We put the script there because when the HTML doc is read by browser line by line. If it reaches js file early, it may take a while to read it.
To avoid the problem above, you can use the `defer` attribute in the tag:
```html
<head>
	<link>
	<script defer src="./filename.js"></script>
</head>
```