##### Date object
This type of object is used for date operations. It has 5 constructor types.
```js
const now=new Date();
const date1=new Date("December 24 2025");
const date2=new Date(12345678); //converts this number as mili seconds to a date.
const date3=new Date(2024,5,24,5,0,0); //No need to write 0s for hours.
const date4=new Date(now)//(date1);
  
console.log({now,date1,date2,date3,date4});
/*
{
  now: 2025-12-24T16:44:24.609Z,
  date1: 2025-12-23T20:30:00.000Z,
  date2: 1970-01-01T03:25:45.678Z,
  date3: 2024-06-24T01:30:00.000Z,
  date4: 2025-12-24T16:44:24.609Z
}
*/
```

##### Date methods
**date.toString()**
Turns your whole date value into a string and then returns it.
```js
console.log(now.toString());
```
others:
```js
console.log(now.toUTCString());//Wed, 24 Dec 2025 16:48:30 GMT
console.log(now.toISOString());//2025-12-24T16:48:30.529Z
```

**toTimeString()**
```js
console.log(date2.toTimeString()); //06:55:45 GMT+0330 (Iran Standard Time)
```

**getTimes**
```js
console.log(now.getFullYear());
console.log(now.getMonth());
console.log(now.getDate()); //day of the month
console.log(now.getDay()); //day of the week(0-6):0 is sunday, ...
console.log(now.getHours());
console.log(now.getMinutes());
console.log(now.getSeconds());
console.log(now.getMilliseconds());
```

**Changing time:**
```js
const newYear=date1.getFullYear()-1;
date1.setFullYear(newYear);

date1.setMonth(date1.getMonth()-1);

console.log(date1.toDateString());
```
You can use all set dates.