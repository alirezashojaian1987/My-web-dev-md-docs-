##### Curried function
```js
const add=(a,b)=>a+b;

const curriedAdd=(a)=>(b)=>)a+b;

console.log(curriedAdd(10)(40);
```
It's used when in a function you want some parted functions in it.
```js
const curriedPow=(a)=>(b)=>Math.pow(b,a);
const powerof2=curriedPow(2);
console.log(powerof2(4)); //16
```

##### Compose function
```js
const compose=(f,g)=>(a)=>f(g(a));

const plus1=(number)=>number+1;
const res=compose(plus1,plus1)(7);
console.log(res);//9
```

```js
const compose=(f,g)=>(a)=>f(g(a));

const plus1=(number)=>number+1;
const mult5=(number)=>number*5;
const res=compose(plus1,mult5)(3);//=> 3*5 => 15+1=16
console.log(res);//9
```