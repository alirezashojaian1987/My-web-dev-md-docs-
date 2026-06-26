Parsers help to convert values.
##### parseInt
Returns integer form of the given value(the value can be a string or a float num or a float num string). It actually treats the given value as a string by default then turns it into num.
```js
console.log(parseInt("10"));//10
console.log(parseInt(10.234));//10
console.log(parseInt("10.234"));//10
```
##### parseFloat
Returns float form of the given value.
```js
console.log("3.14ABc") //3.14
```

##### Number
```js
console.log(Number("123")); //123
console.log(Number("123.45")); //123.45
console.log(Number("123abc")); //Nan
console.log(Number(true)); //1
console.log(Number(false)); //0
console.log(Number(null)); //0
console.log(Number(undefined)); //Nan
console.log(Number("0x11")); //17 hexadecimal
```


