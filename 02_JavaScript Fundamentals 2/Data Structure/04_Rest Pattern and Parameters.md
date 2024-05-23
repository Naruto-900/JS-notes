
Rest pattern which has syntax similar to spread operator but functions just opposite to waht spread operators does.

In case of spread it expands the collections of elements into individual one but in case of rest it concise the elements into a single entity

>[!NOTE]
>The spread operator offers a very concise method to copy the arrays ensuring that any modification in the copied one does not affect the original one. `By spreading the original array into new one we create a distinct copy`


```js
//Spread Operator because on RIGHT side of =
const arr = [1,2,3,...[4,5,6,7]];

//Rest because on left side of =
const [a,b,...remain] = [1,2,3,4,5,6,7]
console.log(a,b,remain);
```


```js
const restaurant = {
   name: 'Classico Italiano',
   location: 'Via Angelo Tavanti 23, Firenze, Italy',
   categories: ['Italian','Pizzeria','Vegetarian','Organic'],
   starterMenu: ['Focaccia','Bruschetta','Garlic Bread','Caprese Salad'],
   mainMenu: ['Pizza','Pasta','Risotto'],

   order: function(startIndex,mainIndex){
     return [this.starterMenu[startIndex],this.mainMenu[mainIndex]]
   },

  openingHours:{
   thu:{
    open:12,
    close:22
   },
   
   fri:{
   close:11,
   close:23
   },

  sat:{
  open:8,
  close:24
  }  
},

orderDelivery: function({starterIndex,mainIndex,time,address}){
 console.log(`Order recieved ${this.starterMenu[starterIndex]} and ${this.mainMenu[mainIndex]} will be delivered to ${address} at ${time}`)
},

orderPizza: function(mainIngredient, ...otherIngredient){
 console.log(mainIngredient,otherIngredient);
}

};

const [pizza,,risotto,...otherFood] = [...restaurant.mainMenu,...restaurant.starterMenu]

console.log(`${pizza} and ${risotto} and ${otherFood}`);
```


>In Destructuring the `rest` must be at last because if not then JS will give error of when to collect all the remaining elements of the array


```js
const {sat, ...weekEnd} = restaurant.openingHours;
console.log(sat,weekend); // {open: 8, close: 24}  {thu: {…}, fri: {…}}
```


#### Using rest in function

```js
const add = function(...nums){
  console.log(nums.reduce((a,b) => a+b,0));
}

add(1,2);
add(1,2,3,4,5)
```

```js
const add = function(...nums){
  console.log(nums.filter(function(i){return i%2==0}));
}

add(1,2);
add(1,2,3,4,5)
```

Here in both the cases `nums` is acting like a array which contains all the variable no of values.

```js
restaurant.orderPizza('mushroom','Paneer','Cheese','Red Chilli','blackOlives')
```

>[!NOTE]
>`restaurant.orderPizza(mushroom)` 
>
>
>In the above case as we have specified only parameter which is mainIngredient and *there is nothing for rest to collect* so in this case _**rest will gives us an empty array**_



```js
const restaurant = {
   name: 'Classico Italiano',
   location: 'Via Angelo Tavanti 23, Firenze, Italy',
   categories: ['Italian','Pizzeria','Vegetarian','Organic'],
   starterMenu: ['Focaccia','Bruschetta','Garlic Bread','Caprese Salad'],
   mainMenu: ['Pizza','Pasta','Risotto'],

   order: function(startIndex,mainIndex){
     return [this.starterMenu[startIndex],this.mainMenu[mainIndex]]
   },

  openingHours:{
   thu:{
    open:12,
    close:22
   },
   
   fri:{
   close:11,
   close:23
   },

  sat:{
  open:8,
  close:24
  }  
},

orderDelivery: function({starterIndex,mainIndex,time,address}){
 console.log(`Order recieved ${this.starterMenu[starterIndex]} and ${this.mainMenu[mainIndex]} will be delivered to ${address} at ${time}`)
},

orderPizza: function(mainIngredient, ...otherIngredient){
 console.log(mainIngredient,otherIngredient);
}

};

const [pizza,,risotto,...otherFood] = [...restaurant.mainMenu,...restaurant.starterMenu]

console.log(`${pizza} and ${risotto} and ${otherFood}`);
```


```js
for(const [key,{open,close}] of Object.entries(openinHours)){
  console.log(`On ${key} we open at ${open} and close at ${close}`)
}
```
