To understand the `getStaticProps` function better, let's do some more example.
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
  };
};
```
Considering this code and we added a time variable to show it. Use the `npm run build`. It will check if the project has any errors or type errors, then eventually builds it. Then you can use the `npm start` command to see your project.
Here's the catch, when making a difference on code, you can't see the changes, so you need to build the project again. 

Here in this example, considering that we used and showed the time and news from an api, neither the time, nor the news data will change due to the fact that time is always passing or the news data always replaces with new ones. On the other hand it's not efficient to rebuild and rebuild and ... . 

If the datas are static, or for example gets some updates after a while like a week or so, we can rebuild and produce the project.

But we have a news website, every 5 mins there is a new event, we can't rebuild the project.

Here NextJs comes to save the day.
We can add s.th beside the prop, and that is the `revalidate` attribute.
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
```
The number is in `seconds`. Not milli secs.
Now if you refresh, you can see the changes.