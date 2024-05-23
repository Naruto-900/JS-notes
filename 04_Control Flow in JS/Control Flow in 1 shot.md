 Control flow means with the help of some condition we can decide the flow of program i.e upon certain condition is getting meet we will execute the code or if we are not meeting the given condition we will execute a certain code

> In case of using switch case if we don't write break statement then all the code after that will be executed `except default case`


Consider the below code  and try to guess the output:

```js
const myArr = [1,2,3,4,5,6]

switch(myArr){
    case [1,9,4,3,5,6] :
        console.log("It doesn't match")
        break;
        
    case [1,2,3,4] :
        console.log("60% matched")
        break;

        case [1,2,3,4,5,6] :
        console.log("100% matched")
        break;

     default :
        console.log("It matched to nothing")
        break;
}
```


A. 100% matched   B. 60% matched   C. It doesn't match  D. It matched to nothing


Correct ans : D. It matched to nothing

Explanation :  The `switch` statement in JavaScript uses strict comparison (`===`), which checks both value and type. When you use arrays in the `case` statement, it’s comparing the **references** of the arrays, not their values.

In your code, `myArr` is a different instance from the arrays in the `case` statements, even though the values are the same for the case `[1,2,3,4,5,6]`. Since they are different instances, their references are different, and the comparison fails, leading to the execution of the `default` case.



This behavior is not exclusive to arrays, it also applies to all objects in JavaScript. `In JavaScript, primitive types (like numbers, strings, booleans, null, and undefined) are compared by their value`, _**while objects (like arrays, functions, and objects) are compared by their reference.**_

*This means that when you compare two objects (including arrays), JavaScript checks to see if they refer to the exact same memory location* `- i.e., if they are the exact same object. `Even if two objects have the exact same properties and values, they are not considered equal because they are stored in different memory locations.


*Falsy Values* : false ,0 ,-0 , BigInt 0n , "" , null , undefined , NaN
*Truthy Values* : "0" , 'false' ," " , [] ,{} , function(){}