##### JS Promises
**Promise** represent a value that may be available now, later or never.
The **Promise Object** represents the completion or failure of an asynchronous operation and its results.
A promise can have 3 states:
1. pending: initial state
2. rejected: operation failed
3. fulfilled: operation completed

##### Why promises?
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
##### Promise states
A promise can be in one of three exclusive states:
- **Pending:**  
    The initial state; the operation has started but is neither fulfilled nor rejected.
- **Fulfilled:**  
    The operation completed successfully, and a value is available.
- **Rejected:**  
    The operation failed, and a reason (error) is available.
A promise is considered **settled** if it is fulfilled or rejected (not pending).
##### Creating a promise
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
##### Promise how to
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
##### Promise object properties
A Js promise object can be:
+ Pending: undefined
+ Fulfilled: a result value
+ rejected: an error object
##### Core methods and usage
Promises consumed using methods attached to the promise object:
- **.then(onFulfilled, onRejected):**  
    This method attaches handlers for both the fulfillment and rejection cases. It returns a new promise, which enables method chaining.
    
- **.catch(onRejected):**  
    This is a shorthand for .then(null, onRejected) and is typically used to handle errors at the end of a promise chain.
    
- **.finally(onFinally):**  
    This handler is called when the promise is settled (either fulfilled or rejected), regardless of the outcome. It's useful for cleanup operations.
##### Using then and catch
You do not read a promise result immediately.
You attach code that runs when the promise finishes.
`then()` runs when a promise is fulfilled and the `catch()` for the rejected.
```js
let myPromise=new Promise(function(resolve,reject){
  let ok=false;
  
  if(ok)
    resolve("It's aight nigga, we cool");
  else
    reject("Fuck you nigga, we not cool");
})
  
myPromise.then(
  function(value){console.log(value);},
).catch(function(value){console.log(value)});
```
##### Returning a promise
Promises become powerful when you return a promise from `then()`.
This creates a clean chain
```js
function step1(){
  return Promise.resolve("Nigga1");
}
function step2(value){
  return Promise.resolve(value+" Nigga2");
}
function step3(value){
  return Promise.resolve(value+" Nigga3")
}
  
step1()
.then(function(value){
  return step2(value);
})
.then(function(value){
  return step3(value);
})
.then(function(value){
  return console.log(value);
});
```
##### Promises and real JS
Many web APIs return promises.
`fetch()` is a common example:
```js
fetch("data.json")
.then(function(response){
	return response.json();
})
.then(function(data){
	console.log(data);
})
.catch(function(error){
	console.log(error);
});
```


##### Bootcamp's promise explanation
Here another way on how to use a Promise:
Syntax:
```js
//defining a promise
const myPromise=new Promise((resolve,reject)=>{
    if(true){
        resolve("Operation successful");
    }
  
    else{
        reject("Operation failed.");
    }
});
  
//Consuming the promise
myPromise
    .then((result)=>{
        console.log(result);
    })
    .then...//other operation(steps)
    .catch((error)=>{
        console.error(error);
    });
```
When the producing code obtains the result, it should call one of the two callbacks.
*Examples:*
```js
//A simple promise use
const getUser=new Promise((resolve,reject)=>{
    let success=true;
    if(success){
        setTimeout(()=>resolve("Data fetched"),1000);
    }
    else{
        setTimeout(()=>reject("Error"),1000);
    }
});
  
getUser.then((result)=>{
    console.log(result);
});
```

```js
//setting steps after defining a promise
const getUser=new Promise((resolve,reject)=>{
    let success=true;
    if(success){
        setTimeout(()=>resolve("Data fetched"),1000);
    }
    else{
        setTimeout(()=>reject("Error"),1000);
    }
});

getUser.then((result)=>{
    console.log(result);
    return result;
}).then((data)=>{
    console.log(data);
    return data+"?!";
}).then((data)=>{
    console.log(data);
}).catch((error)=>{
    console.log(error+"!!!");
});
```
*!Note:* Remember that to put the catch in the end, cause if you use a then after it, it has an undefined data.

**Real example:**
You can use json placeholder web site for practicing requests.
```js
const urls=[
    "https://jsonplaceholder.typicode.com/posts",
    "https://jsonplaceholder.typicode.com/photos",
    "https://jsonplaceholder.typicode.com/users",
];

Promise.all(urls.map((url)=>{
    return fetch(url).then(response=>response.json()).then((data)=>{
        console.log(data);
    })
})).catch((error)=>{
    console.log("Error",error);
});
```

Sometimes you want to get the faster promise result, here you can use the `Promise.race()` method. 
```js
let slowPromise=new Promise((resolve)=>{
    setTimeout(()=>resolve("Slow promise"),2000);
});
  
let fastPromise=new Promise((resolve)=>{
    setTimeout(()=>resolve("Fast promise"),1000);
});
  
Promise.race([fastPromise,slowPromise])
    .then((result)=>{
        console.log(result);
    })
    .catch((error)=>console.log(error));
```

When you have multiple promises and you wanna save their results, whether they are resolved or rejected, you can use the `allSettled` method:
```js
const promise1=new Promise((resolve)=>{
    setTimeout(()=>resolve("promise"),2000);
});

const promise2=new Promise((resolve)=>{
    setTimeout(()=>resolve("promise2"),1000);
});
  
const promise3=new Promise((reject)=>{
    setTimeout(()=>reject("rejected!"),1000);
});
  
Promise.allSettled([promise1,promise2,promise3])
    .then((results)=>{
        console.log(results);
    })
    .catch((error)=>console.log(error));
```

```js
fetch("https://api.example.com")
	.then(response=>respone.json())
	.then(data=>console.log(data))
	.catch(error=>console.error(error));
```