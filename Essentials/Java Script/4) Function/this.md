`this` keyword references the object that is running the current function.
```js
const car={
    name:'Toyota',
    model:'prado',
    getFullName(){
        console.log(this);
        console.log(`${this.name} ${this.model}`);
    },
};
  
car.getFullName();
/*
{
  name: 'Toyota',
  model: 'prado',
  getFullName: [Function: getFullName]
}
Toyota prado
*/
```
So every method that exists beneath an object, this references that object.

##### this in functions
```js
function test(){
    console.log(this);
}
  
test();
```
When you're using node.js here in your code editor, `this` references the global object inside the node.
But if you use it in browser, `this` references to the window object.