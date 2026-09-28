##### Destructuring objects
See objects as a package, sometimes we need a key out of it. Like unpacking an element from the object
```js
const obj={ UserName:"Alireza", id:10, };
const { UserName }=obj;

//instead of this: const name=obj.UserName;
  
console.log(UserName); //Alireza
```

You can unpack functions from objects as well.
```js
const obj={
	UserName:"Alireza",
	id:10,
	sing(){
		console.log("Ha ha ha");
	},
};
const { UserName, sing }=obj;
  
console.log(UserName); //Alireza
sing(); //Ha ha ha
```

*!Note:* If you use a non-existing key value in an object while using destructuring method, it results in `undefined` and will not cause any error.

*!Note:* Remember that to make sure that the variable you are destructuring elements from it, is an object. And also not a `null` object. Because it will cause an error while the program is running. 

*!Note:* Don't use destructures on dynamic objects as well.

##### Destructuring arrays
Destructure method works for arrays as well:
```js
const arr=[1,2,3];
const [num1,num2]=arr;
  
console.log(num1,num2); //1 2
```