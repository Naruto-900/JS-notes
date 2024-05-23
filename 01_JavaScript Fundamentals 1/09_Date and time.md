
```js

//This would create a Date object instance
 let myDate = new Date()
 console.log(myDate)

//output : Fri Mar 01 2024 20:00:38 GMT+0530 (India Standard Time)
```


And if we want to create a specific date then we can create like this

```js

	let myCreatedDate = new Date(2023,0,23)
	console.log(myCreatedDate)

// output : Mon Jan 23 2023 00:00:00 GMT+0530 (India Standard Time)
```

The various date object format are 

```js

new Date()  
new Date(_date string_)  
  
new Date(_year,month_)  
new Date(_year,month,day_)  
new Date(_year,month,day,hours_)  
new Date(_year,month,day,hours,minutes_)  
new Date(_year,month,day,hours,minutes,seconds_)  
new Date(_year,month,day,hours,minutes,seconds,ms_)
```


```js

//This will return time in ms from 1 Jan 1970
let myTimeStamp = Date.now()
```



```js
 //This will return time in ms for this date from 1 Jan 1970
 
 // In this format of Date object month start from 0 to make it normal we will add 1
 
 let myCreatedDate = new Date("01-14-2023")
 console.log(myCreatedDate.getTime())
```




