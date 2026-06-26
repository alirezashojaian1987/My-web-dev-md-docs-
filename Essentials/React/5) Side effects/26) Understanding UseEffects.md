Now that we learnt about the use states, let's talk about the side effects first, then we get to the use effects as well.
So far, every component we made, often had props and arguments and returned a value eventually. Input and result

##### Pure function
Pure function means that you declare a function that whenever it gets an input, it gives a result.
Doesn't matter how many times you call it, you expect same result of the same input of it.
It's good that we declare our functions as pure functions as much as we can.
There are times that we have to do some side tasks beside the main task as well in our component.

For example look at this component:
```jsx
import styles from "./Button.module.scss";

export default function Button({label,onClick,variant}){
    return(
        <button className={`${styles.btn} ${styles[variant]}`} onClick={onClick}>
            {label}
        </button>
    );
};
```
As we talked about pure function, this component gets some inputs and then gives a result. Simple. It's only doing one action.

But there are times that for example we want to store some data in a local storage, or another example we want to send a request to a server from a component then retrieve some data.
Or sometimes we want to change the DOM directly or manually. 

These aren't about rendering or returning a JSX. It's about a subject called **Side Effects**.

##### use effect
When talking about side effects, we need to learn about use effects.
Use effect is another built-in functions of React which is actually called a **Hook**.
We can handle side effects with useEffects.

Now to use it we need to import it:
```jsx
import {useEffect} from "react";
```
*Note:* Every hook starts with a `use` prefix. 
We talked about another hook before called `useState`.

Now the example on how to use useEffects:
```jsx
import Card from "./components/Card";
import { useEffect } from "react";

export default function App(){
  useEffect(()=>{
    console.log("render");
  })
  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        <p className="p-2 text-xl">Handling side effects</p>
      </Card>
    </div>
  )
}
```
As you run it and check the console on the browser you can see the massage.
What does useEffect do here is that when our component renders, useEffect runs the function code we wrote in it after the component rendering.

Now this example:
```jsx
import Card from "./components/Card";
import Custom_btn from "./components/Custom_btn";
import { useEffect, useState } from "react";

export default function App(){

  const [state,setState]=useState(0);
  useEffect(()=>{
    console.log("render");
  })
  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        <p className="p-2 text-xl">Handling side effects</p>
        {state}
        <Custom_btn label={"Update"} onClick={()=>setState(state+1)}/>
      </Card>
    </div>
  )
}
```
Now each time we press the button, the number on the page changes and the component gets
re-rendered and after the re-rendering the useEffect runs.

Now how can we stop the useEffect running after each re-render?
```jsx
import Card from "./components/Card";
import Custom_btn from "./components/Custom_btn";
import { useEffect, useState } from "react";

export default function App(){

  const [state,setState]=useState(0);
  useEffect(()=>{
    console.log("render");
  },[]);
  
  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        <p className="p-2 text-xl">Handling side effects</p>
        {state}
        <Custom_btn label={"Update"} onClick={()=>setState(state+1)}/>
      </Card>
    </div>
  )
}
```
What we did is we added something in the useEffect called a dependency array.

Now the useEffect will only trigger with the first rendering.
Dependency array is only for one time triggering. If we put state in it, it triggers again and again with each re-rendering.

##### When to use useEffects?
We only use useEffects when we want to manage some side effects. For example a request to server or changing DOM manually or storing data in local storage and etc.

You can have multiple useEffects in your component. But it's not really sufficient..
Handling errors after it is hard and it can affect the performance and ...

##### Changing DOM
```jsx
import Card from "./components/Card";
import Custom_btn from "./components/Custom_btn";
import { useEffect, useState } from "react";

export default function App(){

  const [state,setState]=useState(0);
  useEffect(()=>{
    console.log("render");
    document.title="React side effect";
  },[]);
  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        <p className="p-2 text-xl">Handling side effects</p>
        {state}
        <Custom_btn label={"Update"} onClick={()=>setState(state+1)}/>
      </Card>
    </div>
  )
}
```
As you look at the title, it has been changed by the useEffect manually.

*Note:* Use the useEffects at the top level of the component.