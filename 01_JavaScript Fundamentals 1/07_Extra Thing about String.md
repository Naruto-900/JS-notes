
In JavaScript, template literals (also known as template strings) are enclosed by the back-tick `( `` ) character instead of double or single quotes. Template literals can contain placeholders, indicated by the dollar sign and curly braces (`${expression}`)

However, only **expressions** _**can be included inside the placeholders in template literals**_ , not **statements**. An expression is a piece of code that evaluates to a value. Examples of expressions include variables, literals, function calls, and operations that involve values and variables.

Here’s an example:

JavaScript

```javascript
let a = 5;
let b = 10;
console.log(`The sum of a and b is ${a + b}.`); // Outputs: "The sum of a and b is 15."
```


In this example, `a + b` is an expression that gets evaluated and its result gets inserted into the template literal.

On the other hand, a statement performs an action and doesn’t necessarily produce a value. Examples of statements include `if` statements, `for` loops, and `switch` statements. These cannot be used inside the placeholders in template literals.

For example, the following would not be valid:

JavaScript

```javascript

console.log(`The value is ${if (a > b) { 'greater' } else { 'less' }}` ); // This will throw an error
```



In this case, `if (a > b) { 'greater' } else { 'less' }` is a statement, not an expression, so it can’t be used inside a template literal.


> Inserting variable directly into the template literal is called as string interpolation
> - Escape Sequence are those special set of characters when used with another character is not treated as a character
> 



##### Q. Why String are immutable in JS ?

=> The immutability of strings is a design decision made by the creators of the language. There are several reasons for this:

1. **Efficiency**: JavaScript stores identical string values only once in memory to save space.
2. **Hashing**: Immutable strings can be used as reliable keys in hash-based data structures.
3. **Security**: Immutable strings are safer in multi-threaded environments as they can’t be altered by other threads.
4. **String Interning**: Unique string values are stored once in memory, with references used for repetitions, saving memory.
