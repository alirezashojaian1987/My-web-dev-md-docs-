We have this code:
```tsx
import { MockNews } from "../constants/mock";
import NewsList from "../components/NewsList";

export default function HomePage(){
	return(
		<div>
			<NewsList list={MockNews}
		</div>
	)
}
```

We don't want to store all datas in front side. We may have back-end datas so we used to do this:
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
*Note:* This is just a simple simulation.

As mentioned before, the main reason we use NextJs is because of the SEO. 
In React, when using the **view page source** option on the browser, it wouldn't show what we designed, there's an HTML with only a div which has a root as the id. 
The other contents were requested from the server to be retrieved and then render.

In NextJs however, all pages get pre-generate. In other words, all contents and pages are pre-generated and then are sent to the browser. The retrieved html is pre-generated, which means when opening **view page source** option, it shows the html with all contents. 

Here's another problem, when opening the option, you can see that some divs that you only used some mock datas inside them, don't show anything and are empty, now put a h1 tag for test, and now you can see it's no longer empty. 

We don't always have our datas in the first place and can take some time to get them.

We talked about this earlier in React, when rendering, there are some major cycles of rendering in React. One of the main one is the `return()` part which renders the whole component.

`useEffect()` on the other hand, isn't inside the first phase of the rendering because it's a side effect. 
The function component and the return inside it are run first. Then the side effect.

In SEO, this component is put in the view page source, but the data that can be retrieved later, isn't.
##### Solution
To fix this problem, we need to take care of it in order to improve the SEO.
We are trying to prevent NextJs to send the whole content until the data is retrieved.

