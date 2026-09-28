##### ES7
It added `includes` method for arrays:
```js
const nums=[1,2,3];
console.log(nums.includes(4));
```
Which returns true or false.

The other thing was **Exponentiation op**:
```js
console.log(2 ** 3); //8
```
It's like Math's power function
##### ES8
**padStart() & padEnd()**
Will fill string with the given size:
```js
str="Alireza";
console.log(str.padStart(12,"*"));
```

The next features are: entries, values and keys from the Object class.

And the last features which became popular were Async and Await which we'll discuss later.
##### ES10
**Arrays flat method**
Which was used for making an array inside another array, to fo one layer upper.
```js
const arr=[1,[2,[3,[4]],5]];
console.log(arr.flat(3)); //[1,2,3,4,5]
```

**Object.fromEntries:**
You can turn arrays into objects:
```js
const arr=[
	["a",1],
	["b",2],
	["c",3],
];

console.log(Object.fromEntries(arr)); //{ a:1, b:2, c:3 }
```

**trimStart() and trimEnd()**
They remove spaces from start and end.
```js
const fname="     Alireza";
console.log(fname.trimStart()); //"Alireza"
```
As you remember, we also have `trim()` method which removes the spaces from both sides.

**try catch:**
```js
try{
	10+t;
} catch{
	console.log("Error");
}
```
Which helps us to check an statement and get catch errors early in order to prevent the app crashing.
##### ES2020
It's one of the newest Ecma script versions. 

**BigInt**
One of the new added features is a new data type called BigInt.
When having a pretty big number, you can define it as BigInt.

There's a maximum value for a number that Js can handle, to show it:
```js
console.log(Number.MAX_SAFE_INTEGER);
```
Now you can't perform math on that value:
```js
console.log(Number.MAX_SAFE_INTEGER + 10);
```
Which will show a different value. This means that the number is now out of the range and will result in wrong results.

BigInt solves this.

**Optional chaining operator**
This is one of the most used features since it has added to Js.
It returns **undefined** if an object is **undefined or null**.
(Instead of throwing an error).

```js
const user1={
    id:1,
    name:"Ali",
    address:{
        city:"Mashhad",
        alley:"40th",
    },
};
  
const user2={
    id:1,
    name:"Mmd",
    address:{
        city:"Mashhad",
        street:"Azadi",
        alley:"40th",
    },
};
```
Having these objects and for example you want to have a for loop on them. As you see, they are different in one property which is street.
```js
console.log(user1.address.street); //undefined
```
Now imagine that you get datas, objects from backend, they can actually result in errors in these situations.

To prevent that, we can use `optional chaining`.
```js
console.log(user1?.sk);
```
##### ES2021
**Logical assignment Ops**
`&&= and ||=`
```js
let a=false;
let b=true;

a &&= b;

console.log(a); //false

a ||=b;

console.log(a); //true
```

**replaceAll()**
```js
const str="The weather is nice and the day is nice as well"
```
We used the `replace()` method before.
```js
const newStr=str.replace("nice", "great");
// The weather is great and the day is nice as well
```
It only changes the first occurrence. 
To change all the occurrences:
```js
const newStr=str.replace("nice", "great");
```