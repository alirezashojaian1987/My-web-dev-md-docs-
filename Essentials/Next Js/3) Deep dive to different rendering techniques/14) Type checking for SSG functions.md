To do the type checking on the get static props function and etc. You can do this:
```tsx
import { GetStaticProps } from "next";

export const getStaticProps:GetStaticProps=async()=>{}

export const getServerSideProps:GetServerSideProps=async()=>{}
```
It helps us to work easier with these functions.
*Note:* Remember to use only one of those at a time in a page.