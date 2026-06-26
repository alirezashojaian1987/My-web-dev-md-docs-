##### Asynchronus flow
JS **Asynchronus Flow** refers to how JS handles tasks that take time to complete, like reading files, or waiting for user input, without blocking the execution of other code.
To prevent blocking, JS can use **asynchronous programming**.
This allows certain operations to run in the background, and their results are handled later, when they are ready.

Asynchronus patterns
+ Events
+ Callbacks
+ Promises
+ Async / Await
##### Control flow
**Control flow** is the order in which statements are executed in a program. By default, Js runs code **from top to bottom** and left to right. **Async programming** can change this.
##### How Js runs code
Js executes code one line at a time.
Each line must finish before the next line runs.

**Function sequence**
Js functions are executed in the sequence they are called, not in the sequence they are defined.
##### Why Async code
Some tasks take time to finish(network requests, timers, user input).
Asynchronous flow refers to how Js allows certain ops to run in the background and let their results be handled when they are ready.

If Js waited for these tasks, the page would freeze.
Async code lets the rest of the program continue to run.
Async code does not run immediately:
**Timers** run after a specified number of milliseconds.
**Events** run when triggered by an event.
**Network requests** run when the data arrives.
```js
function print(str){
    console.log(str);
}
  
print("A");
  
setTimeout(function(){
  print("B");
},2000);
  
print("C");
//A C B
```
###### JS Events
Events are actions that happen in the browser, often triggered by user interactions(like clicks, keypresses or form submissions) or by the browser itself(like page loading or resizing).
*Example:*
```html
<body>
        <p>Click the button to display the date</p>
        <button onclick="displayDate()">The time is:</button>
</body>
  
    <script>
        function displayDate(){
          document.getElementById("demo").innerHTML=Date();
        }
    </script>
    <p id="demo"></p>
```
##### Asynchronous concepts

| Concept     | Description                                            |
| ----------- | ------------------------------------------------------ |
| Synchronus  | The JavaScript standard flow is executing line by line |
| Timers      | Allows code to run while other code is waiting         |
| Callbacks   | Callbacks were the first solution for async JavaScript |
| Events      | Stores callback function waiting to be executed        |
| Promises    | Tools to handle asynchronous operations cleanly        |
| Async/Await | The clean and modern way to handle async code          |
##### Async vs parallel
Parallel means doing multiple things at the same time on different processors.

Asynchronous means switching between tasks, not necessarily running them simultaneously.
In short, asynchronous tells the system:
1. Start this task now.
2. I don't need the result immediately.
3. Notify me later when it's done.
##### JS callbacks
A **callback** is a function that is passed as an argument to another function, and is intended to be executed at a later point in time, typically when a specific event occurs or an asynchronous operation completes.

**Event handling**
Callbacks are often used in Js, specially in event handling.
User interactions, such as button clicks or key presses, can be handled by providing a **callback function** to an **event listener**.
```html
<body>
        <h1>JavaScript HTML Events</h1>
        <h2>Event Handlers</h2>
  
        <button id="myButton">The time is?</button>
  
        <p id="demo"></p>

  
        <script>
            function displayDate(){
                document.getElementById("demo").innerHTML = Date();
            }
  
                document.getElementById("myButton").addEventListener("click", displayDate);
            </script>
  
    </body>
```
In the example above, `displayDate` is a callback function passed as an argument to the `addEventListener()` method.
`displayDate` will be called when a user clicks the button with `id="myButton"`.

In the example below, `myDisplayer` is called a callback function.
It is passed to `myCalculator()` as an argument.
```html
<body>

	<p>The result of the calculation is:</p>
	<p id="demo"></p>

	<script>
		function myDisplayer(something){
		document.getElementById("demo").innerHTML=something;
		}

		function myCalculator(num1,num2,myCallback){
			let sum=num1+num2;
			myCallback(sum);
		}

		myCalculator(5,5,myDisplayer);
	</script>
</body>
```

**The timing problem**
Async code finishes later.
This means you cannot return the result right away(before they are finished).
```js
let result;
  
setTimeout(function() {
  result = 5;
}, 1000);
  
console.log(result); //undefined
```
The result is `undefined` because the async code has not finished yet.

*!Note:* You cannot solve this problem by waiting in JavaScript. Waiting would freeze the page.

**The Call back idea**
The solution is to run the code after the result is ready.
You must give JavaScript a **callback function** to call later.
A callback is a function passed as an argument to another function.
This technique allows a function to call another function.
```js
function done(value) {
  console.log(value);
}
  
setTimeout(function() {
  done(5);
}, 1000);
```
##### Waiting for a Timeout
**The setTimeout() method** schedules a function to **run after a delay** in milliseconds.
It is an **async operation** used to delay code execution without freezing the browser.

When using the JS `setTimeout()`, you can specify a callback function to be executed on time-out:
```js
setTimeout(myFunction,3000);

function myFunction(){
	console.log("Hello world");
}
```
In the example above, `myFunction` is used as a callback.
`myFunction` is passed to `setTimeout()` as an argument.
##### Waiting for Intervals
When using the JS `setInterval()`, you can specify a callback function to be executed for each interval.
```js
setInterval(myFunction,2000);
  
function myFunction(){
    let d=new Date();
  consle.log(d.getHours()+":"+d.getMinutes()+":"+d.getSeconds());
}
```
In the example above, `myFunction` is used as a callback.
`myFunction` is passed to `setInterval()` as an argument.

##### Callback alternatives
With asynchronous programming, JavaScript programs can start long-running tasks, and continue running other tasks in parallel.
But, asynchronus programs are difficult to write and difficult to debug.
Because of this, most modern asynchronous JavaScript methods don't use callbacks. Instead, in JavaScript, asynchronous programming is solved using **Promises**, **async/await** instead.
##### JS Promises
**Promise** represent a value that may be available now, later or never.
The **Promise Object** represents the completion or failure of an asynchronous operation and its results.
A promise can have 3 states:
1. pending: initial state
2. rejected: operation failed
3. fulfilled: operation completed

###### Why promises?
Many callbacks become hard to read and hard to maintain.
```js
step1(function(r1) {  
  step2(r1, function(r2) {  
    step3(r2, function(r3) {  
      console.log(r3);  
    });  
  });  
});
```
The style above is often called **Callback hell**
Promises let you write the same logic in a cleaner way.

A Promise acts as a placeholder for a value that will be available at some point in the future, allowing you to handle asynchronous code in a cleaner way than traditional callbacks.
###### Promise states
A promise can be in one of three exclusive states:
- **Pending:**  
    The initial state; the operation has started but is neither fulfilled nor rejected.
- **Fulfilled:**  
    The operation completed successfully, and a value is available.
- **Rejected:**  
    The operation failed, and a reason (error) is available.
A promise is considered **settled** if it is fulfilled or rejected (not pending).
###### Creating a promise
`syntax`
```js
let myPromise=new Promise(function(resolve,reject)){
	resolve(value); //When successful
	reject(value); //when error
}
```
The promise constructor takes a function with two parameters:
`resolve:` Function to run if finishes successfully.
`reject:` Function to run if it finishes with an error.
###### Promise how to
Here is how to use a promise:
```js
myPromise.then(
	function(value){/* code if successful */},
	function(value){/* Code if error */}
);
```
*Note:* `then()` takes two args, one `callback` function for success and another for failure. Both are optional, so you can add a callback for success or failure only.
```js
let myPromise=new Promise(function(resolve,reject){
  let ok=true;
  
  //producing code(may take some time)
  if(ok)
    resolve("It's aight nigga, we cool");
  else
    reject("Fuck you nigga, we're not cool");
})

//Consuming code(must wait for a fulfilled promise)
myPromise.then(
  function(value){console.log(value);},
  function(value){console.log(value);}
);
```
*Note:* A promise can resolve or reject **only once**.

##### JS Async / Await
**Async/Await** is a modern, cleaner way to handle asynchronous code.
It makes asynchronous code look synchronous and easier to read. Await keyword means that while the operation has not finished yet, other operations should wait.
Remember we can't have catch here, so you need to use `try-catch` method.
```js
async function getData() {  
  try {  
    const res = await fetch("https://api.example.com");  
    const data = await res.json();  
    console.log(data);  
  } catch (err){
  console.error(err);  
  }
}
```

```js
const getData=()=>{
  fetch("https://jsonplaceholder.typicode.com/posts").then((response)=>{
        return response.json();
    })
    .then((data)=>console.log(data))
    .catch((error)=>console.log(error));
};
  
getData();

//async function newGetData(){}
  
const newGetData=async()=>{
    try{
        const response=await fetch("https://jsonplaceholder.typicode.com/posts");
        const data=await response.json();
        console.log(data);
    }
    catch(error){
        console.log(error);
    }
}

newGetData();
```