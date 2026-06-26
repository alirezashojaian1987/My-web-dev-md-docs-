##### if & else
```js
if(condition){
	//block of code
}

else{
	//block of code
}
```

**else if**
```js
if(condition){
	//block of code
}

else if(condition2){
    //block of code
}

else{
	//block of code
}
```

##### Ternary operator
```js
let text=(age<18) ? "Young":"Adult";
```
The conditional operator is a shorthand for writing conditional `if...else` statements.
It is called a ternary operator because it takes three operands.
```syntax
(condition) ? expression1:expression2
```
exp1:The value to return if the condition is `true`.
exp2: The value to return if the condition is `false`.

*Example:*
```js
function test(age){
    return (age<18)?"Young":"Adult";
}
  
console.log(test(17)); //Young
console.log(test(18)); //Adult
console.log(test(19)); //Adult
```

##### Switch statement
Based on a condition, `switch` selects one or more **code blocks to be executed**
`switch` executes the code blocks that **matches an expression**.
`switch` is often used as a more readable alternative to many if...else if...else statements, especially when dealing with multiple possible values.
```syntax
switch(expression){
	case x:
		//code
		break;
	case y:
		//code
		break;
	case z:
		//code
		break;
	default:
		//code
}
```

*Example:*
```js
switch (new Date().getDay()) {  
  case 0:  
    day = "Sunday";  
    break;  
  case 1:  
    day = "Monday";  
    break;  
  case 2:  
     day = "Tuesday";  
    break;  
  case 3:  
    day = "Wednesday";  
    break;  
  case 4:  
    day = "Thursday";  
    break;  
  case 5:  
    day = "Friday";  
    break;  
  case 6:  
    day = "Saturday";  
}
```
The `getDay()` method returns the weekday as a number between 0 and 6.
The `default` keyword specifies a block of code to run if there is no case match.