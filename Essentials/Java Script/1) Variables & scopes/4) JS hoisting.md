Hoisting is JavaScript's default behavior of moving declarations to the top.
In JavaScript, a variable can be declared after it has been used.
```js
x=5;
console.log(x);
var x;
```
Variables defined with `let` and `const` are hoisted to the top of the block, but not _initialized_.

Meaning: The block of code is aware of the variable, but it cannot be used until it has been declared.

Using a `let` variable before it is declared will result in a `ReferenceError`.