In JS if we want to run our method for continuous amount of time after a given interval then for that we can use `setInterval() method`

```js
setInterval(function(){},1000)
```

here the time is given in ms which is `1s = 1000ms` format and the function will run continuously after 1s


```js
setInterval(function(){
let date = new Date();
//console.log(date.toLocaleTimeString());
  time.innerHTML = date.toLocaleTimeString();
},1000)
```

This code will display time continuously after 1s