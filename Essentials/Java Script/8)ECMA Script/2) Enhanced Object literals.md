You can insert elements in an object simply
```js
const fname="Alireza";
let age=21;
const talk=()=>{
	console.log("Hello");
};

const obj={
	fname,
	age,
	talk;
};

console.log(obj.fname); //Alireza
console.log(obj.age); //21
obj.talk(); //Hello
```