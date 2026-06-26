##### Types of JS operators
There are different types of JS operators:
+ Arithmetic ops
+ Assignment ops
+ Comparison ops
+ Logical ops
+ And more...

**Arithmetic ops:**

| Operator | Description |
|--- |--- |
|+|Addition|
|-|Subtraction|
|*|Multiplication|
|**|Exponentiation|
|/|Division|
|%|Modulus (Division Remainder)|
|++|Increment|
|--|Decrement|

The `+` can also be used to add (concatenate) strings.

**Assignment ops:**

|Operator|Example|Same As|
|---|---|---|
|=|x = y|x = y|
|+=|x += y|x = x + y|
|-=|x -= y|x = x - y|
|*=|x *= y|x = x * y|
|/=|x /= y|x = x / y|
|%=|x %= y|x = x % y|
|**=|x **= y|x = x ** y|

The `+=` assignment operator can also be used to add (concatenate) strings.

**Comparison ops:**
Comparison operators are used to **compare two values**.
Comparison operators always return `true` or `false`.

|Operator|Description|Example|
|---|---|---|
|==|equal to|x == 5|
|===|equal value and equal type|x === 5|
|!=|not equal|x != 5|
|!==|not equal value or not equal type|x !== 5|
|>|greater than|x > 5|
|<|less than|x < 5|
|>=|greater than or equal to|x >= 5|
|<=|less than or equal to|x <= 5|

**Logical ops:**

| Operator | Description |
| -------- | ----------- |
| &&       | logical and |
| \|       | logical or  |
| !        | logical not |

**String Ops:**
```js
let mainword="";
let word="hello"+" "+"world";
mainword+=word;
```