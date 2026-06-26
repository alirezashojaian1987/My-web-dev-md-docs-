##### String objects
We have two types of string, primitive type, object type.
```js
const car_name=new String("Benz");
```
The differences are the definition syntax and also the methods we can use in an string object.
```js
const car1="Pride";
const car2=new String("Benz");
  
console.log(typeof(car1));
console.log(typeof(car2));
```

###### Some methods in string
**length**
```js
const phrase="Pride is a shitty car";
console.log(phrase.length); //21
```

**Indexing**
```js
const phrase="Pride is a shitty car";
console.log(phrase[2]); //i
```

**includes**
```js
const phrase="Pride is a shitty car";
console.log(phrase.includes("shitty")); //true
```

**split**
```js
const phrase="Pride is a shitty car";
console.log(phrase.split(" ")); //[ 'Pride', 'is', 'a', 'shitty', 'car' ]
```
The code above turns your string into an array by the space or a defined character which will be inserted.

**replace & replaceAll**
replace method finds the first target word and replaces it with the requested word, then returns it.
```js
const phrase="Pride is a shitty car";
console.log(phrase.replace("shitty","fatal")); //Pride is a fatal car
```

`replaceAll` method on the other hand, changes all the occurrences. Then returns the new string.
```js
const phrase="Pride is a shitty car";
console.log(phrase.replaceAll(" ",","));
```
The code above find all the spaces and replace them with comma.

**toUpperCase & toLowerCase**
```js
const Name="Alireza";
  
console.log(Name.toUpperCase()); //ALIREZA
console.log(Name.toLowerCase()); //alireza
```
*One real time example*
```js
const car="Benz is a very good car";
console.log(car.toLowerCase().includes("benz"));
```
Which will returns us true.

**Concat**
Connects two or more strings to each other:
```js
const fname="Alireza";
const lname=" Shojaian";
const age=22;
console.log(fname.concat(lname,age)); //Alireza Shojaian22
```