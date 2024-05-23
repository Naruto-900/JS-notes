Sets are nothing but a collection of unique value that doesn't have duplicate

*Syntax*:

```js
const orderSet = new Set(iterator)//general

//In most situation in case of iterator array is passed
const orderSet = new Set(['Pizza','Pizza','Pizza','Risotto','Pasta','Pizza']);
```

>Set can hold mix data type
>- Set are iterable just like array but both of them are very much different
>- Order of elements in set are random they can be in any order


```js
//To check if set has a element or not
//This will return true if element is present else false
console.log(set_name.has(element)); 

//Add element in a set
//Here element will be added only one time
set_name.add(element);
set_name.add(element);

//Delete element from set
set_name.delete(element);

//Delete all the element from the set
set_name.clear();
```

Since `set are iterable we can loop over them` like

```js
 for(const dish of orderSet)console.log(dish)
```

```js
const staff = ['Waiter','Manager','waiter','chef','Manager','waiter','Chef'];

const staffUnique = [...new Set(staff)];

console.log(staffUnique);
```

- Since set are iterable _**so we can also destructure them as below :**_

```js
const staff = ['Waiter','Manager','waiter','chef','Manager','waiter','Chef'];

const staffUnique = [...new Set(staff)];
const[staff1,staff2] = staffUnique; // Waiter Manager

```

