
In JS there is not any difference between denoting string in single quote and double quote

In JavaScript, `const str = new String('uday')` creates a new String object. Here’s what’s happening:

- `new String('uday')` is using the `String` constructor to create a new String object that contains the value ‘uday’.
  
When you do `console.log(str)`, it prints out the details of the `str` String object:

- `String {'uday'}` indicates that `str` is a String object with the value ‘uday’.
  
- `0: "u"`, `1: "d"`, `2: "a"`, `3: "y"` are showing the index-based access to the characters in the string. *In JavaScript, strings are indexable like arrays.*
  
- `length: 4` is a property of the String object that tells you the length of the string, which is the number of characters in it.
  
- `[[Prototype]]: String` and `[[PrimitiveValue]]: "uday"` are internal properties of the String object. The `[[Prototype]]` property is a reference to another object from which properties are inherited. The `[[PrimitiveValue]]` property contains the primitive value of the String object, which is ‘uday’ in this case.

It’s important to note that even though strings in JavaScript are indexable like arrays, they are not actual arrays. Arrays come with a lot of built-in methods that strings do not have. Also, strings are immutable in JavaScript, which means that you cannot change their characters by accessing them via indices.


```js

 const str1 = new String('uday')
 console.log(`Type of str1 is ${typeof str1}`)

 output : Type of str1 is object

 const str2 = 'uday'
 console.log(`Type of str1 is ${typeof str2}`)
 
 output : Type of str2 is string
```


In this code it is being described the two ways of declaring string in JS and it `can be used interchangeably because JS converts automatically between them.`

But there is difference between them in below ways :

1. _**Way of declaring**_ : That *str1 is being declare using string object* and `str1 is a string object not a string primitive`

And *str2 is string primitive and they can't be changed once they are created* because `string are immutable in JS`

2. _**Type of both**_ : str1 is a `string object` where as str2 is `string primitive`


> In JS (it's confusing to say for me) that datatype of string is not fixed but it rather `depend upon the way of declaring it` which are described below
><hr>
> 
>   **String Primitive**: When you declare a string like this: `const str1 = 'uday';`, you’re creating a string primitive. Primitives are the most basic data types in JavaScript, and they include strings, numbers, booleans, null, and undefined. When you assign a primitive to a variable, JavaScript stores the actual value, not a reference to it. So if you do `let str2 = str1;` and then change `str2`, `str1` will not be affected because they each have their own copy of the value.
>   <hr>
>   
     **String Object**: When you declare a string like this: `const str3 = new String('uday')`, you’re creating a String object. In JavaScript, objects are a non-primitive data type. When you assign an object to a variable, JavaScript stores a reference to the object, not the actual object itself. So if you do `let str4 = str3;` and then change `str4`, `str3` will also be affected because they both refer to the same object.
    

![[Pasted image 20240301163130.png]]

Here although `myStr1` is created using *String Object* and the return type is *object* but still here the string `myStr1` will be immutable. _**So we must remember a thing that whether the string is created using**_  `String Primitive`  or  `String Object` _**it will still remain immutable in JS**_

>The reason strings are immutable in JavaScript, even when declared using the String object, is due to the design of the language





If we have string in that case using `indexOf` and `lastIndexOf` method in a string will give us the first and last occurence of the given char in string. If there are multiple occurence then in that case it will give first and last index of that char or there is only single occurence then in that case both of them will give same answer i.e index at which the given char occurs.

We can also use `indexOf` to search for a entire word in a given string and it will return the *index of the first letter of that word*

```js
const myStr = "My name is uday";
const startIndex = myStr.indexOf('uday');

//But here we have to write the exact word it's also case sensitive
console.log(startIndex); // o/p : 11 
```


>[!NOTE]
>If we give negative number to `slice` then in that case it will began extracting from end

