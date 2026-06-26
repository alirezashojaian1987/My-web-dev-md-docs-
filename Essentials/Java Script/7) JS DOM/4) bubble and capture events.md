```html
<body>
        <div id="parent" class="parent">
            this is parent element.
  
            <button id="child" class="child">Child button</button>
        </div>

        <script>
            const child=document.getElementById("child");
            const parent=document.getElementById("parent");

            parent.addEventListener("click",(event)=>{
                console.log("parent event");
            });
  
            child.addEventListener("click",(event)=>{
                console.log("Child event");
            });
        </script>
    </body>
```
In the code above whenever you press on the button, an action occurs on both elements, because the button is inside another element and also the div has it's own event. So both of them cause the action to happen, the parent element and the child element. This is called **bubble event

We can revert this behavior.
```js
parent.addEventListener("click",(event)=>{
	console.log("parent event");
},true);
```
This time, parent event is called first. This is called **capture event**.

##### How to only cause child's event
```js
child.addEventListener("click",(event)=>{
	event.stopPropagation();
	console.log("Child event");
});
```

##### Default behavior
```html
<body>
        <div id="parent" class="parent">
            this is parent element.
  
            <form id="myForm">
                <input type="text">
                <button id="child" class="child">Submit</button>
            </form>
        </div>

        <script>
            const parent=document.getElementById("parent");
            const child=document.getElementById("child");
            const form=document.getElementById("myForm");
  
            form.addEventListener("submit",(event)=>{
                console.log("form submit event");
            });
  
            child.addEventListener("click",(event)=>{
                console.log("Child event");
            });
        </script>
    </body>
```
Whenever you press on a button in a form, everything gets cleared, to avoid that, we can change element's default event:
```js
child.addEventListener("click",(event)=>{
	event.preventDefault();
	console.log("Child event");
});
```
Now if you press the button, the input doesn't get cleared.