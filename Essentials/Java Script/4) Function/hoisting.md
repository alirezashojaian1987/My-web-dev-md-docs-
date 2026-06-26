When running your code, JS reads the code line by line. sometimes you want to run a function, before it's declaration.
```js
print();

function print(){
	console.log("Printing");
}
```
The code works. In JS, when the code is read, JS places function expressions at the top priority.

```js
sing();
  
const sing=function(){
    console.log("Sing");    
};
```
The code above doesn't work because sing is not defined yet.

##### Hoisting for different declaration types
```js
console.log(varTest); //undefined
var varTest=100;
```
The code above will not result in error. varTest variable is undefined.

```js
console.log(letTest); //cannot access 'letTest' before initialization
let letTest=100;
```
The code above will result in error.
*Note:* const variables will result the same way as let vars:
```js
console.log(constTest); //cannot access 'constTest' before initialization
const constTest=100;
```

##### var, const, let in function scopes
```js
function test(){
    if(true){
        // var insideIf=10;
        // let insideIf=10;
        // const insideIf=10;
    }
    console.log(insideIf); //10 / error / error
}

test();
```

```js
function test(){
    // var insideIf=10;
    // let insideIf=10;
    // const insideIf=10;
}
  
console.log(insideIf);
```
Three of them will result in error. Remember try not to use `var` declaration as you can.