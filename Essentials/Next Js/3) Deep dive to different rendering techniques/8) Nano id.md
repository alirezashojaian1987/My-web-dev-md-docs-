It's better for the components folder to be in the root of the project same as pages folder when we are using pages routing system for next js. 
##### Generating random keys for mapping
When mapping some data from objects, mock data files, api responses or json files, the data may not have a unique value to use it as a key. Also we mentioned that using index is not a proper option. It can cause troubles.
So we can use a tool that can generate keys for us and that is `Nano id` package. 
##### Installation
Open the terminal in the project directory and type:
```bash
npm i nanoid
```
##### How to use it
An example code to show it:
```tsx
import { MockNews } from "../constants/mock";
import { nanoid } from "nanoid";

export default function NewsList(){
	return(
		<div>
			<h1>News</h1>
			<div>
				{MockNews.map((news)=>(
					<div key=nanoid()>{news.title}</div>
				))}
			</div>
		</div>
	)
}
```
We can use `nanoid()` method which can generate us a unique key value. 
You can also set a default symbol amount, it's 20 or upper by default. But you can just put any amount in the function's arguments when your data is limited: `nanoid(3)`.

