We learnt that when getting a data from the server or the back-end, the data isn't in the first rendering.
So SEO crawlers cannot see the whole content and data, in other words, our data is incomplete.

In SSR we mentioned that when the user visits the page, sends a request to the server, Server creates the HTML file and sends it rendered for the client.
#### SSG
SSG (static site generation) is one of the solutions.
SSR is divided in 2 methods: SSG and SSR. The 3rd form is the ISR which we'll talk about later.

Here we talk about the SSG which is pretty important among them because it is used more often.
##### How to use it
```tsx
import { MockNews } from "../constants/mock";
import NewsList from "../components/NewsList";
import { useEffect, useState } from "react";

export default function HomePage(){
	const [list,setList]=useState<any[]>([]);
	
	useEffect(()=>{
		//request to server to get latest news
		setList(MockNews);
	},[]);
	
	return(
		<div>
			<NewsList list={list}
		</div>
	)
}
```
After the function component ends, we write another function and export it:
```tsx
import { MockNews } from "../constants/mock";
import NewsList from "../components/NewsList";
import { useEffect, useState } from "react";

export default function HomePage(){
	const [list,setList]=useState<any[]>([]);
	
	useEffect(()=>{
		//request to server to get latest news
		setList(MockNews);
	},[]);
	
	return(
		<div>
			<NewsList list={list}
		</div>
	)
}

export const getStaticProps=()=>{
	return{
	
	}
}
```
The name should be `getStaticProps` because NextJs will look for it. When using this name for the function, we are declaring to NextJs that we intend to use the SSG method and NextJs understands it.

We never have to import this function, only NextJs needs it, so where is it called?

This function is never executed in the client side(your browser). So where and when? 
It gets executed in the **server** during the **build time**.
`npm run build` is the command when we want to put it live on the server for the first time.
In other words, in the production environment.

It also is saved in the development environment as well(`npm run dev` cause it gets compiled every time we make a change). 

*Note:* It should always return an object. The object is the data you get as a prop. The prop you are returning is also an object.

To see when it runs:
```tsx
import { MockNews } from "../constants/mock";
import NewsList from "../components/NewsList";
import { useEffect, useState } from "react";

export default function HomePage(props){
	console.log(props);
	const [list,setList]=useState<any[]>([]);
	
	useEffect(()=>{
		//request to server to get latest news
		setList(MockNews);
	},[]);
	
	return(
		<div>
			<NewsList list={list}
		</div>
	)
}

export const getStaticProps=()=>{
	console.log("The getStaticProps executed");
	return{
		props:{
			name:"test",
			list:[],
		},
	};
};
```
You can see only the props you used in the function component, is shown in the console.
But if you pay attention, you can see the message in the second function we tried to check, is printed in the terminal, before the Homepage message. 

The reason behind it is that the `getStaticProps` never runs in the browser. Only the build time or the development environment.
##### The solution we mentioned earlier
Now to solve our problem we need to fetch our data in the function, then use it in the function component.
This is an async work, and yes we can use the `async` here for the function.
```tsx
import { MockNews } from "../constants/mock";
import NewsList from "../components/NewsList";

export default function HomePage({list}){
	return(
		<div>
			<NewsList list={list}
		</div>
	)
}

export const getStaticProps=async()=>{
	console.log("The getStaticProps executed");
	return{
		props:{
			list:MockNews,
		},
	};
};
```
The list in the props part is an optional name. Then we destructured it in the Homepage function. 

Now if you check the **view page source** on the browser, you can see the datas.
##### The whole process
1. The developer writes the code
2. The source code turns into HTML, CSS, JS 
3. The contents are deployed in the hosting environment(server).
4. A user sends the request by typing the URL address or clicking on a link.
5. The request is sent to the server.
6. The server sends HTML, CSS, JS to the client.
7. The page is then displayed.