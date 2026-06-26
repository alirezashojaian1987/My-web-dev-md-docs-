`setTimeout` is a built-in method which allows you to run a specific function to run with delay:
```js
setTimeout(function(){
    console.log("Hello nigga");
},5000);
```
The code above allows us to run the function after 5 seconds. The method gets two arguments; one is function and the second one is the time(in milli-seconds). 

`setInterval` runs a code on an infinite loop with a delay.
```js
setInterval(function(){
    console.log("Hello nigga");
},2000);
```
The code above prints each 2 seconds.

*!Note:* You should be careful when using `setInterval` method.
To stop the loop, we can go with this approach:
```js
const interval=setInterval(function(){
    console.log("Hello nigga");
},2000);
  
setTimeout(()=>{
    clearInterval(interval);
},6000);
```
The code above will stop printing after 6 seconds.

*!Note:* Like method above, remember to always cleat timeout and Interval methods. Because it will consume more memory.