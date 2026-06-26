##### For loop
**For Loops** can execute a block of code a number of times.
**For Loops** are fundamental for tasks like performing an action multiple times.
```syntax
for(exp1;exp2;exp3){
	//code
}
```
**exp 1** is executed (one time) before the execution of the code block.
**exp 2** defines the condition for executing the code block.
**exp 3** is executed (every time) after the code block has been executed.
*Example:*
```js
for(let i=0;i<5;i++){
	console.log(i,"HELLO");
}
```

```js
const arr=[2,5,4,22,3];
for(let i=0;i<arr.length;i++){
	console.log(arr[i]);
}
```

##### while loop
```syntax
while(condition){
	code
}
```

```js
let i=0;
while(i<10){
	console.log(i);
	i++;
}
```
we have do while too.

##### Continue & break keywords
break exits the loop.
continue skips the iteration in process and goes to next iteration