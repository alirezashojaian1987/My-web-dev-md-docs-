Now that we learnt about the context, we can have a little more practice.
Now we want to create an auth page with context.

Create a folder in pages and a file named Login.
```jsx
import Button from "../../components/Button/Button";
export default function Login(){
    return(
        <div>
            <h1>Login page</h1>
            <Button>Login</Button>
        </div>
    )
}
```

Then a new context file called AuthContext in the context folder.
```jsx
import { createContext,useState } from "react";

export const AuthContext=createContext();

export default function AuthContextProvider({children}){
    const [auth,setAuth]=useState(null);

    return(
        <AuthContext.Provider value={{auth,setAuth}}>
            {children}
        </AuthContext.Provider>
    )
}
```

Now we need to use it's wrapper in our main file. The reason behind it is that we want every component to have access on our auth context.
```jsx
import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import { RouterProvider } from "react-router-dom";
import { router } from "./routes/routes"
import AuthContextProvider from './Context/AuthContext';

createRoot(document.getElementById('root')).render(
  <StrictMode>
    <AuthContextProvider>
      <RouterProvider router={router}/>
    </AuthContextProvider>
  </StrictMode>,
)
```

Then style your navbar however you like.

In your login page:
```jsx
// import styles from "./Login.module.scss";
import Button from "../../components/Button/Button";
import { useContext } from "react";
import {AuthContext} from "../../Context/AuthContext";

export default function Login(){

    const {auth,setAuth}=useContext(AuthContext);

    return(
        <div>
            <h1>Login page</h1>
            <Button onClick={()=>setAuth({user:"Alireza",id:1987})}>Login</Button>

            {auth?.user?<div>{auth?.user}</div>:null}
        </div>
    )
}
```