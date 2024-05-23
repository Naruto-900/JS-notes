 Loop is a way to automate our repitative task

#### Syntax :

```js
 for(let rep = 1; rep<=10; rep++){
   console.log(`Lifting weights rep ${rep}`)
 }
```


```js

  const udayArray = 
  ['uday' ,'Tiwari' ,2037-1992 ,'student' ,['uday1' ,'uday2' ,'uday3']]
```


```js
for(int i=0; i<udayArray.length;  i++){
 console.log(udayArray[i])
}
```


In the code block below which will give error :

```js
const types = []

1.types = ['1','2']
2.types.push('string')
```


Here 1 will give error because types is declared as `const` so we can't *modify* it but in 2 we can `mutate`  the array.

To clear the confusion we can say by performing `1` what we are doing is we are _**Reassigning**_ types to another array since it is declare as const so reassigning it will give error to us.

But in case of `2` we are only _**Mutating**_ array and as array are of type object so we can modify the array so it will not give any error


#### New thing discover

consider the below code and then try to predict the output of the code

```js

const birthYear = [1993,1298,1254,1999]
const ages = []
for(let i=0; i<birthYear; i++){

    ages[i] = 2024-birthYear[i]
    console.log(ages[i])
}   
```

Yes, the loop `for (let i = n; ; i++)` is correct. In JavaScript, it’s allowed to omit any of the three parts in the `for` loop syntax. If the condition is omitted, the loop will run forever (or until an explicit break or return within the loop).



In JS if we want to map or say write a relation between two things such that one thing remains unique so in this case we can use `Map in JS` . Here the relation get formed in `key value pair` , _where every key is unique and we can have same values for different keys_.


##### Syntax :

```js
const map = new Map()
map.set(key ,value)
```

here we could have anything in either key or value or _**and it is also not necessary that type of data in key and value is same it could be of different type also**_  and also **Map reserve the order in which key value pair are inserted**


```js
const map = new Map()
map.set('IN' ,'India')
map.set('UK' , 'United Kingdom')
map.set('FR' , 'France')

for(const key of map) console.log(key) //Output1

for(const [key ,value] of map) console.log(key ,value) //Output2

/*Output1 

['IN', 'India']
['UK', 'United Kingdom']
['FR', 'France']

Output2

IN India
UK United Kingdom
FR France
*/
```


```js
const myObject = {
  'game1' : "IGI",
  'game2' : "GTA",
  'game3' : "NFS"
}

for(const [key ,value] of myObject) console.log(key ,value)

//Output : myObject is not iterable
```

In case of object we can use  `forin loop` to iterate the object with below syntax

```js
for(const key in myObject){ // Output1
  console.log(key)
}

for(const key in myObject){ // Output2
  console.log(` key : ${key}  value :${myObject[key]}`)
}

/*
 Output1
 game1
 game2
 game3

 Output2
  key : game1  value :IGI
  key : game2  value :GTA
  key : game3  value :NFS
*/

```


> The `for...in` loop in JavaScript is designed to work with objects where the properties (or keys) are strings or symbols. It goes through each property one by one.
> 
>The `for...of` loop in JavaScript works with things that are iterable, which means they have a way to go through their items one by one. Arrays, strings, `Map`, and `Set` are all examples of iterable objects.


If we want to destructure object in the `forin` loop then in that case we can write the below code

```js
const myObject = {
  'game1' : "IGI",
  'game2' : "GTA",
  'game3' : "NFS"
}

for(const [key, value] of Object.entries(myObject)) {
  console.log(key, value);
}
```

How the above work is firstly by doing `Object.enteries(myObject)` we are 

converting the object into array and we will get output as 
`['game1', 'IGI'], ['game2' ,'GTA'] , ['game3' , 'NFS']`

Then by using forin loop we are destructuring the object  

In case of array there are some loop which are inbuilt to the array method so we can also use them in our array and one such method is `forEach loop`

```js
const coding = ['js' ,'java' ,'ruby' ,'python' ,'cpp']

//using normal function as a callback function
coding.forEach(function(val){
  console.log(val)
})

//using arrow function as a callback function
coding.forEach( (val) => {
  console.log(val)
})
```

Here `function(){} is called as callBack function`  and how this loop works is that each element in the *coding array will be called as val and each val will be passed as an argument to the callback function* 


- `Object.entries()` is a method in JavaScript that converts a plain object into an array of `[key, value]` pairs i.e **object which are not iterable by default will become iterable**
- This array is iterable, which means you can use a `for...of` loop to go through each pair.
- Here’s how it works:
    1. `Object.entries()` looks at each property in the object.
    2. For each property, it creates an array where the first element is the key and the second element is the value.
    3. It does this for all properties and puts these arrays inside another array.
    
 ```javascript
    let myObject = { 'game1' : "IGI", 'game2' : "GTA", 'game3' : "NFS" };
    let entries = Object.entries(myObject);
    // entries is now [ ['game1', 'IGI'], ['game2', 'GTA'], ['game3', 'NFS'] ]
    for (let [key, value] of entries) {
      console.log('key:', key, 'value:', value);
    }
    // This will log:
    // key: game1 value: IGI
    // key: game2 value: GTA
    // key: game3 value: NFS
    ```



```js
const myCoding = [
   {
     languageName : 'Javascript',
     languageFileName: '.js'
   },

   {
     languageName : 'Python',
     languageFileName: '.py'
   },
   
   {
     languageName : 'Java',
     languageFileName: '.java'
   }
]

// To access the above we can use for each loop

myCoding.forEach((item) => {
   console.log(item)
})
```

Here in the above code `each item refers to each object in the array`  and  inside the for loop what it is doing is that it is accessing the object key and value

 
```js
const newNums = [1,2,3,4,5,6,7,8,9,10]

const myAns = newNums.filter((num) => num>4) 
```


```js
const books = [
   {title: 'Book one', genre: 'History', publish:1981,edition:2003},
   {title: 'Book two', genre: 'Crime', publish:1980,edition:2005},
   {title: 'Book three', genre: 'Romance', publish:1781,edition:2006},
   {title: 'Book four', genre: 'Funny', publish:1989,edition:2002},
   {title: 'Book five', genre: 'Science', publish:1931,edition:2004},
   {title: 'Book six', genre: 'Non-Fiction', publish:1900,edition:2010},
   {title: 'Book seven', genre: 'History', publish:1881,edition:2000},
   {title: 'Book eight', genre: 'Science', publish:1791,edition:2005},
   {title: 'Book nine', genre: 'Biography', publish:1982,edition:2014},
   {title: 'Book ten', genre: 'Biography', publish:1983,edition:2009},
];

const myBooks = books.filter((book) => {
   return book.genre === 'Science'
})

/*
 Output 
[{title: 'Book five', genre: 'Science', publish:1931,edition:2004},
 {title: 'Book eight', genre: 'Science', publish:1791,edition:2005}]
*/
```



```js
const myNumbers = [1,2,3,4,5,6,7,8,9,10]

const newNum = myNumbers.map(() => {return num+10})
console.log(newNum)

//Output [11,12,13,14,15,16,17,18,29,20]
```


#### Chaining of methods

Here in this case we can also apply two or more methods at the same time *i.e means we will have chaining type of effect*

```js
const myNumbers = [1,2,3,4,5,6,7,8,9,10]
const newNum = myNumbers
               .map((num) => {return num+10})
               .map((num) => num+1)
               .filter((num) => (num>=50 && num <= 100))

console.log(newNum)

//Output [51, 61, 71, 81, 91]
```

Here  after applying first map it return us the array and that array serves as a input to the second map operation and in this way there is a chain effect created

1. **Map as a Data Structure**: `Map` is a data structure that stores key-value pairs. In JavaScript, you can create a `Map` object to store and retrieve values based on their keys.

```javascript
let myMap = new Map();
myMap.set('key1', 'value1');
console.log(myMap.get('key1')); // Output: 'value1'
```


2. **Map as a Higher-Order Function**: `map` is a higher-order function in JavaScript’s Array object. It creates a new array with the results of calling a provided function on every element in the array.

```javascript
let arr = [1, 2, 3, 4, 5];
let squares = arr.map(function(element) {
  return element * element;
});
console.log(squares); // Output: [1, 4, 9, 16, 25]
```



```js
const arr1 = [1,2,3,4]

const myTotal = myNums.reduce((acc,currVal) => {
  return acc+currVal;
}, 0)
```


```js
 const shoppingCart = [
     {
      itemName : "JS course",
      price : 2999
     },

     {
      itemName : "Python course",
      price : 999
     },

     {
      itemName : "Data Science course",
      price : 12999
     },
     
     {
      itemName : "Mobile Dev course",
      price : 12999
     },
 ]

 const priceToPay = shoppingCart.reduce((acc,course) => {
    return acc + course.price
 },0)
```


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

console.log(

Object.values(users).reduce((acc,item) => {return acc+item.id},0)

)
```

Here `Object.values(users)`  will return a _array_ where each element will be a object and then applying `reduce` we are summing up the id all the id