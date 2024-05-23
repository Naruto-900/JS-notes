 1. `const sum = arr.reduce((a, b) => a + b, 0);`

By this way we can sum all the elements of the array consisting of numbers


2. If we have a number `n = 4689288` and we want to convert it like this  arr = `[4,6,8,9,2,8,8]` then we can use the below syntax


```javascript
let arr = num.toString().split('').map(Number);
```


- `num.toString()` converts the number `46288` to a string `'46288'`.
- `split('')` splits the string into an array of characters: `['4', '6', '2', '8', '8']`.
- `map(Number)` converts each character in the array back into a number, resulting in `[4,6,8,9,2,8,8]`.



3. Although both gives us a section of array specified by the index but there is a big difference between them which is _`in splice it modified the array`_ but in case  _**in slice it doesn't modify the array**_


```js

   const arr1 = [1,2,3,4,5]

  console.log(`Array1 : ${arr1}`) // [1,2,3,4,5]

  console.log(`Array by using splice : ${arr1.splice(1,3)}`) // [2,3,4]
 
  console.log(`Original array after splice : ${arr1}`) // [1,5]

   const arr2 = [1,2,3,4,5]
   
   console.log(`Array2 : ${arr2}`) // [1,2,3,4,5]
  
  console.log(`Array by using slice : ${arr2.slice(1,3)}`) // [2,3]

  console.log(`Original array after slice : ${arr2}`) // [1,2,3,4,5]
```


4. If we have something like this in array 

```js
const arr = [1,2,3,[4,5,6],7,[6,7,[4,5]]]
```

But we don't want such complicated structure we want a single array or  to flatten or remove nesting up to a certain level so we can use `flat method` and in that method we have to specify how many levels of nesting should be removed

```js
console.log(arr.flat(depth_value))
```

> Here in the depth value we can also provide `Infinity` as argument which means removes all the levels of nesting



5.  Suppose we are collecting data from the website and there can be a possiblity that it comes in various response and if we want it to convert it to array then we can use

  ```js
  console.log(Array.from('uday')) // ['u' ,'d' ,'a' , 'y']
```

we can also pass object but what we have to take care we have to specifically tell that `we have to make array of either key or value`

```js
//Here o/p will be empty array because object is not iterable
console.log(Array.from({name : 'uday'}))
```

>However, an object is not an iterable, which means it cannot be looped over in the same way as an array, string, or other iterable types.

And to convert object into array we can use `Object.keys()` , `Object.values()` and `Object.enteries()` depending upon whether we only want array of keys or values or want to keep them both


And if we have some set of element and we want to convert them back to array we can use
`Array.of()` and pass elements separated by comma

```js
const name1 = 'uday1'
const name2 = 'uday2'
const name3 = 'uday3'
console.log(Array.of(name1,name2,name3)) // ['uday1' , 'uday2' , 'uday3']
```


>[!NOTE]
>In case of creating array using array constructor i.e using `new keyword` we have to take care that while passing argument to the constructor function that :
>- If we pass a single argument it will create an `empty array` of that given length
>- And if we pass multiple arguments separated by comma then in this case it will create array with those multiple values



6. While using  ==*arrow function*== we have to take care that while using `{}` and `()`  i.e in case of `()` we don't need to write return keyword in arrow function and in `{}` we need to write return keyword

```js
 //Explicit return
   const addUsingReturn = (num1 ,num2) => {
      return num1 + num2;
   }

    //Implicit return
   const addWithoutReturn = (num1 ,num2) => (num1 + num2)
```


And also if we want to return object from arrow function then we have to use below syntax

```js
 const addTwo = (num1,num2) => ({userName: "uday"})
```



7. When we create array using `Array.of()`   and `arr[] (array literal)`  although both of them create array but there is a difference between them which is

  - _**Array.of()**_ will create array with a single element with value being equal to argument and if we `pass multiple arguments` of  **any type and any amount**  then in that case it will create elements with those values

```js
console.log(Array.of(1,2,"uday1" ,["uday2" , "uday3" , ["uday4" ,"uday5"]],{email : "uday@gmail.com" ,age :21}))

 /*
 
 0 index : 1
 1 index : 2
 2 index : "uday1"
 3 index : (3) ['uday2', 'uday3', Array(2)]
 4 index : {email: 'uday@gmail.com', age: 21}

 where Array(2) is ["uday4" , "uday5"]
*/
```


- _**using array literal []**_   it will create array with elements being passed inside the square bracket  and if we didn't pass any element then in that case it will create an empty array

```js
const arr = [1,2,3,4] // length = 4
const arr2 = [] // array being empty i.e length = 0
```


8. We can also shorten an array using the `length` property:

```javascript
const numbers = [1, 2, 3, 4, 5];
if (numbers.length > 3) {
  numbers.length = 3;
}
// numbers is now [1, 2, 3]
```


9. We can also check if we got a empty object or not

```js
if(Object.keys(Object Name).length === 0)
  console.log("Object is empty")
```

What above code is doing actually  that it *first convert the object into arrays of keys* then by using `.length` property it is checking the length of that array and if length is not zero it means object has some property inside it 


10.  While getting data from the database it is possible that we might get `null` or `undefined`  so to prevent null or undefined entering our value we can use _**Nullish Coalescing Operator ( ?? )**_

```js
let val1;
val1 = null ?? 10;

console.log(val1);
```

In the above case `??` will check if we are getting null value then we will assign the `value 10` to val1.

>[!NOTE]
>returns its right-hand side operand when its left-hand side operand is `null` or `undefined`, and otherwise returns its left-hand side operand.


But in case of real life devlopment we would write function which would make call to server and if we get response from the server then in that case we would assign that value to it and if we got nothing then in that case it will assign null so that we can handle the case accordingly


11. In JavaScript, a **“plain object”** is an object that is created using _object literal syntax_ or constructed with `new Object()`. It’s the simplest form of object you can create. Here’s an example:

```javascript
let myObject = {a: 1, b: 2, c: 3}; // This is a plain object
```



A plain object has properties and values, and you can add, change, or remove these properties. _**The keys (or property names) of a plain object are always strings or symbols.**_

On the other hand, **special objects** like `Array`, `Map`, `Set`, `Date`, etc., are not plain objects. They are built-in objects that come with additional features and methods.


13. In case of map if we try to insert a key,value pair to the map in which the key already exist then in that case JS will replace the value assoicated with that key

```javascript
const map = new Map();
map.set('IN', 'India');
map.set('IN', 'France');
```


The key `'IN'` is first set to `'India'`, but then it’s updated to `'France'` in the next line. So, if you were to retrieve the value of `'IN'` after these operations, you would get `'France'`.

```javascript
console.log(map.get('IN')); // This will log: 'France'
```

13.  Consider these while selecting element in DOM

1. **Cache selections**: Store and reuse results from `querySelector` to avoid repeated costly operations.
   
2. **Specific selectors**: More specific selectors (e.g., `document.querySelector('div.myClass')`) are faster than generic ones.
   
3. **Use IDs for single elements**: `getElementById` is faster than `querySelector` because IDs are unique.
   
4. **Avoid premature optimization**: Focus on clear code first, then optimize if needed. 



14. There is a difference between how `forin` and `forof` loop works here working means how it's iterate over the elements

   - Since we know forin loop is used to iterate over the property of the object so when we used it in object so it will iterate over the property of the object _**But when it is used in case of array so as we know array are special type of object and in array the key are indices of the array**_  so forin loop access the indices of the array.

But if we use forof loop then in that case it `will directly access the element so we don't need to used index to access the element`


15.  The `property` of an array is dynamic and can be directly modified . If we increase the length, new indices will be filled with undefined. If we decrease it the array will be truncated.

16. When we write like this `arr[0]` what JS does behind the scene is that since we know array is also a object but special type so when we are writing `arr[0]` we are actually **accessing the property of the object**. JS convert the index number to a string behind the scene. So `arr[0]` and `arr["0"]` both are same. However we can't use dot notations with the numbers so `arr.0` is not valid

And this behaviour is called as `Dynamic Indexing`