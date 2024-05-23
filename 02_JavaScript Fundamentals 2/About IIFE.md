#### IIFE = Immediately Invoked Function Expression

The above is also a function but a special type of function that `runs immediately as soon as it is define`  but before we understand this we must understand there is a difference between _running immediately as soon as program runs_  Vs. **running as soon as it is define**


In case _running immediately as soon as program runs_  means when the program start executing it will firstly before any other thing

Since we know that in JS programs get executed in the form of `top to bottom`  so when the program flow reaches where _**IIFE is defined so instead of looking for the function calling for the function and then executing it will immediately execute that function**_  i.e `running as soon as it is define`


##### Syntax for IIFE

```js
//with anonymous arrow function inside
(() => {
  //do stuff
});
```

```js
(function(){
 //do stuff
})();
```





The function expression is enclosed within `()` to distinguish it as an expression and not a statement. The trailing `()` triggers the immediate execution of the function.



Reason 1) Does not pollute the global object namespace

```js
 //Global
 const x = 10
 const helloworld = () => "Hello World"

 //isolate declaration within the function
 (() => {
     const x = 'life whatever'
     const helloWorld = () => "hello IIFE"
     console.log(x)
     console.log(helloWorld())
 })();
```