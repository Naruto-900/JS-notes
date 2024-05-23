In case of primitive datatype they all acquire memory in *Stack* and that of non-primitive type will acquire memory in *Heap*

> In case whenever we get any stack memory we will get the copy of that memory and in case of heap we will get the reference of that
> Means in case of copy  all the changes will get reflected in copy  and there will not be any effect on original one
> But in case of reference any changes will also affect the original one 

<hr>

Primitive Type
```js

		let myName = "uday"
		let anotherName = myName
		anotherName = "93094"

       console.log(myName,anotherName)
   
 //  output : uday 93094
```

<hr>

Non Primitive Type

```js

  let userOne = {
    email:"user1@gmail.com",
    upi:"user1@oksbi",
  }

  let userTwo = userOne

  userTwo.email = "uday@gmail.com"

  console.log(userOne.email , userTwo.email)
//Output = uday@gmail.com uday@gmail.com
```
