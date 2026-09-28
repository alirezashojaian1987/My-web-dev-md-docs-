Functions are **reusable block of code** designed to perform a particular task.
Functions **are executed** when they are "**called**" or "**invoked**".
```syntax
function function_name(arguments //or no args){
	//lines of code
}
```

```js
function sum(n1,n2){
	return n1+n2;
}

console.log(sum(2,3));
```
##### Scope
```js
const a=10;
console.log(a);
```
Obviously it prints the 10, now:
```js
const a=10;
function test(){
    const b=10;
}
console.log(b);
```
Will result in an error that the b is not defined. That's because it's not in the global scope.
```js
const a=10;

function test(){
    const b=100;
    console.log(a);
}

test();
```
The console will print the `a`. because it's defined in the global scope.
In other words: when on a scope(like inside a function), it can access the parent scope(which here is the global scope).

Let's go with another example:
```js
function test(){
    const b=100;
    if(b>100){
        const c=101;
        console.log(b);
    }
    console.log(c);
}
test();
```
Which will result in: `ReferenceError: c is not defined`
Here, in the `if` scope as you see we can access the `b` but in the outer layer, we can't access the `c` parameter in the function scope.

Now what if we have two parameters with the same name but in different scopes:
```js
const a=10;

function test(){
	const a=100;
	console.log(a);
}

test(); //100
console.log(a); //10
```
What happened here is that inside the function scope, the nearest parameter with the `a` name was considered.
##### Function declaration and hoisting
There are 2 ways to declare a function, first one as we mentioned before is by using the `function` keyword. 
The other method is **function expression**
```js
const sing=function(){ // or also function test(){}
	console.log("Singing");
};

sing();
```
Function expressions help when you want to pass your functions to another variables.

But the main difference here is the **hoisting** matter.
Let's go with examples:
```js
function run(){
	console.log("Running");
}
run();
```
Which will print the result as we expect.
But how about this:
```js
run();

function run(){
	console.log("Running");
}
```
It will still print the result! Although as we know, in Js that it reads and executes the code line by line.

```js
sing();

const sing=function(){
	console.log("Singing");
};
```
Now here we will have reference error.

Here we can discuss about the hoisting matter.
When we declare a function, Js will actually places it above the code behind the scene, and then executes it. It won't do it for the function expression.

##### Arrow functions
**Arrow Functions** allow a shorter syntax for **function expressions**.
You can skip the **function** keyword, the **return** keyword, and the **curly brackets**:

**Before Arrow:**
```js
let myFunction=function(a,b){return a*b};
```

**With Arrow**
```js
let myFunction=(a,b)=>a*b;
```
##### this in functions
In JS, the `this` keyword refers to an **object**.
The `this` keyword refers to **different objects** depending on how it is used:

| Alone, `this` refers to the **global object**.                                     |
| ---------------------------------------------------------------------------------- |
| In a function, `this` refers to the **global object**.                             |
| In a function, in strict mode, `this` is `undefined`.                              |
| In an object method, `this` refers to the **object**.                              |
| In an event, `this` refers to the **element** that received the event.             |
| Methods like `call()`, `apply()`, and `bind()` can refer `this` to **any object**. |
**this** alone when used, `this` refers to the **global object**.
Because `this` is in the global scope.
In a browser window the global object is `[object Window]`.
##### Function's call method
With the `call()` method, you can write a method that can be used on different objects.
In JavaScript all functions are object methods.
If a function is not a method of a JavaScript object, it is a function of the global object.
The example below creates an object with 3 properties, fname, lname, fullName.
```js
const person={
	fname:"Alireza",
	lname:"Shoja",
	fullname:function(){
		return this.fname+ ' ' + this.lname;
	}
}

person.fullname();
```

**JS call() method:**
It can be used to invoke (call) a method with an object as an argument (parameter).
*Note:* With `call()`, an object can use a method belonging to another object.
```js
const person={
    fullname:function(){
        return this.firstName+" "+this.lastName;
    }
}
  
const person1={
    firstName:"Ali",
    lastName:"Shoja",
};
  
const person2={
    fname:"Shirin",
    lname:"Taheri",
};
  
console.log(person.fullname.call(person1)); //Ali Shoja
console.log(person.fullname.call(person2)); //undefined undefined
```
The variable names should be as the same as the method's variables.

**call() method with arguments:**
The `call()` method can accept arguments:
```js
const person={
    fullname:function(country,city){
        return this.firstName+" "+this.lastName+" "+country+","+city;
    }
}
  
const person1={
    firstName:"Ali",
    lastName:"Shoja",
};
  
const person2={
    fname:"Shirin",
    lname:"Taheri",
};
  
console.log(person.fullname.call(person1,"Iran",'Mashhad')); //Ali Shoja Iran,Mashhad
```

##### Function vs anonymous function
```js
function print(){
	console.log("Print");
}

print();

const play=function(){
	console.log("Playing");
};

play();
```