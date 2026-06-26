As we talked about an object of states, here we want to see how we can use array of states as well.
```jsx
import Custom_btn from "./components/Custom_btn";
import Card from "./components/Card";
import Custom_input from "./components/Custom_input";
import reactImage from "./assets/react.svg";
import { useState } from "react";

export default function App(){

  const [value,setValue]=useState("");
  const [list,setList]=useState([
    "HTML",
    "CSS",
    "JavaScript",
    "TypeScript",
    "React"
  ]);

  const add=()=>{

  }

  const remove=()=>{
    
  }

  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        <img src={reactImage} height="80px" width="80px"/>
        <div className="flex items-center gap-2">
          <Custom_input label="tech name" value={value}/>
          <Custom_btn label="add" onClick={add}/>
          <Custom_btn label="remove" onClick={remove}/>
        </div>

        <ul className="my-5 flex flex-col gap-2 items-center">
          {list.map((item)=>(
            <li key={item}>{item}</li>
          ))}
        </ul>
      </Card>
    </div>
  )
}
```
We want to add, remove and update elements in the array shown.
 ```jsx
 
 ```