Sometimes we have a separate component that it's on different layer and we want work with it from different component for example in the shop project we have the products page and we have a cart page.

We learnt that when saving a value in a state and we want to share that state, we need to include it in upper layers so that all child layers have access to it. 

For example if we want our components to access the state, we need to put it on the top layer and then we need to pass it so many times till it gets to the component we want which is on the lower layers. This passing is an anti-pattern cause you're passing a function to lower layers each time.
This will result in re-render for all of the components. 
Also some of the components may not even need it!

This whole situation is called **Props drilling** that we mentioned before.

We can use a tool and a hook from React called **Context**.
##### Context introduction
For start, create a folder called Context, then a jsx file called the same name.
```jsx
import {createContext} from "react";

export const cartContext=createContext();

export const cartProvider=({children})=>{
	
}
```
The function above has a default value argument(you can either set it or not).
When using `.`, it show 3 properties: `consumer, provider, displayName`

Now let's talk about context.
Context is a **global** state which you can use in the top layers of your project and it's not a function or a component **exclusive**.

When using **useStates**, they're only excluded for their own component where they're declared.
(Yes you can pass it as props, but the parent can't access it and the child layers... well you know what happens).

Components can access the values in the context and can change them.
##### Working with context
Here in this example, we want our navbar page and item details page to access our context, when pressing the add to cart button, the state in the context gets a change.

Remember we created a page called layout?(Which also was a shared component between others)
Now we can use our context in it.
```jsx
import { Outlet } from "react-router-dom";
import styles from "./Layout.module.scss";
import Navbar from "../Navbar/Navbar";
import {cartContext} from "../../Context/Context";

export default function Layout(){
    return(
      <cartContext.Provider>
        <div className={styles.layout}>
          <Navbar/>
          <Outlet/>
        </div>
      </cartContext.Provider>
  )
}
```
Provider acts a new scope that includes data in itself. The datas in it such as the navbar or the outlet can consume from it.

The context gives us a value which can be in a form of an object and we can give it datas in object form.
```jsx
import { Outlet } from "react-router-dom";
import styles from "./Layout.module.scss";
import Navbar from "../Navbar/Navbar";
import cartContext from "../../Context/Context";
import { useState } from "react";

export default function Layout(){

  const [cartItems,setCartItems]=useState([]);

    return(
      <cartContext.Provider value={{cartItems,setCartItems}}>
        <div className={styles.layout}>
          <Navbar/>
          <Outlet/>
        </div>
      </cartContext.Provider>
  )
}
```

Now to use our context in different pages.
In old method, you could use the `context.consumer` wrapper tag and include all your tags in it to become consumers.

First you need to import the `useContext` hook.
In your itemDetails page:
```jsx
import {useContext} from "react";
import {cartContext} from "../../pages/context/context";
export default function test(){
	const {cartItems,setCartItems}=useContext(cartContext);
	
	return(
		//...
	<Button ... onClick={()=>setCartItems((previtems)=>([...previtems,product]))}
	)
}
```
Now the item is added in your cartItem variable you declared. You can check it's contents in different page with console.

*Note:* Remember, using context many times in your project may result in your slow rendering, cause every component that has used context inside it, re-renders after each set context.

*Note:* Remember to choose a good name for your context so when you see it, you realize what it's for. 
Context is often used for theme(dark/light), multi language options, ...

*Note:* You can also create all your context in one place, not needing layout page to contain some of it's logic or the others.

In your context file
```jsx
import {createContext,useState} from "react";

export const cartContext=createContext();

const CartContextProvider=({children})=>{
	const [cartItems,setCartItems]=useState([]);
	
	return(
	  <cartContext.Provider value={{cartItems,setCartItems}}>
		  {children}
      </cartContext.Provider>
	)
}
```

Now in your layout:
```jsx
import { Outlet } from "react-router-dom";
import styles from "./Layout.module.scss";
import Navbar from "../Navbar/Navbar";
import cartContext from "../../Context/Context";
import { useState } from "react";

export default function Layout(){

  const [cartItems,setCartItems]=useState([]);

    return(
      <cartContext.Provider>
        <div className={styles.layout}>
          <Navbar/>
          <Outlet/>
        </div>
      </cartContext.Provider>
  )
}
```
