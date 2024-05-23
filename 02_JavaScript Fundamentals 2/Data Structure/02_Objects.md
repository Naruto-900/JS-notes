 Consider below Code 

```js

  const udayArray = 
  ['uday' ,'Tiwari' ,2037-1992 ,'student' ,['uday1' ,'uday2' ,'uday3']]
```


Here in this code `intutively` we know that first element is name and second one is title , last one is friends list

But problem is that _**in array there is not anyway to give them name or we can't reference them by name but we can do that by index of array**_ so to solve this problem we have another DS called as *Objects*

>In Objects we define `key value pair` and in case of array we used *square brackets* and in Objects we use *curly brackets*


##### Syntax for declaring Object

```js

 const uday = {

   firstName : 'uday', //Key : Value
   lastName  : 'Tiwari',
   age : 2024-1988,
   Job : 'student',
   Friends : ['uday1' ,'uday2' ,'uday3']
 }
```

Here in value `we can write any expression which leads to value` and value can be of any type


> Each of the key is called as `Property` and we say the given object has 5 `Property`


> _**And the above way of declaring Object is called as Object Literal syntax**_
> And also one main difference between array and object is in case of `retrieving elements from array the order of element matter` _**but in case of object this doesn't matter**_
> In object we will access the data by the `Key`
> So by ordering we can say that we will need array when we will need to have structured and ordered data and object when we need unstructured data




##### Dot vs. Bracket Notation


```js
 
 const uday = {

   firstName : 'Uday', //Key : Value
   lastName  : 'Tiwari',
   age : 2024-1988,
   Job : 'student',
   Friends : ['uday1' ,'uday2' ,'uday3']
 }
```

here to access the property of the object we can use `.(dot notation)`  like below

```js
console.log(uday.lastName)
```

_What this .(dot notation) does is it goes to the object and then search for the property and gives us the value_

And to access the property of the object we can also use `bracket notation([])` like below

```js
console.log(uday['lastName'])
```

So here we have to write the key as a string inside the square bracket


> The main difference between both of them is in case of bracket notation we can write any expression that will lead to the value
> But in case of  `.` we can't write an expression we have to write the whole property name
> *And if we want to access the property in the object which is not present then in that case we will get undefine*

```js
const nameKey = 'Name'
console.log(uday['first' + nameKey])
console.log(uday['last' + nameKey])
```


Suppose we don't know what property we want to display and that will come from UI so in that case we can't use `.` for accessing the property in object

```js
 const interestedIn = 
 prompt("what do u want to know about uday whether it is firstName ,lastName ,job,friends")

 console.log(uday.interestedIn)
```

The above will give error because `there is not any property define interestedIn in object`

So to solve the above problem we can use `[]` instead

```js

  const interestedIn = 
 prompt("what do u want to know about uday whether it is firstName ,lastName ,job,friends")

 console.log(uday[interestedIn])
```

Here depending upon value of interestedIn we will get the correct output


We can also use `dot and bracket notation`  to add some property to the object like below

```js
uday.property_name = value
uday['property_name'] = value
```



#### Object Methods

Since we know that  in case of `value` in object we *__can have any expression which can return value so by this thought we can also write method in the value of the property__*

Syntax for writing method or function in value  : 
`function name : function expression`

```js
 
 const uday = {

   firstName : 'Uday', 
   lastName  : 'Tiwari',
   birthYear : 1999,
   Job : 'student',
   Friends : ['uday1' ,'uday2' ,'uday3'],
   hasDriverLicense : true,
   
    calcAge : function(birthYear){
     return (2037-birthYear)
   }  

    checkLicense : function(){
      return (this.hasDriverLicense)
    }
 }

 console.log(uday.calcAge(1999))
 console.log(uday['calcAge'](1999))
```

Here as `birthYear` is being define in the object itself so with the help of _**this**_  keyword we can access the birthYear in the object so we don't need to pass birthYear as an argument to the function

`And with the help of "this" keyword we can also add property to the object using the dot operator`

```js
 this.property_Name = value
```

```js

 calcAge : function(){
  return (2037- this.birthYear)
 }
```

```js
  //Challenge by Jonas
console.log(`${uday.firstName} is a ${uday.calcAge()}-year old ${uday.Job}, and he has ${uday.checkLicense()==true ? `a` : `no`} driver's license`)
```


>[!NOTE]
>If we have define any property inside a function which is being declared in object and we want to use that property then for that we have *to call that function first then only we can use that property*
>
>And writing same method in both object can be optimise by *OOPS*


When you define a method (a function inside an object), `this` allows you to access the properties and other methods of that object. This is useful because it lets you interact with the object from within its own methods.


There are two ways of accessing objects 

1. Using `dot notation`
2. Using `square bracket`


- **Dot notation** is shorter and easier to read, and is generally used when you know the name of the property you’re accessing.

```javascript
let car = {make: 'Toyota', model: 'Camry'};
console.log(car.make);  // Outputs: Toyota
```


-  **Bracket Notation** :  is more flexible because it can evaluate expressions. This means you can use variables and strings that are calculated at runtime. That means if we define an key that is being evaluated by function call can be acessed by bracket notation

And to use symbol as a key in object we have to use below syntax

```js
 const mySymbol = Symbol('key1')

 const myObj = {
   [mySymbol] : "mykey1"
 }
```

and to acess it we will use  bracket notation `console.log(myObj[mySymbol])`


And if we want that not anybody could change the object property then we can use `freeze method`

```js
Object.freeze(Object Name)
```

By this method it will not give any error but the changes made after this will not be propagated


In JavaScript, objects are dynamic. This means you can add properties and methods to an object at any time after it has been created.This is useful because it allows you to extend and modify objects as needed.

```js
const myObj2 = {
  value : 1,
  value : 2,
}

myObj2.greetings = function(){
  console.log("Hello World")
}
```

But when in this code we try to access `greetings` then in that scenario there are two cases

1. `console.log(myObj2.greetings)` this means we are only refering the object itself and not calling it

```js
let sayHello = myObj2.greetings;
sayHello();  // Outputs: hello world
```

In this example, `sayHello` is now a reference to the `greetings` function, and you can call `sayHello()` to execute it.

2. `console.log(myObj2.greetings())` here we are actually invoking or calling the function


>Q. What's difference between adding property to object using .notations and using this keyword
>Q. What's the difference between accesing object key using dot notation and using this keyword


If we want to add or concat two object then in that case we can use `Object.assign() method`

```js
const obj1 = {1:"a" ,2:"b"}
const obj2 = {2:"a" ,3:"b"}
const obj3 = {5,"a" ,4:"b"}

const obj3 = Object.assign(target ,source)

//where target would be {}
// source would be all the objects i.e obj1,obj2,obj3 ....
```

And `const obj3 = Object.assign(target ,source)` what this says is that copy all the source to target

And we can also use `spread operator` to add both the object by following syntax

```js
const obj3 = {...obj1, ...obj2 ,...obj3}
```


>[!HINT]
>Whenever data come from database it comes in the form of `array of objects`

```js
const users = [
        {
          name : "user1",
          id : 1,
          email : "user1@gmail.com"
        },

        {
         name:"user2",
         id:2,
         email : "user2@gmail.com"
        }
    ]
```

And suppose if we want all the keys of the object then in that case we can use `Object.keys(object name)` and return type will be array of keys

```js
console.log(Object.keys(users))
//Output : ['0' ,'1']
```


In JavaScript, an array is a special type of object. The keys of an array are the indices used to access the elements in the array.

So when you call `Object.keys(users)`, it returns the keys (indices) of the `users` array. Since `users` has only two element (an object), its only key (index) is `0 and 1`. That’s why you get `['0' ,'1']` as the output.


And if we want to access the keys of the object then in that case we can write something like this `Object.keys(users[0])` and in the same way we can access the values by only writing `Object.values(users)`

So when we only write `Object.values(users)` we will get the array where each element contains object 

```js
 [{name : "user1",id : 1,email : "user1@gmail.com"}, {name : "user2",
  id : 2,email : "user2@gmail.com"}]
```


We can also check if a object has certain property or not by below syntax :

```js
console.log(ObjectName.hasOwnProperty(property))

// It will boolean depending upon whether it exist or not
```



### Object Destructuring  and JSON API intro

If we want to access the values of the object then for that generally what we used to do is `ObjectName.key` but if we want to do this in many places then in that case we can use other syntax

```js
const course = {
   courseName : 'JS in hindi',
   price : "999",
   Instructor : "hitesh"
}
/*Inside the curly braces we would write the property which we want to access*/

const {Instructor} = course 

//Then after writing above we can directly write the name of property so we don't have to write the ObjectName.property all the times

console.log(Instructor)
```

And if we want to give it smaller name instead long one so we can use below syntax

```js
console.log(Instructor : teacher)
```


<hr>


Sure, here’s a summary:

1. **Rest Parameter Must Be the Last Parameter**: The rest parameter in JavaScript is denoted by `...` and must be the last parameter in a function definition. It collects all remaining arguments into an array.

```javascript
function myFunction(a, b, ...rest) {
  // 'a' and 'b' are regular parameters.
  // 'rest' collects all remaining arguments.
}
```

2. **Rest Parameters Are True Array Instances**: Unlike the `arguments` object in JavaScript, rest parameters are true arrays. This means you can use array methods directly on them.

In JavaScript, there’s an older feature called the `arguments` object, which also lets you access all arguments passed to a function. But `arguments` is not a real array, so you can’t directly use array methods like `sort()`, `map()`, `forEach()`, or `pop()` on it.


```javascript
function myFunction(...args) {
  // 'args' is a rest parameter and a real array.
  // You can use array methods like forEach directly.
  args.forEach(arg => console.log(arg));
}
```

In the first function, `a` and `b` are regular parameters, and `rest` is a rest parameter that collects all remaining arguments. In the second function, `args` is a rest parameter and a real array, so you can use array methods like `forEach` directly on it.


##### Passing object to the function

```js
const userA = {
   userName : 'uday',
   price : 199
}

function handleObject(anyObject){

console.log(`Username is : ${anyObject.userName} and price is ${anyObject.price} `)
}

handleObject(userA) // Username is : uday and price is 199
```

But here we have to take care of typesafety that the given parameter is object or not and what if the property we are accessing is available or not

We can also `directly`  pass object to the function by writing in curly braces  while passing the argument

```js
console.log(handleObject({
  userName : "uday",
  price : 199
}))

// Username is : uday and price is 199
```


- In JavaScript, when you create an object and add properties, the keys are always turned into strings or symbols.
- For example, if you use a number as a key, it gets turned into a string.
- If you use a `Symbol` as a key, it stays a `Symbol`.
- This is a basic rule of JavaScript and it’s always true. You can’t change this behavior.

Here’s a short example:

```javascript
let myObject = {};
myObject[123] = 'test'; // The number 123 is turned into the string '123'
let mySymbol = Symbol('mySymbol');
myObject[mySymbol] = 'test'; // The Symbol stays a Symbol
```

So in case of object `if we use anything as key except string or symbol it will get converted to string`


<hr>


### Destructuring Object

```js
const restaurant = {
   name: 'Classico Italiano',
   location: 'Via Angelo Tavanti 23, Firenze, Italy',
   categories: ['Italian','Pizzeria','Vegetarian','Organic'],
   starterMenu: ['Focaccia','Bruschetta','Garlic Bread','Caprese Salad'],
   mainMenu: ['Pizza','Pasta','Risotto']

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
}

};
```

In case of object we can also destruct them by `using curly braces {}` and in the curly braces we have to *write the exact property name of the object*

```js
const {name,openingHours,categories} = restaurant
console.log(name,openingHours,categories)
```


Here in the curly braces we have to give the exact property name but we can also give another name by following syntax

```js

const{name:restaurantName,openingHours:hours,categories:tags} = restaurant

//This will give same result as above but here we can use our own name
console.log(restaurantName,hours,tags)
```

And we can also have a default value for the case where we are trying to read a property which doesn't exist in the object because in this case `we will get undefined` so to change this we can `provide default value`


```js
//Here in case of default value we are giving an empty array
const {menu = [] , starterMenu:Starter = []} = restaurant
```


##### Mutating varibales in object


```js
let a = 1;
let b = 2;
const obj = {a:3,b:4,c:5}
```

here if we try to mutate the value of a and b we can't simply write just like what we have written in case of array while mutating the variable just like this and we can't write const or let in front of the curly braces *because that will redefine the variable decalred*.

And if we write this we will get error because in case of JS whenever it encounters `{}` it expect to see code written and we can't assign something to codeblock by equal sign so to solve this problem we can wrap `{a,b} = obj` inside parentheses

```js
{a,b} = obj
console.log(a,b) // SyntaxError: Unexpected token '='

({a,b} = obj)
console.log(a,b) // This will give correct result
```

##### Nested object destructuring

```js
const {sat} = openingHours
```

The above code means inside the restaurant object we have a `openingHours object` and inside that openingHours object we have a `sat object` so by writing *const {sat} = openingHours* we are simply destructuring the object and since the `sat` is also a object then in that case we can further destructure it like this

```js
const {sat : {close,open}} = openNingHours;
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
}

};

console.log(restaurant.orderDelivery({
  time: '22:30',
  address: 'Via del sole,21',
  mainIndex: 2,
  starterIndex:2
}))
```