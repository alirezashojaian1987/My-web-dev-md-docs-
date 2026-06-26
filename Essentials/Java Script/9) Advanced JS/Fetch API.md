```js
function getter(){
    fetch("https://jsonplaceholder.typicode.com/users/1") //API endpoint
        .then((response)=>response.json()) //Parse the JSON from the response
        .then((data)=>{
            document.getElementById("UserData").innerHTML=
                // "<p>Name: "+ data.name+ "</p>";
                console.log(data);
        })
        .catch((error)=>{
            document.getElementById("UserData").innerHTML=
                // "<p>An error occured while fetching data.</p>";
                console.log(error);
        });
}
  
getter();
```