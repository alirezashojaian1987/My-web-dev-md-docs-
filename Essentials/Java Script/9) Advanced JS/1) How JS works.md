When you want to run your code in JS, there are 4 environments which will recognize the code first, then will execute it:
1. call stack FILO(First in Last out)
2. Web API
3. Callback
4. Event Loop
```js
console.log("Hi");

setTimeout(()=>{
	console.log("Hello");
},100);

console.log("World");
```
In call stack, JS reads the code line by line and puts it in call stack, executes it and then puts another one. There are some methods that are for Web API, such as here is the `setTimeout()` function. In this program, the first console log goes to call stack, the function goes into the web api until it's timer runs out. Then it goes to call back as a normal function. Event loop checks whether the call stack is empty or not. If it is, it takes the function out of call back and puts it in call stack. 
You can check what happens in this site: **JEloop Visualizer**