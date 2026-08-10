When trying to fetch datas from an API, it's good to always have a log in your code first, in order to check the contents of the response of the api, to check whether the request was successful, the contents and etc.
```tsx
export const getStaticProps:GetStaticProps=async()=>{
	let list=[];
	
	const response=await fetch("https://content.....");
	
	const responseData=await response.json();
	
	console.log(responseData);
	
	if(responseData.response.status==="ok"){
		list=responseData.response.results;
	}
	
	return{
		props:{
			list:MockNews,
		}
	}
}
```
After `console.log()` you can check the terminal and see what it actually returned. For example you can see there's an object which is response, the attribute called `status` inside it has an `ok` value. And there's also an attribute called results, which can be multiple objects. Those are the datas you need. 

*!Note:* Because we're using `async` function, it may result in success or rejection, so it's always necessary to use `try, catch` in order to prevent some crash or errors to occur.
```tsx
export const getStaticProps:GetStaticProps=async()=>{
	let list=[];
	
	try{
		const response=await fetch("https://content.....");
		
		const responseData=await response.json();
		
		console.log(responseData);
		
		if(responseData.response.status==="ok"){
			list=responseData.response.results;
		}
		
		return{
			props:{
				list,
			}
		}	
	}
	
	catch(error){
		return{
			props:{
				list:[],
				error:JSON.stringify(error),
			}
		}
	}
}
```