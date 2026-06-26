Just like objects, map can store key value pairs as well, but with a difference:
In objects, our keys are string literals, but in maps we can use any data type as a key.
```js
const person=new Map([
    ["Fname","Alireza"],
    ["age",21],
    [{score:20},"math"],
]);
  
console.log(person); //Map(3) { 'Fname' => 'Alireza', 'age' => 21, { score: 20 } => 'math' }
```
The first element in the array is a key, the second one is value paired to the key.

##### Adding elements to map
```js
const person=new Map([
    ["Fname","Alireza"],
    ["age",21],
    [{score:20},"math"],
]);

person.set("Lname","Shoja");
  
console.log(person);
/*
Map(4) {
  'Fname' => 'Alireza',
  'age' => 21,
  { score: 20 } => 'math',
  'Lname' => 'Shoja'
}
*/
```

##### Check if a key exists in a map
```js
console.log(person.has("Fname")); //true
console.log(person.has("Job")); //false
```
You should use a key in the method.

*!Note:* About objects:
```js
console.log(person.has({score:20})); //false
```
Although we put the right name of the object in the method that also exists in the map as well, the method returns false due to the reference addresses of the object so they are not the same. To avoid this problem, we can do this:
```js
const obj={score:20};
const person=new Map([
    ["Fname","Alireza"],
    ["age",21],
    [obj,"math"],
]);

console.log(person.has({score:20})); //Now it returns true
```

##### Deleting an element from an object
```js
const obj={score:20};
const person=new Map([
    ["Fname","Alireza"],
    ["age",21],
    [{score:20},"math"],
]);

person.delete("Fname");
person.delete({score:20});
  
console.log(person);
```
Although the fname element is deleted here, but the object isn't due to the reason mentioned above.
You can delete it when you're directly refering the object itself.

**clear**
You can clear your whole map:
```js
person.clear();
```

##### Iteration on maps
**Using forEach()**
```js
//person.forEach((val)
person.forEach((val,key)=>{
    console.log(key,val);
});
```
*Note:* First argument is always value. If you put the second arg, it will be key.
Order is important

**Using for of**
```js
const person=new Map([
    ["Fname","Alireza"],
    ["age",21],
    [{score:20},"math"],
]);
  
for(const item of person){
    console.log(item);
};
/*
[ 'Fname', 'Alireza' ]
[ 'age', 21 ]
[ { score: 20 }, 'math' ]
*/
```

You can use destructures as well:
```js
for(const[key,value] of person.entries()){
	console.log({key,value});
};
```

##### values and keys methods
You can return only keys or values from a map. They return them as an object, not arrays!
```js
console.log(person.keys());
console.log(person.values());
```

##### Turning map into an array
```js
console.log(...person);
console.log(...person.keys());
```

Or we can use **Array** class instead. Using a method called `from()` which will take an iterable object.
```js
const arr=Array.from(person.values());
```