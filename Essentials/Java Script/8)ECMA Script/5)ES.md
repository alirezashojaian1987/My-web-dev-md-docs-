##### ES8
**padStart() & padEnd()**
Will fill string with the given size:
```js
str="Alireza";
console.log(str.padStart(12,"*"));
```

##### ES10
**Object.fromEntries:**
You can turn arrays into objects:
```js
const arr=[
	["a",1],
	["b",2],
	["c",3],
];

console.log(Object.fromEntries(arr)); //{a:1,b:2,c:3}
```

**trimStart() and trimEnd()**
They remove spaces from start and end.

**try catch:**
```js
try{
	10+t;
} catch{
	console.log("Error");
}
```
