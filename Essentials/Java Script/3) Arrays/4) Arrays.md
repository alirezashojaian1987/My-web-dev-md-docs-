```js
const cars=["pride", "samand"];
```
An Array is an object type designed for storing data collections.

##### Arrays are Objects
Arrays are a special type of objects. The `typeof` operator in JavaScript returns "object" for arrays.
But, JavaScript arrays are best described as arrays.
Arrays use **numbers** to access its elements.
Objects use names to access it's members.

Array elements can be objects.
JavaScript variables can be objects. Arrays are special kinds of objects.
Because of this, you can have variables of different types in the same Array.
You can have objects in an Array. You can have functions in an Array. You can have arrays in an Array.
##### Creating an array
Using an array literal is the easiest way to create a JS array.
```syntax
const array_name=[item1, item2, ...];
```

*Notes:*
1. As objects, spaces and line breaks are not important. A declaration can span multiple lines.
2. You can also create an empty array and insert elements later.
```js
const cars=[];
cars[0]="Pride";
cars[1]="BMW";
```

**Using JS new:**
The following example also creates an Array, and assigns values to it:
```js
const cars=new Aray("Saab","Volvo","BMW");
```
The two examples above do exactly the same.
There is no need to use `new Array()`.
you can safely use `[]` instead.
##### Accessing array elements
You can access an array element by referring to the index number.
```js
const nums=[1,2,3,4];
console.log(nums[2]); //3
```

This statement changes the value of the first element in arrays:
```js
nums[3]=40;
```

Accessing the last element in an array:
```js
const arr=[1,2,3,4];
console.log(arr[arr.length-1]);
```

**Finding element's index**
You can use `indexof()` method.
```js
const nums=[2,122,50,222];
console.log(nums.indexof(50)); //2
```
*!Note:* If the element doesn't exist in the array, it returns -1.
*Note:* If you are sure that the element you are looking for, is above a certain index, you can set it right next to the requested element.
```js
console.log(nums.indexof(222,2));//2 is the start index for search operation.
```
If you set the base index out of range, it will return -1.

**Check if an element exists in an array:**
```js
const nums=[1,2,3,4,5];
console.log(nums.includes(6)); //false
```
*Note:* Same as `indexof` method, you can set a start search index.

##### Finding objects in an array
Because objects and arrays are non-primitive types, they have their own addresses.
If you use includes method in order to realize if an object exists in an array or not, it will always return false, even that the objects are the same. The difference is that they have their own addresses.

To find an object in an array, we can use these methods:
```js
const names_list=[
	{id:1,name:"Alireza"},
	{id:2,name:"Shirin"},
]

const res=names_list.find(function(item){
    return item.id===1;
})

console.log(result); //{id:1,name:"Alireza"}
```

If you want to find the index of the object, you can use this method:
```js
console res_index=names_list.findIndex(function(item)){
	return item.id===1;
}
```
##### Access the full array

##### Iterating arrays
One way to loop through an array is using a `for` loop:
```js
const fruits=["Banana","Orange","Apple","pineapple","Mango"];

for(let i=0;i<fruits.length;i++){
    console.log(fruits[i]);
}
```
The method above, is using an element like i as an index.

You can also make an iterator for your array's iteration.
```js
const arr=[1,2,3,4];

for(const item of arr){
    console.log(item);
}
```

You can also use the `Array.forEach()` function:
```js
arr.foreach(function(item)){
	console.log(item);
}
```

To add or change elements while on iteration, you can use map.
```js
arr.map(function(item)){
	console.log(item);
	return item+" "+"Num";
}
```
The code above alone does nth.

You can use this:
```js
const newarr=arr.map(function(item){
    return item+" "+"Num";
})

console.log(newarr);
```

*More examples:*
```js
const brands=["apple","samsung","xiaomi","nokie"];

const newbrand=brands.map(function(item){
	return{
		name:item,
		price:Math.random()*1000,
	}
})
```
random function returns a random num between 0&1.
you can put that inside `parseInt()` method for just the integer side.

##### Adding and removing array elements
The easiest way to add a new element to an array is using the `push()` method:
```js
const fruits=["Banana","Orange","Apple","pineapple","Mango"];
fruits.push("Lemon");
```
New element can also be added to an array using the `length` property:
```js
const fruits=["Banana","Orange","Apple","pineapple","Mango"];
fruits[fruits.length]="Lemon";
```
*!Note:* Adding elements with high indexes can create undefined "holes" in an array.

**Add elements at the start of an array:**
To add elements at the start of an array, we use `unshift` method.
```js
arr.unshift(2);
```

**Array splice()**
The `splice()` method adds and/or removes array elements.
The `splice()` method overwrites the original array.
```syntax
array.splice(index,count,item1,...,itemN)
```
*Parameters*

| Parameter     | Description                                                                                                         |
| ------------- | ------------------------------------------------------------------------------------------------------------------- |
| _index_       | Required.  <br>The index (position) to add or remove items.  <br>A negative value counts from the end of the array. |
| _count_       | Optional.  <br>Number of items to be removed.                                                                       |
| _item1_, ..., | Optional.  <br>The new elements(s) to be added.                                                                     |
```js
const arr=[1,2,3,4,5];
arr.splice(1,0,10,11);
console.log(arr); //at index 1, adds 10 and 11 elements, 0 items are removed at the side of index 1
```

**pop() method** 
This method removes the last element. and then returns it.
```js
arr.pop();
```

##### Clear arrays
To clear arrays, just put the length size to 0.
```js
arr.length=0;
```

##### Merging arrays
```js
const arr=[1,2,3];
const arr2=[4,5,6];

const arr3=arr1.concat(arr2);
```

##### Slicing arrays
```js
arr=[1,2,3,4,5,6,7,8,9];
const arr2=arr.slice(2,4);
```
First value is the start index and the second one is the end index. You can also just put one value for just the start. Remember that this method only copies and will not change the original array.

##### Filter arrays
 ```js
 const phones=[
    {name:"apple",price:1000},
    {name:"samsung",price:550},
    {name:"xiaomi",price:250},
    {name:"nokia",price:800},
    {name:"sony",price:450},
];
  
const cheap=phones.filter(function(item){
    return item.price <500;
});
  
console.log(cheap);
 ```
The filter method uses a function that have a condition in it.
The `filter()` method creates a new array filled with elements that pass a test provided by a function.
The `filter()` method does not execute the function for empty elements.
The `filter()` method does not change the original array.

Another example:
```js
const ages=[32,33,16,40];
const result=ages.filter(is_adult);
  
function is_adult(age){
    return age>=18;
};
  
console.log(result);
```

##### Array reduce method
The `reduce()` method executes a reducer function for array element.
The `reduce()` method returns a single value: the function's accumulated result.
The `reduce()` method does not execute the function for empty array elements.
The `reduce()` method does not change the original array.
```syntax
array_.reduce(_function(total, currentValue, currentIndex, arr), initialValue_)
```
+ function() : Required. A function to be run for each element in the array.
+ total: Required. The _initialValue_, or the previously returned value of the function.
+ currentValue: Required. The value of the current element.
+ currentIndex: Optional. The index of the current element.
+ arr: Optional. The array the current element belongs to.
+ initialValue: actually required but it's optional. A value to be passed to the function as the initial value.
*Example*
Calculate total price:
```js
const prices=[17500,3000,21000,5000];
total=prices.reduce(calculate,0);
  
function calculate(sum,price){
    return sum+price;
}
  
console.log(total);
```

The other way you can use this method:
```js
const prices=[17500,3000,21000,5000];
total=prices.reduce(function(sum,price){
    return sum+price;
},0);
  
console.log(total);
```

*Another example:*
```js
const products=[
    {name:"monitor",price:1000},
    {name:"keyboard",price:500},
    {name:"mouse",price:250},
];
  
const total=products.reduce(function(sum,elm){
    return sum+elm.price;
},0);
  
console.log(total);
```

##### Array properties and methods
```js
arr.length //returns the number of elements
arr.sort() //sorts the array
```
sort method in Js actually sorts elements alphabetically. So it won't sort them ordered as you imagine.
To avoid this problem, you should give it arguments and define the sort behavior for it.
```js
arr=[100,23,4,100235];
arr.sort();
console.log(arr); //[ 100, 100235, 23, 4 ]
```

The right way to sort:
```js
arr.sort(function(a,b){
	if(a>b) return 1;
	if(a<b) return -1;
	else return 0;
});
```

**reverse()**
This method sorts your array in reversed order. last element goes first and... . 
##### Array flat join
If you want to put all your array elements into an string, you can use join method.
```js
names=["ali","hossein","hassan","mohammad"];
const joined_name=names.join(",");
console.log(joined_name);
```
You can set a separator value in join method. Here is ',' . 

**flat**
Is a method that changes a nested array into a one array. But you need to define a layer for it in order to make your deeper layers into one layer.
```js
const arr=[1,2,3,[4,5,[6,7],8],9];
arr.flat(2);
```
##### every and some methods
Sometimes you just need an check iteration on an array for a condition you're looking that all your array elements have. 
```js
arr=[100,23,4,1002];
  
const res=arr.every(function(num){
    return num<1000;
});
  
console.log(res);//false
```
every method iterates over array to check if all the elements has the condition. It stops when it find a false one.

**some** method checks at least one element has the condition.
```js
arr=[100,23,4,1002];
  
const res=arr.some(function(num){
    return num<1000;
});
  
console.log(res);//true
```
##### When to use arrays and when to use objects
- JavaScript does not support associative arrays.
- You should use **objects** when you want the element names to be **strings (text)**.
- You should use **arrays** when you want the element names to be **numbers**.
##### How to recognize an array?
```js
Array.isArray(arr);
```

##### Converting an array to a string
The JavaScript method `toString()` converts an array to a string of (comma separated) array values.
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];  
document.getElementById("demo").innerHTML = fruits.toString();

//Banana,Orange,Apple,Mango
```

##### Exercises
**Finding max element in array:**
Normal method
```js
const nums=[15,23,12,543,231,324,124,2,5432,5546];
  
function max(input){
    if(input && Array.isArray(input)){
        let max_elm=0;
        for(const item of input){
            if(item>max_elm){
                max_elm=item;
            }
        }
        return max_elm;
    }
    return null;
}
  
console.log(max(nums));
```

Using **reduce()** method:
```js
const nums=[15,23,12,543,231,324,124,2,5432,5546];
  
const max_elm=nums.reduce(function(mv,item){
    if(mv<item) return item;
    return mv;
},0);
  
console.log(max_elm);
```

**Filtering:**
```js
const samsung_mobiles=[
    {
        model:"Samsung Galaxy s24",
        release_year:2023,
        screen_size:6.2,
        resolution:"2400 * 1080",
        processor:"Exynos 2100 / Snapdragon 888",
        ram:"8GB",
        storage:"128GB / 256GB",
        battery:"400mAh",
        camera:{
            front:32,
            rear:"108MP + 64MP + 12MP",
        },
        price:799,
    },
  
    {
        model:"Samsung Galaxy s21 Ultra",
        release_year:2023,
        screen_size:6.8,
        resolution:"3200 * 1440",
        processor:"Exynos 2100 / Snapdragon 888",
        ram:"12GB / 16GB",
        storage:"128GB / 256GB / 512GB",
        battery:"5000mAh",
        camera:{
            front:40,
            rear:"108MP + 10MP + 10Mp + 12Mp",
        },
        price:1199,
    },
  
    {
        model:"Samsung Galaxy Note 20",
        release_year:2020,
        screen_size:6.7,
        resolution:"2400 * 1080",
        processor:"Exynos 990 / Snapdragon 865",
        ram:"8GB",
        storage:"256GB",
        battery:"4300mAh",
        camera:{
            front:32,
            rear:"12MP + 64MP + 12Mp",
        },
        price:999,
    },
];
  
//screen size  6.5 && font camera at least 24MP / ordered in decending price
  
const model_names_list=samsung_mobiles.filter(finder);
  
function finder(mobile){
    return mobile.screen_size>6.5 && mobile.camera.front >=24;
};
  
model_names_list.sort(function(a,b){
    if(a.price>b.price) return -1;
    if(a.price<b.price) return 1;
    else return 0;
})
  
console.log(model_names_list);
```

```js
const models=model_names_list.map(function(item){
    return item.model;
})
console.log(models);
```