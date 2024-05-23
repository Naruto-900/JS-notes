
### Javascript Execution Context(JEC)

JEC means how JS will execute the code and for running our program JS runs it in two phases

Whenever we give any code file to JS for execution then in that case firstly and mostly it will `create an Global Object`

##### This is what it means to be single threaded in JS
 Imagine you’re at a fast-food restaurant. You place your order at the counter `(this is like starting a JavaScript operation)`. Instead of waiting at the counter for your food *(which would block anyone else from ordering)* , you step aside so the next person can order. When your order is ready, the restaurant calls you back to the counter to pick it up. This is _**similar to how JavaScript can start an operation (like fetching data), move on to the next operation, and then come back to the first operation when the data is ready.**_ 

So when JS execute our code file then it is being divided in to two parts

1. Memory creation phase
2. Execution phase 

In Memory creation phase memory is being declared to the variable or declaration we have done in our code and importantly `nothing is being executed in this phase`



```js
let val1 = 10;
let val2 = 5;
function addNum(num1 ,num2){
   let total = num1 + num2;
   return total;
}

let result1 = addNum(val1 ,val2);
let result2 = addNum(10 ,2);
```


If the above code is being given to JS for execution then in that case JS will follow this steps to execute that

1. The `GEC` is created and it is being asssignesd to `this`

 2. In memory creation phase we generally collect all the variable and assign *undefined* to it because in this phase the program is not executed and there is nothing being assigned to the variable

      val1 --> undefined
      val2 --> undefined
      addNum --> definition 
      result1 --> undefined
      result2 --> undefined

here definition consist of the code which we have written inside the function

3.  In the execution phase val1 and val2 are being assigned value 10 and 5 resp.

4. Interesting thing happen when JS reaches towards result1 then in that case it sees addNum function call `it creates another execution context (or another enviroment variable + Execution thread` and then *process 1 and 2 again happens for the function*


> In case of function when there is a memory creation phase JS executes memory to all the parameters and variable inside the function



*Compilation* : Entire code is converted into machine code at once and written to a binary file that can be executed by a computer


*Interpretation* :  Interpreter runs through the source code and executes it line by line

**Just-in-time(JIT) compilation :** Entire code is converted into machine code at once then executed immediately

![[Drawing 2024-04-24 23.32.29.excalidraw.png]]


>[!NOTE]
>Web API are the functionalities that are being provided to engine via window object 
>Execution Context is a enviroment in which JS code is executed and it stores all the necessary information for the code to be executed