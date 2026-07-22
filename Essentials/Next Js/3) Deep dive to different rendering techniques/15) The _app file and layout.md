At the start, we were talking about the differences between NextJs and React. One of them that is remaining to talk about is the `_app` file in pages.
It exists in page router by default. 
```tsx
import type { AppProps } from "next/app";
  
export default function App({ Component, pageProps }: AppProps) {
  return <Component {...pageProps} />;
}
```
This is what you see. 

But let's make some changes for now:
```tsx
import type { AppProps } from "next/app";
  
export default function App({ Component, pageProps }: AppProps) {
  return <h1>Hello world</h1>
}
```

But if you open it now, you can see that there's only the hello world message though we made and saw our changes in the index file or in other words, we can't see the homepage we considered and designed in index file in pages folder.

Even if you type another route, you're still seeing the hello world message. Even a random route.

So the role of the `_app` file is that it's the main root of the whole project. Every page or components are rendered inside this file. 

It has 2 default input args: Components and pageProps. 

```tsx
import type { AppProps } from "next/app";
  
export default function App({ Component, pageProps }: AppProps) {
  return <Component {...pageProps} />;
}
```
Component is the file of the page that we want to see so it will replace the component. page props is for the component so it considers the props. 
##### Other use of `_app` file
One uses of the app file is considering a design for all pages like a layout for example or an style.

You can also use a context provider so you want all pages to have access to that context. 
For example design a layout:
```tsx
import type { AppProps } from "next/app";
  
export default function App({ Component, pageProps }: AppProps) {
  return(
    <Layout>
      <nav>
        <li>Home</li>
        <li>News</li>
        <li>About us</li>
      <Component {...pageProps} />;
    </Layout>
  )
}
```
Now you can see your changes in every page and route.
*!Note:* Adding more logics in this page will result in an slower rendering, cause this page is the root and renders every page. 