##### getElementById
As you remember that you could assign an Id for only one element, we can use this selector on web console or IDE.
```js
document.getElementById("idname")
```
It returns it for you.

##### getElementsByTagName
It returns all the elements by their name.
```js
document.getElementsByTagName("tag")
```

##### getElementsByClassName
Like id, it returns the elements with the same class attribute.
```js
document.getElementsByClassName("classname")
```

##### querySelector
It returns the first occurrence of requested element.
```js
document.querySelector("tag")
```
And if you want all of them, you can use `querySelectorAll()`. 

##### setAttribute
You can set an specified attribute for an element.
```js
document.getElementById("Idname").setAttribute("class","New_className")
```
First argument is the attribute you wanna set and the second one is the value for it.
*!Note:* Remember that if you use this selector and the element has already contained a class, it overrides it. 
You can use this method instead:
```js
element.classList.add("className")
```
You can use `remove()` too.

##### get & remove attribute
```js
element.getAttribute("class") //classname
element.removeAttribute("class")
```

##### Changing contents
```js
const h1=document.getElementsByTagName("h1")
h1[0].innerHTML="<span>Hellooooo!!!</span>
h1[0].textContent="Hello"
```
InnerHtml adds tags and contents, on the other hand textContent changes the content.
Both of them override the contents.

##### element.style

##### Create elements
```js
const new_tag=document.createElement("tagName");
```

*Example:*
```js
const newLi=document.createElement("li");
newLi.textContent="PK";
myList.appendChild(newLi);
```

**removeChild**
```js
const list=document.getElementByTagName("li");
myList.removeChild(list[0]);
```
*!Note:* Remember that you should select the element first!