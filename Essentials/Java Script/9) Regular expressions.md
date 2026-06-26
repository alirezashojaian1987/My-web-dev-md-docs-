Regex as above shows, is used for example we have an input and we want to check whether it has a proper email form or not. It helps us to make a validation for the texts and inputs and...
```js
const regex=/car/;
console.log(typeof(regex)); //object
  
regex. //when you see the methods, you'll see that they are different methods from the objects and string
```

```js
const regex=/car/;
const str="I have a car";
const str2="I'm a nigga";
console.log(regex.test(str)); //true
console.log(regex.test(str2)); //false
```
*!Note:* that the regexes are case sensitive.
To avoid the condition above, you can use flags for our regex. There are different types of flags.

**i flag**
Ignores the case sensitive condition for us.
```js
const regex=/car/i;
const str="I have a Car";
console.log(regex.test(str)); //true / without i in regex: false
```

##### Expressions we can make
`/char ..... char/`
```js
const regex=/s..g/;
console.log(regex.test("sing")); //true
console.log(regex.test("Samsung")); //false
```
The code above checks that an string has a length of 4 characters, starts with `s` and ends with `g`.
The amount of dots are the amount of characters no matter what is the character.

`[]`
```js
const regex=/s[oi].g/;
console.log(regex.test("song"));//true
console.log(regex.test("sing"));//true
console.log(regex.test("sung"));//false
```
The code above checks that an string has a length of 4 chars, starts with `s`, the second char can be `o` or `i`.  then a random char and it ends with `g`. 

`^ & []`
```js
const regex=/s[^oi].g/;
console.log(regex.test("song"));//false
console.log(regex.test("sing"));//false
console.log(regex.test("sung"));//true
```
The code above checks that an string has a length of 4 chars, starts with `s`, the second char must not be `o` or `i`.  then a random char and it ends with `g`.  The `^` here acts like a `not`.

`*` 
```js
const regex=/go*d/;

console.log(regex.test("gd")); //true
console.log(regex.test("god")); //true
console.log(regex.test("good")); //true
console.log(regex.test("goose")); //false 
console.log(regex.test("goosed")); //false
```
Starts with `g`, the `o`  can be repeated multiple times or not and ends with `d`.

`?`
```js
const regex=/colou?r/;

console.log(regex.test("color")); //true
console.log(regex.test("colour")); //true
console.log(regex.test("colouur")); //false
```
Only one or no repeat times of the character is allowed.

`char{n}`
```js
const regex1=/o{2}/;
const regex2=/u{2}/;
  
console.log(regex1.test("color")); //false
console.log(regex2.test("colouur")); //true
```
Checks that there is at least on occurrence of n chars with each other. Here regex1 says 2 `o`s with each other .

`^`
```js
const regex=/^hello/i;
console.log(regex.test("Hello World"));
```
Must start with the string shown. It even detects spaces.

`$`
```js
const regex=/world$/i;
console.log(regex.test("Hellol World"));
```
Must end with the string shown.

Checking a number string
```js
const regex=/(\d{3}-\d{8})/;
console.log(regex.test("021-88886565")); //true
```
d stands for digit.

`d+`
checks if a number exist.
```js
const regex=/\d+/;
console.log(regex.test("error")); //false
console.log(regex.test("erro4r")); //true
```

##### How to abstract numbers from string
```js
const regex=/\d+/;
const str='The price is 100 dollars and 20 cents';

const result=str.match(regex);
console.log(result);
/*
[
  '100',
  index: 13,
  input: 'The price is 100 dollars and 20 cents',
  groups: undefined
]
*/
```
You can put the `g` flag in order to find every numbers.
```js
const regex=/\d+/g;
console.log(result);
//[ '100', '20' ]
```

##### More examples
```js
const str="The cost of the new phone was $799, which is just under a 1000 dollars, and it was well worth every dollar spent. Dollar is usa money.";

const regex=/dollars*/ig;
console.log(str.match(regex));
```
It will find every word of dollar. considering upper cases and s at the end. We can use both i and g flags together.

```js
const str=`The cost of the new phone was $799, which is just under a 1000 dollars,
and it was well worth every dollar spent.
Dollar is usa money.`;

const regex2=/^dollars*/ig;

console.log(str.match(regex2)); //null
```
We wanted to find every dollar that is in the first of each line. To do so, we can use `m` flag. Which is used for multiline strings.
```js
const regex2=/^dollars*/igm; //Dollar
```

##### RegExp object
```js
const re=new RegExp("Hello","gi");
```