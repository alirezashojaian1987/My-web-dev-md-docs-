When having a styled page, if you want to navigate using the components inside it, you need to use `<Link>` tag wrapper for all the components. This will messes some styles. 

So the right approach is to just use `useRouter()`. 
```tsx
const router=useRouter();

<div className={styles.card} onClick={()=> router.push("/path")}
```

