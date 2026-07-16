An **object** is a variable that can hold many variables.
Objects are collections of **key-value pairs**, where each key (known as **property names**) has a value.

##### JS Objects
This code assigns many values to an object named car:
```js
const car={type:"Volvo",color:"White"};
```
You should declare objects with the const keyword.
When an object is declared with const, you cannot later reassign it to point to a different variable.
It does not make the object unchangeable. You can still modify its properties and values.

##### How to create a JS Object
An object literal is a list of **key : value** pairs inside curly braces **{ }**:
```js
{firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}
```
In object terms, the **key : value** pairs are the **object properties**.
**Spaces and line breaks** are not important. An object literal can span multiple lines.
```js
const person = {  
  firstName: "John",  
  lastName: "Doe",  
  age: 50,  
  eyeColor: "blue"  
};
```

You can also create an **empty object**, and add the properties later:
```js
const person=new Object();
person.name="Ali"; //This adds a name key with the "Ali" value
person.age=21; //This adds a age key with the 21 value
console.log(person);
```

##### Using the `new` keyword
```js
const person = new Object({  
  firstName: "John",  
  lastName: "Doe",  
  age: 50,  
  eyeColor: "blue"  
});
```
```js
const car=new Object();
car.color="red";
car.speed=200;
```
All the examples above do exactly the same.
There is no need to use `new Object()`.
For readability, simplicity and speed, use an **object literal** instead.

##### Object properties
You can access object properties in two ways:
```
objectName.propertyName
```
```
objectName["propertyName"]
```

```js
person.lastName;
```
```js
person["lastName"]
```

Object methods are actions that can be performed on objects.
Object methods are function definitions stored as property values. In other words, every function that is defined inside an object is called the object's method:
```js
const person = {  
  firstName:"John",  
  lastName:"Doe",  
  id:5566,  
  fullName:function(){  
    return this.firstName + " " + this.lastName;  
  }  
};
```
In the example above, `this` refers to the **person object**:
**this.firstName** means the **firstName** property of **person**.
**this.lastName** means the **lastName** property of **person**.

##### How to delete a key?
You can use `delete` keyword to remove a key and also the object itself.
```js
delete person.fname;
```
##### How to display JS Objects?
Displaying a JavaScript object will output **[object Object]**.
```js
const person = {  
  name: "John",  
  age: 30,  
  city: "New York"  
};  
  
let text = person;
```

**Displaying Object properties:**
The properties of an object can be added in a string:
```js
const person = {  
  name: "John",  
  age: 30,  
  city: "New York"  
};  
  
// Add Properties  
let text = person.name + "," + person.age + "," + person.city;
```

**Using for loop:**
```js
const device={
    name:"Asus",
    price:"800$",
    weight:"2kg",
    config:{
        ram:16,
        hdd:500,
    },
};

for(let key in device){
    console.log(key,device[key]);
}
```

##### Object constructor and factory functions
Sometimes we need to create many objects of the same **type**. It's not really ideal to use same codes over and over. So we can use a **Constructor function** 
To create an **object type** we use an **object constructor function**.
```js
function Person(first, last, age, eye) {  
  this.firstName = first;  
  this.lastName = last;  
  this.age = age;  
  this.eyeColor = eye;
  this.greet=function(){
      console.log("Hello nice to meet you")
  }
}
```
In the constructor function, `this` has no value.
The value of `this` will become the new object when a new object is created.

Now we can use `new Person()` to create many new Person objects:
```js
const myFather = new Person("John", "Doe", 50, "blue");  
const myMother = new Person("Sally", "Rally", 48, "green");  
const mySister = new Person("Anna", "Rally", 18, "green");  

const mySelf = new Person("Johnny", "Rally", 22, "green");
```
What does `new` do is that it first creates an empty object, `this` keyword has the reference of the empty object that is created and assigns the values to it.

**Factory functions:**
```js
function cars(price,hp,topSpeed,color){
	return{
		price,
		hp,
		topSpeed,
		color,
		move(){
			console.log("Moving");
		},
		
		break(){
			console.log("Using breaks");
		},
	}
}

const car1=cars("3000$",4000,250,"red");
```

##### Cloning & extending an object
One of the simple way is using keys method in a for loop:
```js
const device={
    name:"Asus",
    price:"670$",
    weight:"1.2kg",
    config:{
        ram:16,
        hdd:500,
    },
};
  
const clone={};
  
for(let key in device){
    clone[key]=device[key];
};

console.log(clone);
```
The shorter way is using `Object.assign()` method.
```js
const clone=Object.assign({},device);
  
console.log(clone);
```
This method gets 2 arguments, first one is target which here is an empty object, and the second one is source arg, which here is the object we want the copy from it.
In order to extend the object, we can set the object itself in the 1st argument:
```js
const device2={
    capacity:5000,
    color:"red",
};
  
const clone=Object.assign(device2,device);
  
console.log(clone);
```
With this approach you can extend your object.
The simplest way possible is using 3 dots:
```js
const clone={...device};
  
console.log(clone);
```
The method above copies an object into the targeted one. you can also extend it by placing comma to put another object as well.
```js
const clone={...device,...device2};
```
It combines them and then copies them.
You can also insert new keys and even change an existing key from previous objects:
```js
const clone={...device,...device2,...{width:"70cm"},name:"Apple"};
```
The name key actually gets overwrote. Not added.
##### Empty object vs Null
```js
const box={};
const temp=null;

console.log(typeof(box)); //object
console.log(typeof(temp)); //object
```
So based on the code above, the type of these two are objects. What is the difference? see below:
```js
const box={};
box.capacity=500;

console.log(box); //{ capacity: 500 }
```

```js
const temp=null;
temp.capacity=500;
console.log(temp); //TypeError: Cannot set properties of null (setting 'capacity') at Object.
```

##### Object built-in methods
To access the Object methods. we need to write Object first and then . after it.
```
Object.method(object_name);
```

**keys**
```js
const person={
    name:"Alireza",
    last_name:"Hosseini",
    age:21,
}
  
console.log(Object.keys(person)); //[ 'name', 'last_name', 'age' ]
```
keys method returns all of the key properties stored in the object.

**values**
```js
const person={
    name:"Alireza",
    last_name:"Hosseini",
    age:21,
}
  
console.log(Object.values(person)); //['Alireza','Hosseini', 21 ]
```
This method returns the values paired to keys inside the object.

**entries**
```js
const person={
    name:"Alireza",
    last_name:"Hosseini",
    age:21,
}
  
console.log(Object.entries(person));
```
It returns both keys and values . There are two differences. First, when you use this on console log, it returns it in a form of an array. second, there are no colons.

**assign**
You can assign values to an object in two ways, first one was direct assignment which u saw above. second one is using the assign method.
```syntax
Object.assign(object_name,{key:value});
```

```js
const person={
    name:"Alireza",
    last_name:"Hosseini",
    age:21,
}

Object.assign(person,{height:180});

console.log(person); //The height is added.
```

**toUpperCase()**
not actually specified method for objects, but you can use it.
```
string.toUpperCase();
```

**Checking if a key exists in an Object:**
```js
const person={
    name:"Alireza",
    last_name:"Hosseini",
    age:21,
};

console.log("age" in person);
```
You can use `in` for checking if a key exists in an Object.

##### Object getter and setter
**get:**
```js
const mobile={
    brand:"Apple",
    model:"15 promax",
    price:"1200$",
  
    getName(){
        return `${this.brand} ${this.model}`;
    }
};
  
console.log(`${mobile.brand} ${mobile.model}`); //1st method
console.log(mobile.getName()); //2nd method
```
This is an example. We want to copy the two arguments above.
An easier way is to use `get` keyword before the getName function here:
```js
const mobile={
    brand:"Apple",
    model:"15 promax",
    price:"1200$",
  
    get getName(){
        return `${this.brand} ${this.model}`;
    }
};

console.log(mobile.getName())
```
The difference is that you didn't call the function as a method and you called it as a property.

**set:**
We can change an object key's value by calling it and assigning new value to it.
```js
mobile.brand="samsung";
```

A better way is to use a setter method.
```js
const mobile={
    brand:"Apple",
    model:"15 promax",
    price:"1200$",
  
    get getName(){
        return `${this.brand} ${this.model}`;
    },
    
    setName(brand){
	    this.brand=brand;
    },
};

mobile.setName("samsung");
```

```js
const mobile={
    brand:"Apple",
    model:"15 promax",
    price:"1200$",
  
    get Name(){
        return `${this.brand} ${this.model}`;
    },
  
    set Name(brand){
        this.brand=brand;
    },
};
  
mobile.Name="Samsung";
console.log(mobile.Name);
```
You can use same name for the methods. You don't need to call them, you can just access them as a property.
```js
const mobile={
    brand:"Apple",
    model:"15 promax",
    price:"1200$",
  
    get Name(){
        return `${this.brand} ${this.model}`;
    },
  
    set Name(brand){
        const newName=brand.split(" ");
        this.brand=newName[0];
        this.model=newName[1];
    },
};
  
mobile.Name="Samsung s24";
console.log(mobile.Name);
```