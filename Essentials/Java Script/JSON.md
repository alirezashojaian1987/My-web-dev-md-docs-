JSON stands for **Java script object notation**. It's mainly used for storing and transporting data to a server or a web page.
```json
{
    "Products":[
        {
            "id":1,
            "title":"Laptop",
            "price":90000000
        },
  
        {
            "id":2,
            "title":"Phone",
            "price":50000000
        },
  
        {
            "id":3,
            "title":"Airpods",
            "price":9000000
        }
    ]
}
```
##### JSON syntax rules
- Data is in name/value pairs
- Data is separated by commas
- Curly braces hold objects
- Square brackets hold arrays
##### JS object notation
The JSON format is syntactically identical to the code for creating JavaScript objects.
Because of this similarity, a JavaScript program can easily convert JSON data into native JavaScript objects.
##### A name and a value
JSON data is written as name/value pairs, just like JavaScript object properties.
A name/value pair consists of a field name (in double quotes), followed by a colon, followed by a value:
```json
"firstName":"John"
```
##### Converting object to Json and vice versa
We mentioned that a json is similar to an obj. But with some differences.
To convert a Js object into a json, we can use this method:
```js
const user={
    id:1,
    name:"Alireza",
    age:22,
    address:{
        country:"Iran",
        city:"Mashhad",
    },
};
  
const JsonUser=JSON.stringify(user);
```

To convert a Json into an obj:
```js
const ObjUser=JSON.parse(JsonUser);
```
