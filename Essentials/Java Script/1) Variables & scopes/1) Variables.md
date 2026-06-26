#### JS Variables
Variables = Data containers
JS variables can be declared in 4 ways:
**Modern JS:**
+ Using `let`
+ Using `const`
**Older JS:**
+ Using `var` (Not Rec)
+ Automatically (Not Rec)

```JS
let x=5;
let y=6;
let z=x+y;
```

```JS
const x=5;
const y=6;
const z=x+y;
```

##### JS identifiers
Variables are identified with **unique names** called **identifiers**.
Names can be short like x, y, z.
Names can be descriptive age, sum, carName.

The rules for constructing names (identifiers) are:
- Names can **contain** letters, digits, underscores, and dollar signs.
- Names must **begin** with a letter, You can also use a $ sign or an underscore (_).
- Names are **case sensitive** (X is different from x).
- **Reserved words** (JavaScript keywords) cannot be used as names.
```JS
let $ = "Hello World";  
let $$$ = 2;
```

##### Declaring JS variables
You declare a JavaScript variable with the `let` keyword or the `const` keyword.
```JS
let carname;
```
After the declaration, the variable has no value (technically it is `undefined`).
*!Note:* It will not be a NULL variable! NULL variables are actually objects.
To **assign** a value to the variable, use the equal sign.
```JS
carname="Volvo"
```
Most often you will assign a value to the variable when you declare it.

**Using const:**
```JS
const carname="Volvo"
```
*!Note:* Remember that you can't change the value of the const defined variable after declaring it.

*!Note:* Undeclared variables are **automatically declared** when first used which is not recommended.

##### When to use `var`, `let`, or `const`?
1. Always declare variables
2. Always use `const` if the value should not be changed
3. Always use `const` if the type should not be changed (Arrays and Objects)
4. Only use `let` if you cannot use `const`
5. Never use `var` if you can use let or const.

##### One statement, many variables
You can declare many variables in one statement.
Start the statement with `let` or `const`and separate the variables by **comma**:
```JS
let person="Ali", carName="Pride", age=21;
```
A declaration can span multiple lines:
```JS
let person="Ali",
carName="Pride",
age=21;
```

##### The assignment op(=)
In JavaScript, the equal sign (`=`) is an **assignment** operator, not an **equal to** operator.
The **equal to** operator is written like `==` in JavaScript.

##### JS arithmetic
As with algebra, you can do arithmetic with JavaScript variables, using operators like `=` and `+`.

You can also add strings, but strings will be concatenated:
```JS
let x="John"+ " " +"pork";
```

*!Note:* If you put a number in quotes, the rest of the numbers will be treated as strings, and concatenated.
```JS
let x = "5" + 2 + 3;
//result="523"
```

```JS
let x = 2 + 3 + "5";
//result="55"
```

##### Ternary op
