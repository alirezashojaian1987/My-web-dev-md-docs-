A variable can hold 8 types of data: 7 Primitives and 1 Object
##### Data types in JS
**Primitive data types:**
*Numeric type:*
+ Number
+ bigint
*Non-Numeric type:*
+ string
+ boolean
+ Null
+ Undefined
+ symbol

**None primitive or reference typs:**
*Objects:*
+ object
+ array
+ function
+ date
+ RegExp
+ set
+ map

| Type      | Description                                   |
| --------- | --------------------------------------------- |
| String    | A text of characters enclosed in quotes       |
| Number    | A number representing a mathematical value    |
| Bigint    | A number representing a large integer         |
| Boolean   | A data type representing true or false        |
| Object    | A collection of key-value pairs of data       |
| Undefined | A primitive variable with no assigned value   |
| Null      | A primitive value representing object absence |
| Symbol    | A unique and primitive identifier             |
*Note:* As mentioned above, undefined is a type, but also can be a value. A variable is undefined when there's no value assigned to it.

*Examples:*
```JS
// Strings  
let color = "Yellow";  
let lastName = "Johnson";  
  
// Number  
let length = 16;  
let weight = 7.5;  
  
// BigInt  
let x = 1234567890123456789012345n;  
let y = BigInt(1234567890123456789012345);  
  
// Boolean  
let x = true;  
let y = false;  
  
// Object  
const person = {firstName:"John", lastName:"Doe"};  
  
// Array object  
const cars = ["Saab", "Volvo", "BMW"];  
  
// Date object  
const date = new Date("2022-03-25");  
  
// Undefined  
let x;  
let y;  
  
// Null  
let x = null;  
let y = null;  
  
// Symbol  
const x = Symbol();  
const y = Symbol();
```

*!Note:* When adding a number and a string, JavaScript will treat the number as a string.
```JS
let x="Ali"+20; //Ali20
let y=20+"Ali"; //20Ali
```

JavaScript evaluates expressions from left to right. Different sequences can produce different results:
```js
let x=16+4+"Ali"; //20Ali
let y="Ali"+16+4; //Ali164
```

In the first example, JavaScript treats 16 and 4 as numbers, until it reaches "Volvo".
In the second example, since the first operand is a string, all operands are treated as strings.

##### Primitive vs reference types
**Mutability**
```js
let a=10;
let b=a;
a=5;
console.log(a,b); //5 10
```

```js
const arr=[10,15];
const arr2=arr;
arr[0]=0;
console.log(arr); //[0,15]
console.log(arr2); //[0,15]
```
So as you can see above, primitive types are immutable but the reference types are mutable. The reason is that they have the address, not the value.

**Storage mechanism**
Primitive types store actual values.
Non-primitive types store references to values.

**Memory management**
Primitive values are stored in stack.
Non-primitive types are stored in heap and the references to them are stored in stacks.
##### JS types are dynamic
JavaScript has dynamic types. This means that the same variable can be used to hold different data types:
```js
let x;       // Now x is undefined  
x = 5;       // Now x is a Number  
x = "Ali";  // Now x is a String
```

##### JS strings
Strings are written with quotes. You can use single or double quotes.
```js
let car1="BMW X4";
let car2='Pride';
```
*!Note:* You can use quotes inside a string, as long as they don't match the quotes surrounding the string!

##### JS numbers
All JavaScript numbers are stored as decimal numbers (floating point).
Numbers can be written with, or without decimals.
```js
let x1=12;
let x2=12.00;
```

**Exponential notation**
Extra large or extra small numbers can be written with scientific (exponential) notation.
```js
let y=123e5; //12300000
let x=123e-5; //0.00123
```

##### JS booleans
Booleans can only have two values: `true` or `false`.
```js
let x = 5;  
let y = 5;  
let z = 6;  
(x == y)       // Returns true  
(x == z)       // Returns false
```

##### JS objects
JavaScript Objects represent **complex data** structures and functionalities beyond the primitive data types (string, number, boolean, null, undefined, symbol, bigint).

JavaScript objects are written with curly braces `{ }`.
JavaScript objects contains a collection of different **properties**.
Object properties are written as `name:value` pairs, separated by commas.
```js
const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```
It's better to declare objects with `const`. But the problem is you can't add anything after declaring it.
So you can use this declaration method instead:
```js
const person=new Object();
person.name="Ali"; //This adds a name key with the "Ali" value
person.age=21; //This adds a age key with the 21 value
console.log(person);
```

##### The typeof operator
You can use the JavaScript `typeof` operator to find the type of a JavaScript variable.
The `typeof` operator returns the type of a variable or an expression:
```js
let x="Ali";
console.log(typeof(x)); //string
```

##### JS arrays
JavaScript arrays are a special type of JavaScript objects.
JavaScript arrays are written with square `[ ]` brackets.
Array items are separated by commas.
```js
const names=["Alireza", "Shirin", "Mohammad"];
```
Array indexes are zero-based.

##### Undefined
In JavaScript, a variable without a value, has the value `undefined`. The type is also `undefined`.
```js
let name;
console.log(typeof(name)); //undefined
```
Any variable can be emptied, by setting the value to `undefined`. The type will also be `undefined`.
```js
name=undefined;
```

*!Note:* An empty value has nothing to do with `undefined`.
An empty string has both a legal value and a type.
```js
let name=""; //string
```

##### Null 
In JavaScript, a variable or an expression can obtain the datatype null in several ways.
A function can return null or a variable can be assigned the null value.
```js
let name=null; 
```
The **typeof** operator returns **object** for null.
This is a historical quirk in JavaScript and does not indicate that null is an object.

The strict equality operator `===` compares both the value and the type of the operands.

It returns `true` only if both the operands values and types are `null`.

The **loose equality operator** `==` also returns `true` for a `null` value, but it also returns true if the value is `undefined`.

Using `==` is not recommended when checking for `null`.

