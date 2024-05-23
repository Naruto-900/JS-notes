```js
const rest1 = {
  name: 'uday1',
  numGuest: 20
};

const rest2 = {
  name: 'La Piazza',
  owner: 'uday2'
};
```


Here our task is to add a property in those object which doesn't have a given property for this we can use 

```js
rest1.numGuest = rest1.numGuest || 10;
rest2.numGuest = rest2.numGuest || 10;

console.log(rest1,rest2);

//{name: 'uday1', numGuest: 20}
//{name: 'La Piazza', owner: 'uday2', numGuest: 10}
```

The above happens because in case of rest2 since numGuest property doesn't exist so `||` assigns the property of numGues with value 10 to the rest2 object. But in case of rest1 since numGuest exist so `rest1.numGuest` is true so it will not assign the value of numGuest as it already exist

>[!NOTE] 
>rest1.numGuest = rest1.numGuest || 10 `is same as` rest1.numGuest ||= 10;


Suppose if we want to anonymise the name of restaurant owner if it exist in the object so we can write as

```js
rest1.owner  = rest1.owner || 'ANONYMOUS';
rest2.owner = rest2.owner || 'ANONYMOUS';

//{name: 'uday1', owner:'ANONYMOUS', numGuest: 20}
//{name: 'La Piazza', owner: 'uday2', numGuest: 10}
```

The above happens because in case of rest1 since owner property doesn't exist so `||` assigns the property of owner with value 'ANONYMOUS' to the rest1 object. But in case of rest2 since owner exist so `rest2.numGuest` is true so it will not assign the value of owner as it already exist

>[!NOTE]
>- So in case of `||` logical assignment operator it only assign the value when the given property which is to be assigned doesn't exist that it is false
>
>
>
>- And in case of `&&` logical assignment operator it only assign the value when the given property which is to be assigned exist that it is true


And also one thing we must have to take care of difference b/w both the code snippet

1. 
```js
rest1.owner  = rest1.owner && 'ANONYMOUS';
rest2.owner = rest2.owner && 'ANONYMOUS';

console.log(rest1,rest2);
```

2. 
```js
rest1.owner  &&= 'ANONYMOUS';
rest2.owner &&= 'ANONYMOUS';

console.log(rest1,rest2);
```


Here in case of  1 we will get  output as 
```
{name: 'uday1', numGuest: 20, owner: undefined} //rest1
{name: 'La Piazza', owner: 'ANONYMOUS', numGuest: 10}//rest2
```


And in case of 2 we will get the output as 
```
{name: 'uday1', numGuest: 20} //rest1
{name: 'La Piazza', owner: 'ANONYMOUS', numGuest: 10} //rest2
```


The difference is been created on the basis of  how JavaScript handles `undefined` values.

In 2 , when you use the logical assignment operator `&&=`, the property is only assigned if it already exists. If the property doesn’t exist (i.e., it’s `undefined`), JavaScript doesn’t create the property. That’s why `rest2` doesn’t end up with an `owner` property it only update the owner string to `ANONYMOUS`. And for `rest1` since it doesn't have that owner property so `&&=` will not create that property.

But in the expanded form `rest1.owner  = rest1.owner && 'ANONYMOUS'` JS *evaluates the right hand side of the assignment first*. If rest1.owner is `undefined`, the result of undefined `&&` ANONYMOUS is `undefined`. Then, JavaScript assigns this undefined value to rest1.owner, effectively creating the `owner` property with an undefined value.

