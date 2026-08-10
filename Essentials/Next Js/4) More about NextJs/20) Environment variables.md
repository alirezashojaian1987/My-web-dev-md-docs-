When working on a real project, let's say we want to use api endpoint in many places. Also maybe our url can be pretty much different in each code file.
We can use env file. 
There's also a doc in NextJs. 
##### How to use env
Create a file inside your project folder called `.env` 
If you are working on a local project, you can name it `.env.local`
If on production: `.env.production` Next will realize it. 

You can use addresses, keys, secret urls and etc.
*!Note:* Remember to put it inside the git ignore as well.
```env
BASE_URL="https://contentURL"
```
