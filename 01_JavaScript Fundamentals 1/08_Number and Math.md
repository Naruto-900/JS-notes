We can declare number in JS by two ways as below image :

![[Pasted image 20240301165302.png]]

Here the difference is that num1 is declared using `Number Primitive`  and num2 is declared using `Number Object`

That's why the return type of num2 is object and that of num1 is primitive(number)

> When we are dealing with `high precision` values then in that case we can use *toFixed* to solve this and what it does is it accept one number and then it will display those places of decimal according to the number given
> ![[Pasted image 20240301170456.png]]
> Here we have given `toFixed` a value 2 and it is showing value after 2 places of decimal


```js

 const hundreds = 1000000
 console.log(hundreds.toLocaleString())

 //output = 10,00,000
```

what it does is it will correctly format the number so that it appears good but by default it display according to the US standard and for printing according to indian standard we *only have to pass 'en-IN' to the method*


<hr>


```js
  console.log(Math)
```

The above will  print out the `Math` object, which includes various properties and methods used for mathematical operations.


```js
 console.log(Math.random()) // This will give value b/w 0 and 1
```


```js

 //This code will generate number from 0 to x where x is exclusive and 
 //0 is included

 console.log(Math.random()*x)
```

And since output of the above can be 0 and if we want that we should not have 0 then in that case we would `add 1`

```js
 console.log((Math.random()*x) + 1)
```


And if we want to generate random number between two ranges then we could do the following

```js

// For a random integer between min (inclusive) and max (inclusive)

 const min = 10
 const max = 20

 console.log(Math.floor(Math.random() * (max - min+1)) + min)
```

```javascript
// For a random integer between min (inclusive) and max (exclusive)

 const min = 10
 const max = 20

 console.log(Math.floor(Math.random() * (max - min)) + min)
```

![[Pasted image 20240301191252.png]]

![[Pasted image 20240301192832.png]]


>[!Note]
>One thing we must take care that in case of c++ (which i know) if we perform *int/10*  it will return an *int* but in case of JS doing the same thing will not return *int* but it will return **floating number**

