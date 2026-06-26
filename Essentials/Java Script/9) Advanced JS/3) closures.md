Closures is for a function that returns an inner function and that inner function has access to the parent function attributes and even after returning it, the attribute is not cleared.
```js
const first=()=>{
    const age=20;
  
    const second=()=>{
        alert(age);
    };
  
    return second;
};
  
const newfunc=first();
  
newfunc(); //in the browser: 20
```

```js
const first=()=>{
    let age=20;
  
    const second=()=>{
        alert(age);
    };
    
    age=22;
  
    return second;
};
  
const newfunc=first();
  
newfunc(); //22
```
It will return the last value.

##### Some uses of closure
```js
const elementCreator=(element)=>{
    return ()=>{
        document.createElement(element);
    };
};
  
const createElm=elementCreator("div");
createElm();
createElm();
createElm();
createElm();
```
You can set any logic you want in your function.

**Counter:**
```js
const counter=()=>{
	let num=10;
	return()=>{
		num++;
		console.log(num);
	};
};

const c=counter();

c(); //11
c(); //12
c(); //13
```