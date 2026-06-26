It helps us to do specific math operations we need.

##### Math.random
Returns a random number between 0 and 1.
```js
console.log(Math.random());
```
*Note:* `Math.random()` used with `Math.floor()` can be used to return random integers.
```js
console.log(Math.floor(Math.random()*10)); //generates a num between 0 and 10
```
You can also set a range with your own function:
```js
function getRandNum(min,max){
  return Math.floor(Math.random()*(max-min))+min;
};
  
console.log(getRndInteger(10,20));
```

##### Math.PI
```js
console.log(Math.PI);
```

##### absolute
Returns the absolute form of a number:
```js
console.log(Math.abs(-5));
```

##### floor and ceil and round
The `Math.floor()` method rounds a number rounded down to the nearest integer.
The `Math.ceil()` method rounds a number rounded up to the nearest integer.
The `Math.round()` method rounds a number to the nearest integer.
```js
console.log(Math.floor(4.2)); //4
console.log(Math.ceil(4.2)); //5

console.log(Math.round(0.2)); //0
console.log(Math.round(0.5)); //1
```

##### Math.trunc()
Returns the integer form of a number.
```js
console.log(Math.trunc(1.2342312)); //1
```

##### Math.max() and min()
```js
console.log(Math.max(2,4,1,8,6)); //8
console.log(Math.min(2,4,1,8,6)); //1
```

##### Math.sqrt()
Returns the square root of a number:
```js
console.log(Math.sqrt(16)); //4
```

##### Math.pow()
Returns the power of a num:
```js
console.log(Math.pow(2,3)); //8
```