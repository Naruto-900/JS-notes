
Here generally in the official documentation of JS datatypes are generally divided into only two types of datatypes which are :

- Primitive    
- Non-primitive / Reference type


>[!HINT]
>The difference is created on the basis of how data is stored in the memory and how we will access them



_**Primitive**_ : They are of 7 type which are `String`  ,  `Number`  , `Boolean`  ,  `Null`  , `Undefined`  ,  `Symbol`  ,  `BigInt`.

>[!NOTE]
>In primitive datatype it is being treated as call by value that means whenever we copy them from a given place then *we will don't get the memory reference of that place where it is store originally*  i.e means we will not the get the original value instead we will get the copy of that value and all the changes occur in copy



_**Non-Primitive (Reference Type)**_ :  In this case we will be given direct reference of the memory space where they are stored in the memory

And they are  `Array`  ,  `Object`  ,  `Functions`

In case of non-primitive type the `typeof` will be object


>[!HINT]
>- Master object in JS and browser events to master JS
>- In JS both integer and float value comes under Number datatype


`JavaScript is a Dynamically typed language because we don't  explicitly need to define the datatype of the variable we declared`


```javascript

 const id1 = Symbol('123')
 const id2 = Symbol('123')  

 console.log(id1 === id2);

 const bigNumber = 9093034904903n;
```


Here the output will be false because as we know `Symbol` is used to uniquely identify something so even if we have given them same values id1 and id2 will be different

And appending `n` at last the number will be treated as `bigInt`



```javaScript

 const heroes = ["shaktiman" ,"naagraj" ,"doga" ,"kimada"]

 let myObj = {

  name: "uday",
  age : 23,
 }

```


Here inside the curly braces all the thing are object and datatype can be anything


```JavaScript

  const myFunction = function(){
       console.log("Hello World")
  }

  console.log(typeof variable_name)
```

Here `typeof` in JS will tell the *datatype* of variable


