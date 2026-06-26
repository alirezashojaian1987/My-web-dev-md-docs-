We learnt that useEffect only runs when our component renders for the first time and also with a dependency array, it reacted with every change based on the dependency we defined for it.

One of the other things it does is the **Clean up** matter.
```jsx
import Card from "./components/Card";
import Custom_btn from "./components/Custom_btn";
import { useEffect, useState } from "react";

export default function App(){

  const [state,setState]=useState(0);

  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        <p className="p-2 text-xl">Handling side effects</p>
        {state}
        <CountDown/>
        <Custom_btn label={"Update"} onClick={()=>setState(state+1)}/>
      </Card>
    </div>
  )
}

const CountDown=()=>{
  const [count,setCount]=useState(1000);
  
  useEffect(()=>{
    setInterval(()=>{
      setCount((count)=>count-1);
    },1000);
  });

  return <div className="text-xl text-blue-700 p-3">{count}</div>
}
```
When you run this, you can see that there's no one second count down and the value is reducing faster each time so we actually are in an infinite loop.

Now adding an empty dependency array to the useEffect will prevent this and as you run it, you can see that it's reducing the value every second by two(It reduces the value by two because of the Strict mode we mentioned before...).

##### Using the clean up
Remember that we mentioned when using intervals in JS, they run forever.

Here in this example, when we don't need the count down component and don't want to show it anymore, we need to clear the interval because it's still running in the browser.

Consider this example:
```jsx
import Card from "./components/Card";
import Custom_btn from "./components/Custom_btn";
import { useEffect, useState } from "react";

export default function App(){

  const [state,setState]=useState(true);

  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        <p className="p-2 text-xl">Handling side effects</p>
        {state && <CountDown/>}
        <Custom_btn label={"Toggle"} onClick={()=>setState(!state)}/>
      </Card>
    </div>
  )
}

const CountDown=()=>{
  const [count,setCount]=useState(1000);
  
  useEffect(()=>{
    setInterval(()=>{
      setCount((count)=>count-1);
    },1000);
  },[]);

  return <div className="text-xl text-blue-700 p-3">{count}</div>
}
```
It's true that when we press the button, the count down starts again, but here's the problem.
The previous interval is still running in the memory so it eventually affects the performance.

So the clean up of the useEffect comes to our rescue.
```jsx
import Card from "./components/Card";
import Custom_btn from "./components/Custom_btn";
import { useEffect, useState } from "react";

export default function App(){

  const [state,setState]=useState(true);

  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        <p className="p-2 text-xl">Handling side effects</p>
        {state && <CountDown/>}
        <Custom_btn label={"Toggle"} onClick={()=>setState(!state)}/>
      </Card>
    </div>
  )
}

const CountDown=()=>{
  const [count,setCount]=useState(1000);
  
  useEffect(()=>{
    const interval=setInterval(()=>{
      setCount((count)=>count-1);
    },1000);

    return ()=>{
      clearInterval(interval);
    }

  },[]);

  return <div className="text-xl text-blue-700 p-3">{count}</div>
}
```
Easy, simple.

We can use this method for sending long term requests as well. What we mean is sometimes you send a request but it takes some time and you are impatient and leave the section or close the tab while requesting. So we need to clear that as well.