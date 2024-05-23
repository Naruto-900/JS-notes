Array is like special type of variable which can hold multiple values like a single container holding multiple things

> `type of array is object`



##### Syntax for creating array in JS

1. *Creating array using Array literal*
```js

const friends = ['uday1' ,'uday2' ,'uday3']
console.log(friends)

output : {"uday1" , "uday2" ,"uday3"}
```


2.  *Creating array using Array constructor*
```js

 const years = new Array(1991,1992,1993,2003,2004)
 console.log(years)

output : [1991,1992,1993,2003,2004]
```


> In case of array whether they are created using *array literal* or  **array constructor** in both the case the _`typeof`_ remains same as `object`

To Access the element in the array we could use square bracket just like `console.log(arr[indx])` and in JS if we try to access a element which is not present in the array then *JS would return undefine*

- To get the no of element in the array we could use `.length`  property in JS as

```js
 console.log(years.length)
```

And the output will not be 0 based that for 3 elements it would give us 2 that  0->1->2


- `console.log(arr[indx])` , here in case of indx we can put **any expression that will gives us value**

ex : 

```js
//This will give the last element of the array
console.log(years[years.length-1])
```


- We can also use the `[]` brackets to replace or change the values in the array
   ex :

```js

years[1] = 2024
console.log(years)

output(original) :  [1991,1992,1993,2003,2004]
output(changed) :   [1991,2024,1993,2003,2004]

```


> In case of `primitive type` if they are declared using const they can't be changed but in case of string it doesn't matter by which means we declare it either const or let it will not change
> But in case of `non-primitive type` even if they are declared using const they can be changed
>  That means *we can only change the values inside the array* not the entire array as
```js
 years = [1,2,3,4,5]
 //output : Assignment to constant variable
```


- Array could also hold *values of different  type*

  ```js
  const details = ['uday' ,'Tiwari' ,23]
```

Here for each element JS accept expression not statement so writing 2023-1934 instead of 23 will be fine


- We can also have array inside another array as follow

   ```js
 const arr1 = [1,2,3,4]
 const arr2 = [arr1,5,6,7]

 console.log(arr2) //  [Array(4), 5, 6, 7]
```

##### Basic Array Operations


1. Push Method : By this it pushes the element in last of the array

```js
  const num = [1,2,3,4]
  num.push(5)

 /*

 output : nums = [1,2,3,4,5]
 
 */

```

And also `push function returns the length of the array after element being pushed`

And *if we want to add element to front of the array then we can use "unshift" method*

```js

 const num = [1,2,3,4]
  num.unshift(0)

 /*

 output : nums = [0,1,2,3,4]
 
 */

```  


`unshift also return the length of the array after pushing`


2. Remove Element : By this it removes the `last element` from the array

```js
 const lastValue = num.pop()

//  Output : nums = [1,2,3] , lastValue = 4
```

And output return the last element which is popped and to get that value we will only have to save the value onto a variable

And if we want to remove the first element from the array we could use `shift method`

```js
const firstValue = num.shift()

//Output : nums = [2,3,4] ,firstValue = 1
```


3. To get the index of element  : With the help of this method we can get the index of the element in the array

```js
 console.log(num.indexOf(2))

//Output : 1 as 2 is present in 1st index
```

And if  *we try to search for the index of the element which is not present in the array we will get -1 as output*

```js

 console.log(num.includes(2))

 //Output : true (as 2 is present in the array other wise false)

```

And this include method uses `strict equality` to search for the element


If we try to perform below operation in array then it would return some interesting result

```js

 const num1 = [1,2,3,4]
 const num2 = [5,6,7,8]

 console.log(num1+num2)

```

According to jonas `he said that by performing the above operation then in that case two array will get converted back to string and then they will be concatenated`

But checking this images left me 😶‍🌫️😶‍🌫️😶‍🌫️😶‍🌫️

![[Pasted image 20240303203932.png]]

![[Pasted image 20240303203959.png]]


![[Pasted image 20240303204025.png]]

<hr>

##### assigning value directly vs. pushing value directly to array

consider the below :

```js
1. types[i] = uday[i] 
2. types.push(uday[i])
```

Yes, there is a difference between `types[i] = uday[i]` and `types.push(uday[i])` in JavaScript.

1. `types[i] = uday[i]`: This line of code is directly assigning the value at index `i` of the `uday` array to the `i`' th index of the `types` array. If `types[i]` already has a value, it will be overwritten. 

  And also in case of `1` if we are trying to assign value to a index which is larger than size of the array then in that case what JS will do is given below :
 

  if length of types is 5 and we are assigning value to 9 index of the array so as we can see
  `here the index at which we are assigning value is greater than length of array ` so firstly JS *will increase the size of array then problem came of assigning values to the array* so in this case JS will assign  all the index from 6 (arr.length+1) till 8(index-1 , which is 9 in this case) to `undefined`

```js
const x = [1,2,3,4]
x[7] = 5

console.log(x)
// Output -> x = [1,2,3,4,undefined,undefined,undefined,5]
```

    
2. `types.push(uday[i])`: This line of code is adding the value at index `i` of the `uday` array to the end of the `types` array, regardless of what values `types` already contains. The `push` method automatically increases the length of the array by one.
    

Here’s a small example to illustrate the difference:

```javascript
let types = ['a', 'b', 'c'];
let uday = [1, 2, 3];

types[1] = uday[1]; // types is now ['a', 2, 'c']
types.push(uday[2]); // types is now ['a', 'b', 'c', 3]
```


<hr>


Consider the below code 

```js
const num1 = [1,2,3,4]
const num2 = [4,5,6,7]

num1.push(num2)

console.log(num1) 
```

In the above what mostly people assume that both the array will merge but it will not but the output will be `[1,2,3,4,[4,5,6,7]]`


But if we use _Concat method_ for the above example then we will have

```js

const num1 = [1,2,3,4]
const num2 = [4,5,6,7]
const num3 = [1,2,3,4,...num4]
const num4 = [4,5,6,7]


console.log(`Result using concatenation: ${num1.concat(num2)}`);
console.log(`Result using spread Operator: ${num3}`);
```

Here although num4 is define above num3 but this code will still give correct answer because of a concept called `hoisting in JS`

**What concat has done is it add both the array and then return a new array but without modifying the original array**


But there is one more way of combining two arrays which is using _`Spread operator in array which is used to expand any iterable into it's individual element`_


```js
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const combined = [...array1, ...array2];  // [1, 2, 3, 4, 5, 6]
```


<hr>



### Destructuring Arrays

It is a `ES6` feature which means can separate a given collection of values into  `separate variable`

```js
const arr = [1,2,3,4];

//Normally
const a = arr[0];
const b = arr[1];
const c = arr[2];
const d = arr[3];

//Using Destructuring 
const [a,b,c,d] = arr;

console.log(a,b,c,d) // 1 2 3 4
```

```js
const restaurant = {
   name: 'Classico Italiano',
   location: 'Via Angelo Tavanti 23, Firenze, Italy',
   categories: ['Italian','Pizzeria','Vegetarian','Organic'],
   starterMenu: ['Focaccia','Bruschetta','Garlic Bread','Caprese Salad'],
   mainMenu: ['Pizza','Pasta','Risotto']

   order: function(startIndex,mainIndex){
     return [this.starterMenu[startIndex],this.mainMenu[mainIndex]]
   }
};

//If we want to skip particular element then we can simply leave a hole in the destructuring

const [first,second] = restaurant.categories;

//Swapping values using destructuring
[second,first] = [first,second];

//Recieve 2 return values from a function
const[starter,main] = restaurant.order(2,0);

console.log(starter,main) // "Garlic Bread" , "Pizza"

const nested = [2,4,[5,6]]

const nested = [1,2,[3,4]]
const [num,,arr] = nested
console.log(`num is ${num} and array is ${arr}`); // 1 [3,4]
```


```js
const nested = [1,2,[3,4]]

const [num1,num2,[num3,num4]] = nested;
console.log(num1,num2,num3,num4)// 1, 2 , 3 ,4

//Default values
const [p,q,r] = [8,9]
console.log(p,q,r) // 8 9 undefined

//Or

const [p,q,r=10] = [8,9];
console.log(p,q,r)
```


```js
//Using Destructuring 
const [a : x , b , c , d] = arr;
console.log(x,b,c,d); // SyntaxError: Unexpected token ':'
```

In JavaScript, the `:` symbol is used in *object destructuring to map properties to variable names*. However, arrays don’t have properties like objects do, they have indices. So, _**when destructuring arrays, JavaScript uses the order of elements instead**_. That’s why `:` is not used in array destructuring.
