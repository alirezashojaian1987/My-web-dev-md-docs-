There are times that you have more than one state in your component, which has so many values and they are irrelevant towards other.

Let's go with the last example, just make these changes in the App file.
```jsx
import Custom_btn from "./components/Custom_btn";
import Card from "./components/Card";
import Custom_input from "./components/Custom_input";
import reactImage from "./assets/react.svg";
import { useState } from "react";

export default function App(){

  const [visible,set_visible]=useState(true);
  const [counter,set_counter]=useState(0);
  
  const [name,set_name]=useState("ali");
  const [address,set_address]=useState("fakori");
  const [mobile,set_mobile]=useState("0915");

  const handle_toggle=()=>{
    set_visible(!visible);
    set_counter(counter+1);
  }

  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        {visible ? <img src={reactImage} height="80px" width="80px"/> : null}
        <Custom_input label="name:" value={name}/>
        <Custom_input label="address:" value={address}/>
        <Custom_input label="mobile:" value={mobile}/>
        <Custom_btn label="Toggle" onClick={handle_toggle}/>
      </Card>

    </div>
  )
}
```

Consider you want to store the input values in states, as mentioned before we are not limited on using states but it's not sufficient. Because tracking them will be hard, you need to be very careful when changing them and etc... and it has so many repeated code lines.

So you can actually use objects.
```jsx
import Custom_btn from "./components/Custom_btn";
import Card from "./components/Card";
import Custom_input from "./components/Custom_input";
import reactImage from "./assets/react.svg";
import { useState } from "react";

export default function App(){

  const [visible,set_visible]=useState(true);
  const [counter,set_counter]=useState(0);

  const [form_state,set_form_state]=useState({
    name:"Ali",
    address:"Fakori",
    mobile:"0915"
  })

  const handle_toggle=()=>{
    set_visible(!visible);
    set_counter(counter+1);
  }

  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        {visible ? <img src={reactImage} height="80px" width="80px"/> : null}
        <Custom_input label="name:" value={form_state.name}/>
        <Custom_input label="address:" value={form_state.address}/>
        <Custom_input label="mobile:" value={form_state.mobile}/>
        <Custom_btn label="Toggle" onClick={handle_toggle}/>
      </Card>

    </div>
  )
}
```

You can even put the visible variable inside it and now you may ask how can we change it? If you use `set_form_state(false)`, every value gets cleared, because the set state is for all the state. what you need to do is this:
```jsx
export default function App(){

  const [counter,set_counter]=useState(0);

  const [form_state,set_form_state]=useState({
    name:"Ali",
    address:"Fakori",
    mobile:"0915",
    visible:true,
  })

  const handle_toggle=()=>{
	  set_form_state({...form_state,visible:!form_state.visible})
  }

  return(
    <div className="flex items-center justify-center h-[100vh] w-full">
      <Card>
        {form_state.visible ? <img src={reactImage} height="80px" width="80px"/> : null}
        <Custom_input label="name:" value={form_state.name}/>
        <Custom_input label="address:" value={form_state.address}/>
        <Custom_input label="mobile:" value={form_state.mobile}/>
        <Custom_btn label="Toggle" onClick={handle_toggle}/>
      </Card>

    </div>
  )
}
```
the `...` means that keep the previous as before, and change after the requested parameter.(It actually gets a copy and then overwrite it with the new one)

You can do it with this way as well:
```jsx
const handle_toggle=()=>{
  set_form_state((prev)=>{
	  return {...prev,visible:!prev.visible}
  })
}
```