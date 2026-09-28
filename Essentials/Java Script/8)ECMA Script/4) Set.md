A set is a collection of values where each value is unique.
```js
const my_set=new Set();
my_set.add("Samsung");
my_set.add("Apple");
my_set.add("Samsung");
  
console.log(my_set); // Samsung Apple
```
As you can see, we cannot have duplicate members in set.
Set's type is **Object**.

You can store any types of data in a set.

**Making set with default values**
```js
const mySet=new Set([1,2,3]);
```

**Size of a set:**
```js
console.log(mySet.size);
```

**Has method**
You can use some of the array's methods on sets as well:
```js
console.log(collection.has("apple"));
```

##### Deleting from set
```js
const mySet=new Set([1,2,3]);
mySet.delete(2);
console.log(mySet); //1,3
```

**clear() method**
```js
mySet.clear();
```
It clears the whole set.

##### Loops on sets
We can use `forEach()` on sets:
```js
const mySet=new Set([3,2,4,6,5,7]);

mySet.forEach((val)=>{
    console.log(val);
});
```

Or we can use `for of`:
```js
for(const item of mySet){
	console.log(item);
}
```

##### Turning a set into an array
```js
const arr=[...mySet];
console.log(arr);
```