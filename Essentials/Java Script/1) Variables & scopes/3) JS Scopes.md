**Scope** determines the accessibility of variables. JS variables have 3 types of scope:
- Global scope
- Function scope
- Block scope

##### Global scope
Variables declared **Globally** (outside any block or function) have **Global Scope**.
**Global** variables can be accessed from anywhere in a JavaScript program.
Variables declared with `var`, `let` and `const` are quite similar when declared outside a block.
They all have **Global Scope**:

##### Function scope
Each JS function have their own scope.
Variables defined inside a function are not accessible(visible) from outside the function.
Variables declared with `var`, `let` and `const` are quite similar when declared inside a function.
They all have **Function Scope**.
```js
function func1(){
	var car1="volvo"; // Function Scope
}

function func2(){  
  let car2="Volvo";  // Function Scope  
}  
  
function func3(){  
  const carName="Volvo";  // Function Scope  
}
```
Variables declared within a JavaScript function, are **local** to the function.

##### Block scope
Before **ES6**, JS variables could only have **Global scope** or **Function scope**. ES6 introduced two important new JavaScript keywords: `let` and `const`. These two keywords provide **Block Scope** in JavaScript.
Variables declared with `let` and `const` inside a code block are "block-scoped," meaning they are only accessible within that block.
```js
{
	let x=2;
}
// x can NOT be used here
```
- Variables declared with the `var` keyword can NOT have block scope.
- Variables declared with the `var` keyword, inside a { } block; can be accessed from outside the block.

*!Note:* If you assign a value to a variable that has **not been declared**, it will become a **GLOBAL** variable.

```js
function car(){
	car1="Pride";
}

console.log(car1);
```

**Examples of code blocks:**
A **code block** or **block statement** is a group of statements enclosed within curly braces **{ }**.

*Functions:*
```js
function myfunc(){
	//block of code
}
```

**if and else statements:**
```js
if(condition){
	//block of code
}

else{
	//block of code
}
```

**For and while:**
```js
for(;;){
}

while(condition){
}
```

*!Note*: Remember, variables declared with `let` and `const` inside a code block are "block-scoped," meaning they are only accessible within that specific block.