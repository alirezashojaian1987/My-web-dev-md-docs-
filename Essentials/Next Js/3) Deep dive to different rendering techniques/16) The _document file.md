We talked about the `_app` file. Now let's talk about the `_document` file. It's pretty much different.

It builds the main structure of the HTML file. It renders in the server. 
You can add some meta datas in the `<Head/>` file. Or some languages for the better SEO. 

`<Main>` is the tag that contains all your pages and components. `<NextScript>` is for some NextJs logics.

You can't use the SSG functions here.

```tsx
import { Html, Head, Main, NextScript } from "next/document";
  
export default function Document() {
  return (
    <Html lang="en">
      <Head />
      <body>
        <Main />
        <NextScript />
      </body>
    </Html>
  );
}
```
