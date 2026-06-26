The previous practice we had, has a little point, and that is if you put a console log in the code and run in the browser, whenever you type, the console prints it 2 times for each character you type.
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

  //console.log()
  console.log(value,"Value")

  const add=()=>{
    setList([...list,value]);
  }

  const remove=()=>{
    setList(list.filter(item=>item!==value));
  }

  const handleChangeInput=(e)=>{
    setValue(e.target.value)
  }

  const update=()=>{
    setList(list.map(item=>{
      if(item===value){
        return item+"js";
      }
      else return
    })
    );
  }

  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        <img src={reactImage} height="80px" width="80px"/>
        <div className="flex items-center gap-2">
          <Custom_input label="Tech name" value={value} onChange={handleChangeInput}/>
          <Custom_btn label="Add" onClick={add}/>
          <Custom_btn label="Remove" onClick={remove}/>
          <Custom_btn label="Update" onClick={update}/>
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

As you remember, in the main code the App tag is between to `StrictMode` tags. This actually helps you track and find bugs in your development environment.
The 2 time printing in the console is actually only in the development environment, Because of the strict mode, which is trying to help you track bugs.

Each state and each function runs 2 times.
The first time is for the React insuring that the state is changing and the second time is for the virtual DOM to change that state.

When you build the project eventually, everything goes back to normal and the 2 times run is onl for the strict mode.