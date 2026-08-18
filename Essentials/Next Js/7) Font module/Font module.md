Let's talk about how we can import some fonts in our Next project.

NextJs has 2 optimized methods for fonts.
+ The fonts that are installed locally
+ The fonts that are imported from google and etc.
There are some differences but minor.
##### Local method
Inside the `layout.tsx` file:
```tsx
import localFont from "next/font/local";

const primaryFont=localFont({
	src:"../assets/fonts/GeistVF.woff" //The path of your font and the name
	//or
	src:[
		{
			path:"../assets/fonts/GeistVF.woff",
			weight:"700", //and other styles
		}
	]
})
```

You can also set a variable name for it(optional):
```tsx
import localFont from "next/font/local";

const primaryFont=localFont({
	src:"../assets/fonts/GeistVF.woff", //The path of your font and the name
	variable:"--primary-font",
})
```

Now to use it:
```tsx
export default function RootLayout({
  children,
}: Readonly<{
  children: React.ReactNode;
}>) {
  return (
    <html lang="en">
      <body
        className={`${primaryFont.className} antialiased`}
      >
        {children}
      </body>
    </html>
  );
}
```
##### Link method
Inside the `layout.tsx` file:
```tsx
import {} from "next/font/google";

const robotoFont=Roboto({
	weight:["400","500","700"],
	variable:"--roboto-font",
	preload:true, //or false,
})
```