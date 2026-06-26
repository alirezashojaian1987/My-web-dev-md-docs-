`<DOM>` or (Document object model) is an object in web pages and you can work with HTML and CSS in the document. They are kinda parsed.
There is the `window` object, then the `document` object which is our DOM, after that is the html doc which is divided to 2 parts which are `head` and `body`.

When you open the browser, the whole page you see is called a **window object** or sometimes you call it the **root object**.
The part that we enter an address is called **location object**.

And when you open a webpage which is our final work's result, is called **DOM**.

To understand DOM more:
When you search for a webpage on your browser,(for example, Google.com), your request eventually reaches the server. At first, server send the HTML file of the web page for your browser. Your browser reads the HTML file and renders it till it reaches the `<link>` tag which will hold the CSS code and the CSS file will be sent for your browser. Finally the JS file and then the DOM will be created with these.

##### Open your browser console
Type `document`. You can see that when you hover on it, the whole page is hovered. It's like a tree with nodes. document is an object, you can type `document.` to see it's methods. 
*For example*:
```
document.write("Hello World")
```
It changes your whole DOM. There will be the massage above.

**Note:** Every tag in the HTML code is called an element. The content within the tags are called nodes. Even tags are nodes too. Well kinda..