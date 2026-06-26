```js
function sum(var1,var2,var3,var4){
    console.log(arguments); //[Arguments] { '0': 1, '1': 2, '2': 3, '3': 4 }
}
  
sum(1,2,3,4);
```
The `arguments` keyword, returns an array like object, containing variables you gave the function as arguments.

when you want to give your functions as many arguments as you need, you can use this method:
```js
function sum(){
    let total=0;
    for(const item of arguments){
        total+=item;
    }
  
    return total;
}
  
console.log(sum(1,2,3)); //6
console.log(sum(1,2,3,4)); //10
console.log(sum(1,2,3,5,4)); //15
```

Another method is using `rest` operator method below: (`...`)
```js
function sum(...args){
    console.log(args); //[ 1, 2, 3, 4 ]
}
  
sum(1,2,3,4);
```
It will return an array of your given elements. You can use any name instead of args, if you need.
```js
function sum(...nums){
    let total=0;
    for(const item of nums){
        total+=item;
    }
  
    return total;
}
  
console.log(sum(1,2,3)); //6
console.log(sum(1,2,3,4)); //10
console.log(sum(1,2,3,5,4)); //15
```
*Note:* You can put another variable before, or after `...args` as well.

##### Default function arguments
```js
function rec(width,height=2){
    return width*height;
}
  
console.log(rec(2));//4
console.log(rec(2,3));//6
```
This will prevent errors when you're not giving another argument.
The better way for that purpose is using this method:
```js
function rec(width,height){
    width=width || 10;
    height=height || 20;
}
  
console.log(rec()); //200
```
*!Note:* Remember to put the arguments at left, they are priority for the default declaration!