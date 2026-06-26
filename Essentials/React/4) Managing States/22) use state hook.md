We talked about **use states** before, but let's get it to a real action!

Here's an example. There's an image and a button and we want to make the image disappear when the button is pressed.

In components folder create:
`Card.jsx`
```jsx
export default function Card({children}){
    return(
        <div className="bg-white/65 backdrop-blur-md min-h-36 rounded-xl p-4 flex flex-col items-center w-1/3">
            {children}
        </div>
    );
};
```

`Custom_btn.jsx`
```jsx
export default function Cutsom_btn({label,onClick}){
    return(
        <button
            className="bg-green-500 px-2 py-1 rounded-lg text-white font-semibold text-md h-8 min-w-16 mt-4 hover:bg-gray-800"
            onClick={onClick}
        >
            {label}
        </button>
    );
};
```

Then the `App.jsx`
```jsx
import Custom_btn from "./components/Custom_btn";
import Card from "./components/Card";
import reactImage from "./assets/react.svg";
  
export default function App(){
  
  let visible=true;
  
  const handle_toggle=()=>{
    visible=!visible;
  }
  
  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        {visible ? <img src={reactImage} height="80px" width="80px"/> : null}
        <Custom_btn label="Toggle" onClick={handle_toggle}/>
      </Card>
  
    </div>
  )
}
```
So we made a variable named visible. And a function to change it's value. 
But when we press the button, it won't change because the variable is only meant for the scope so the virtual Dom will never realize the change. It actually never tracks the variables you create in the components.

What is the solution? Well you guess it. States. Yeppie :)
As you remember, state is the current value and the set state will change it's value.

```jsx
import Custom_btn from "./components/Custom_btn";
import Card from "./components/Card";
import reactImage from "./assets/react.svg";
import { useState } from "react";
  
export default function App(){
  
  const [visible,set_visible]=useState(true);
  
  const handle_toggle=()=>{
    set_visible(!visible);
  }

  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        {visible ? <img src={reactImage} height="80px" width="80px"/> : null}
        <Custom_btn label="Toggle" onClick={handle_toggle}/>
      </Card>
  
    </div>
  )
}
```
Now it works.

When changing an state. the Dom changes as well and the re-rendering occurs.

Now let's add a p tag there:
```jsx
import Custom_btn from "./components/Custom_btn";
import Card from "./components/Card";
import reactImage from "./assets/react.svg";
import { useState } from "react";
  
export default function App(){
  
  const [visible,set_visible]=useState(true);
  let counter=0;
  
  const handle_toggle=()=>{
    set_visible(!visible);
    counter++;
  }

  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        {visible ? <img src={reactImage} height="80px" width="80px"/> : null}
        <p>{counter}</p>
        <Custom_btn label="Toggle" onClick={handle_toggle}/>
      </Card>
  
    </div>
  )
}
```
So now we expect that each time we toggle the button, the counter shows us the count but as you see, it remains at the 0 value. It's because each time you change the state, the component gets re-rendered which means the values are reset to their initial value, now the question is why the values in the states such has visible here doesn't reset?

It's because that the state's values are stored somewhere else, beside the component. React will keep them stored until the component is visible on the browser page.

set state updates states in async way, means that the result takes some time.

*!Note:* Remember to never put the state in an if condition or in a return scope.

**How to put some operations in the initial state?**
```jsx
const [visible,set_visible]=useState(()=>{
	if(counter>5) return true;
	else return false;
});
```
Remember to put a return as well.
Pressing the button several times won't change the initial amount a second time or more!

The other method to use set state is this:
```jsx
  const handle_toggle=()=>{
    set_visible((prev)=>{
      return !prev;
    });
    counter++;
  }
```
