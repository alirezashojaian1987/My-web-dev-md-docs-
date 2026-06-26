There are some key features when using JS for our web designing.

First thing we know is that it's not common using internal JS code. 

Second thing is that the separation of concern which is using them with their own type files.

Third which is new now, is dependency management. Let's have an example:
In our html doc, we have 3 script files:
```html
<script src="./js.js"></script>
<script src="./js.js1"></script>
<script src="./js.js2"></script>
```
For example, we have written a function in the js file and we also used it in the js2 file. Considering the chance that we may make a mistake and not ordering them right, it will cause a problem. If js2 is defined first in the html, the browser will download that file first, the function's definition is in first js file so the browser doesn't recognize the function which will cause some issues.

Fourth new thing is reusability. Let's say we have written a html doc and used some scripts in it. Now we are writing another html doc related to the main one and also we can use some of the scripts there, it's not proper copying and pasting the code there, we always need to avoid using codes multiple times. Cause when you face a problem in your code, you need to correct it from every where you pasted the code.

##### IIFE
Immediately invoked function expressions(IIFE) is a function that will run automatically and immediately after definition.
Normally we write our functions like this:
```js
function hello(){
    console.log("Hello");
}
```
To make it in IIFE form:
```js
(function hello(){
    console.log("Hello");
})()
```
This was good for avoiding global function definitions. You could also add your methods in the window object but it's not common now.

##### CommonJS + Browserify
These two helped exporting some files and then importing in another. Or for example a function.
```js
//file1.js
function add(a,b){
	return a+b;
}
module.export=add

//file2.js
const add=require("./file1.js");
```

The other thing that browserify does is module bundling. What it does it that when your project is built, it creates a js file which will contain all of your js files content(we cannot see it). It considers dependencies as well.

##### ES6 module
The newest module that we use nowadays. It solved so many problems. 
**Encapsulation:** Modules keep code that belongs together in one place, which helps prevent global namespace pollution.

**Reusability:** Code inside a module can be reused across different parts of the application or even in different applications.

**Maintainibility:** Breaking down a program into modules makes it easier to manage and update.

**Dependency management:** Modules can import dependencies they need without relying on global variables, making the code more predictable. 

**Webpack**
Will contain configs. 

###### Exporting and importing
```js
//file1.js
function add(a,b){
	return a+b;
}

export default add;

//file2.js
import add from "./file1.js"
```

```js
function add(a,b){
	return a+b;
}

function hi(){
 console.log("Hello");
}

export {add,hi}

import {add,hi} from "./file1.js"
```