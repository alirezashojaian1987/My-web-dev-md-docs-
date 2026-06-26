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