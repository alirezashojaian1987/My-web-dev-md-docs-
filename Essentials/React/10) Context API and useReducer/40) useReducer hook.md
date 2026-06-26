So far we used useStates for managing our states and values in different components.
Now sometimes, our states and managing them can be a little complicated so we want to introduce a new method.

Let's start with an example. Considering having this code:
`App.jsx`
```jsx
import Button from "./components/Button/Button";
import { useState } from "react";
  
export default function App(){
  const [value,setValue]=useState(100);
  return(
    <div className="w-full h-[100vh] bg-white flex flex-col items-center justify-center gap-8 text-xl">
      <div>{value}</div>
      <div className="flex gap-8">
        <Button onClick={()=>setValue(value+1)}>Increase</Button>
        <Button onClick={()=>setValue(100)}>Reset</Button>
        <Button onClick={()=>setValue(value-1)}>Decrease</Button>
      </div>
    </div>
  )
}
```
`Button.jsx`
```jsx
import { useEffect } from "react";
import styles from "./Button.module.scss";
  
export default function Button({children , onClick , variant}){
    return(
        <button className={`${styles.btn} ${styles[variant]}`} onClick={onClick}>
            {children}
        </button>
    );
};
```
So as you can see we expect that when pressing increase, it adds 1 to 100, decrease 1 from 100 and reset turns the value back to 100.

Now imagine this that your page has so many states and logics and now you want to use reset again, you may forget that what was the initial value(which was 100, but you think it was 0). 

Or you may even not now what even was the initial value's type.

When using `setStates` you must always be careful with the logic you defined for yourself and now using it again.
So `useReducer` hook comes to rescue for managing your states.
##### How to use useReducer
useReducers support components and it's better for them to be at top level. useReducers get 2 arguments, first is a reducer function and the second one is the initial value.

It will return 2 things, first is the value the 2nd one is the action we want to set the value with.
```jsx
const [state,dispatch]=useReducer(()=>{},100);
```
The names are optional but they are more common.
Dispatch helps us to send a request that the function to be applied.
Reducer will set the value for us.

You can use your function on a different page or upper than your component.

```jsx
import Button from "./components/Button/Button";
import { useState,useReducer } from "react";

const reducer=(state,action)=>{
  if(action==="Increase") return state+1;
  if(action==="Decrease") return state-1;
  if(action==="Reset") return 100;
  return state;
}
  
export default function App(){
  const [state,dispatch]=useReducer(reducer,100);
  return(
    <div className="w-full h-[100vh] bg-white flex flex-col items-center justify-center gap-8 text-xl">
      <div>{state}</div>
      <div className="flex gap-8">
        <Button onClick={()=>dispatch("Increase")}>Increase</Button>
        <Button onClick={()=>dispatch("Reset")}>Reset</Button>
        <Button onClick={()=>dispatch("Decrease")}>Decrease</Button>
      </div>
    </div>
  )
}
```
Reducer gets the state as the first arg. The action will be the 2nd arg. It can be a string or an object. Here is a string. 
In the function, it's important that it returns a value as a state.

It's best not to use the strings in the dispatch function, you can save them in constant vars and use the vars in your reducer function instead. 