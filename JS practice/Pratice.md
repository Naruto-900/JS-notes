1. consider this code 

```js
let num = '12'
let convertedNum = Number(num)

console.log(`typeof num is ${typeof num} and that of convertedNum is ${typeof convertedNum}`)

// output : typeof num is string and that of convertedNum is number
```

Here `typeof num` is still string because since we know that string is a primitive data (big confusion) type so in case of *primitive data we only get the copy of value not the memory reference so any changing will affect the copy only not the original one*


#### Q 2. Why primitive data type is being stored in stack and non-primitive data type is stored in heap ?

1. **Primitive Data Types**: These are simple data types like numbers, strings, and booleans. They are stored in the **stack**, which is fast but has limited space. This is because primitive data types are small and have a fixed size.
    
2. **Non-Primitive Data Types**: These are complex data types like objects and arrays. They are stored in the **heap**, which has more space but is slower. This is because non-primitive data types can change in size.
    
3. **References**: When a non-primitive data type is created, a reference to it is stored in the stack, but the actual data is stored in the heap. This is why non-primitive data types are also known as reference types.
    

In essence, the stack and heap are used together to efficiently manage memory in JavaScript. The stack is used for fast access to small, fixed-size data (primitive types), while the heap is used for larger, dynamic data (non-primitive types). References in the stack point to the actual data in the heap


#### Fact about stack and heap memory

The scenario where the stack and heap collide is typically a result of one of two situations:

1. **Stack Overflow**: This happens when the stack grows too much, usually due to deep recursion or allocation of large local variables. This could cause the stack to encroach on the heap’s territory, leading to overwriting of heap data
    
2. **Heap Overflow**: This occurs when too much memory is dynamically allocated during runtime, causing the heap to grow and possibly encroach on the stack. If not handled well, this can lead to memory leaks

**Concurrency Issues**: The heap is accessible across multiple threads, which can lead to data corruption if not properly synchronized. The stack, however, is thread-specific, so switching the two could lead to concurrency issues