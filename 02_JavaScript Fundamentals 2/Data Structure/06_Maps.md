Here `map` is a type of DS which can use to map two things in the form of `key-value pairs`

And in case of map *key can be of any type* but in case of **object it will always be of string type**

#### Syntax

```js
const restMap = new Map(); // creates an empty map
```

```js
//To add element in the map
restMap.set('name','Uday Dhaba');
restMap.set(1,'Ranchi');
restMap.set(2,'Delhi');
```

Here in the above code doing `restMap.set(key,value)` it returns the map after inserting the value

```js
const updatedRestMap = restMap.set(2,'Delhi');
console.log(updatedRestMap);
```

Since `set method` returns the map then we can also do *chaining of methods* as

```js
restMap.set(1,'Ranchi').filter((item)=>{
  console.log(item)
})

/*
“Uncaught TypeError: restMap.set(…).filter is not a function” occurs because the filter method is not available for Map objects.
*/

//So to correct above error we can use
[...restMap.set(1,'Ranchi')].filter((item)=>{
  console.log(item)
}) 

//or

Array.from(restMap.set(1,'Ranchi')).filter((item)=>{
  console.log(item)
})
```


```js
//To get value if key is given we can use get method
console.log(restMap.get(key)) //This will give value for that key
```

>Map does `strict equality check` while getting the value from the key


```js
//To check if map has certain key or not
console.log(map_name.has(key)) //return true or false

//To get the size of the map
console.log(restMap.size);

//Remove all the element from the map
restMap.clear();
```

```js
1.
 const updatedMap = restMap.delete(2); console.log(updatedMap); //returns true
```

```js
2.
console.log(restMap.delete(2)); //output false
```
 
why `1` is returning true and `2` is returning false because in both case we are doing same thing ??

--> The above is happening because delete method in JS return a `boolean value which indicate that whether the element is sucessfully deleted or not`. If it returns true that means element is successfully deleted and that element is being present for being deleted and if returns false that means the element doesn't exist so it can't be deleted


```js
const question = new Map([
 ['question','What is the best programming language in the world'],
 [1,'C'],
 [2,'Java'],
 [3,'Javascript'],
 ['correct',3],
 [true,'Correct'],
 [false,'Try again!'],
]);

//Convert object to map
const obj_To_Map = new Map(Object.entries(object name));

console.log(question.get('question'));

for(const [key,value] of question){
  if(typeof key === 'number'){
   console.log(`Answer ${key} : ${value}`)
  }
}

const userAns = Number(prompt(`What's your answer`));

if(question.get('correct') === userAns)console.log(`You are correct`);
else console.log('Try Again!');
```