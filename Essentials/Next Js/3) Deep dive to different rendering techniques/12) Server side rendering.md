Now we know about the ISR, sometimes we have to update our data after some seconds, in other words, the update rate is pretty much high. So we have another solution and that is SSR.
##### How to use SSR
To use SSR we have to use another function:
```tsx
import { News } from "@/constants/mock";
import NewsList from "@/components/NewList";
  
export default function Home({list,time}){
  return (
    <div>
      <NewsList list={list}/>
      <p>{time}</p>
    </div>
  );
}
  
export const getStaticProps=async()=>{
  console.log("The getStaticProps executed");
  const date=new Date();
  return{
    props:{
      list:News,
      time:date.toTimeString(),
    },
    revalidate:100,
  };
};

export const getServerSideProps=async()=>{
	const date=new Date();
	return{
		props:{
		  list:News,
		  time:date.toTimeString(),
		},
	};
}
```
The name is important here as well. The function can also be async.
Like previous function, it returns an object that has props.
The key difference here is that we no longer use the `revalidate`. 

The server side props function doesn't get called during the build time, it runs when a request is sent from a client to the server.

The retrieved data is always updated.

When you refresh the page, you can see the changes. 
##### Context in SSR
```tsx
export const getServerSideProps=async(context)=>{
	const date=new Date();
	const res=context.res;
	const req=context.req;
	
	return{
		props:{
		  list:News,
		  time:date.toTimeString(),
		},
	};
}
```
This function can get an arg called context, this is a long object if you put it in console, 
two properties that are important here are request(req) and the response(res). 

By accessing them, you can change or check your request.(Header, body, token and etc.).

