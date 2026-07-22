Considering the news project, because our route is dynamic, we can't just say hey, let's get the news in the `[0]` part. 
So to solve this, we need to access the URL which is getting a path out of it, and to do so we can use the context we talked about before:
```tsx
export const getStaticProps=async(context)=>{
	const {newsId}=context.params;
	return{
		props:{
			news:MockNews[newsId],
		}
	}
}
```
*!Note:* Hooks in React(`useState`, `useEffect`, `useRouter`, and etc.) will never work in these functions. Because as we mentioned before, these functions are actually server codes and are executed in the server. 

Considering that you used the code format above for your news project, when you type the `/1` or other paths to open a news, you will face an error which says: `getStaticPaths is required for dynamic SSG pages and is missing for /[newsId].`

newsId is the page we named for being the dynamic page for us, the problem here is the SSG which we mentioned that it's an static page and is pre-generated during the build time, cached and then is sent for the client, so this is why the error occurred. It being an static page.

But we want it to be dynamic as well.

To fix the error above, we can use one other function from NextJs and that is:
```tsx
export const getStaticPaths=()=>{
	return{
		paths:[
			{params:{newsId:"0"}},
			{params:{newsId:"1"}},
			{params:{newsId:"2"}},
			{params:{newsId:"3"}},
		]
	}
}
```
This function is one of the functions that are used in SSG pages, and the NextJs calls it. 
It is called during the build time of the project. We need to declare the amount of paths for NextJs.
It returns an array called paths, and for each path we need to return an object that has params and that params has an object that we use our id inside it

Here we declared for NextJs that we have 4 pages. 
In real projects, we fetch, then we use `map()`.
*!Note:* The ids must be string and not number types.

Doing this and then opening the page again on the browser results in another error.
`Error: The fallback key must be returned from getStaticPaths in [newsId]`
```tsx
export const getStaticPaths=()=>{
	return{
		paths:[
			{params:{newsId:"0"}},
			{params:{newsId:"1"}},
			{params:{newsId:"2"}},
			{params:{newsId:"3"}},
		],
		fallback:true
	}
}
```
We need to use this arg as well, it can be `true` or `false`. 

When declaring false, we are telling NextJs there are no pages with other ids rather than the ones we declared for it.

When using `true`, we are telling NextJs that besides these pages that we declared for you, there might be some updates and some other pages. It sends an empty HTML and then tries to regenerate it, but it can result in error since it may not receive all the data at first.

So we can use the `blocking` string value for it. It's like `true` but tells NextJs that unless the data is not ready, don't send it. 