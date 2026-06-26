A JavaScript event is **a specific action that occurs within a web page or application**, such as clicking on an element, moving the mouse, pressing a key, or loading a page.

```html
<body>
        <h1>Top 10 shitiest cars in the world in 2025</h1>
  
        <button>Click here</button>
  
        <ul id="myList">
            <li>pride</li>
            <li>tiba</li>
            <li>quick</li>
            <li>Nissan</li>
            <li>Kia</li>
            <li>shahin</li>
            <li>peykan</li>
            <li>MVM 110</li>
            <li>Peugeot RD</li>
        </ul>
  
        <h2>What is the ugliest car?</h2>
        <p>Probabelythe MVM110 is the ugliest due to it's shape being like a frog</p>
  
        <script>
           const button_list=document.getElementsByTagName("button");
            button_list[0].addEventListener("click",()=>{
                alert("You clicked the button");
            })
        </script>
    </body>
```
There are many more events. `addEventListener` performs an action for us, gets 2 arguments, first is the action we do, second one is a function. `alert()` method shows a massage after we do the action.

##### Adding content to our list
First we need to select it:
```html
<script>
           const button_list=document.getElementsByTagName("button");
            const list_items=document.getElementById("myList");
            const newLi=document.createElement("li");
            newLi.textContent="PK";
  
            button_list[0].addEventListener("click",()=>{
                list_items.appendChild(newLi);
            });
        </script>
```
or if you wanna add as many times as you want:
```html
<script>
            const button_list=document.getElementsByTagName("button");
            const list_items=document.getElementById("myList");
            console.log(list_items);
            
  
            button_list[0].addEventListener("click",()=>{
                const newLi=document.createElement("li");
	            newLi.textContent="PK";
	            list_items.appendChild(newLi);
            });
        </script>
```
**mouse actions**
In the example above if you use `mouseenter` instead of click, whenever you hover your mouse on the button, action happens. `mouseleave` causes action if you put away your mouse on the button, after hovering it.

You can use `mouseup` and `mousedown` as well. They are for holding the click.

##### Working with `<input>`
```html
<input id="myInput" type="text">
```
```js
const input=document.getElementById("myInput");
input.addEventListener("keypress",()=>{
	console.log("Key got pressed.");
});
```
Based on the code above if you check the browser console, you can see the massage is shown whenever you press on your keyboard.

```js
const input=document.getElementById("myInput");
input.addEventListener("keypress",(event)=>{
	console.log(event);
});
```
Code above returns event when a key is pressed. It shows an object, the key name pressed, the code of the key pressed and etc.

There is a target object that shows what element you used, here is input.
```js
const input=document.getElementById("myInput");
input.addEventListener("keypress",(event)=>{
	console.log(event.target.value);
});
```
It shows everything you typed in the input section. This is how you can access your input value.

##### Adding elements to a list, using input and button actions
```html
<h1>Top 10 shitiest cars in the world in 2025</h1>
       <input id="myInput" type="text" placeholder="List item name">
        <button id="btn">Add to list</button>
  
        <ul id="myList">
            <li>pride</li>
            <li>tiba</li>
            <li>quick</li>
            <li>Nissan</li>
            <li>Kia</li>
            <li>shahin</li>
            <li>peykan</li>
            <li>MVM 110</li>
            <li>Peugeot RD</li>
        </ul>
  
        <h2>What is the ugliest car?</h2>
        <p>Probabely the MVM110 is the ugliest due to it's shape being like a frog</p>
  
        <script>
            const button=document.getElementById("btn");
            const input=document.getElementById("myInput");
            const list=document.getElementById("myList");
  
            button.addEventListener("click",()=>{
                const newLi=document.createElement("li");
                newLi.textContent=input.value;
                list.appendChild(newLi);
            })
        </script>
```

##### remove listeners
When you created a listener, until the web page is on, the listener is active as well, sometimes you don't need it. 
```js
element.removeEventLiswtener("attribute");
```
*!Note:* Remember to put the exact event (and function if defined) you defined for the element.