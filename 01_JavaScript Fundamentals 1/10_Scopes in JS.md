
In JS the use of `var keyword`  is not used for declaring varaible because it doesn't follow scope rules consider the below code

```js
{
 const a = 10
 let b = 11
 var c = 12
}

console.log(a,b,c)
```

Here in the above code since we have defined a scope for three varaibles so `accessing a and b will give error`  as we are accessing them outside their scope but _**in case of var this is not the case we can access  "  c  "  outside it's scope**_  which is not at all good for security reasons.  So the usage of var is discouraged



#### About this keyword

*Bookish Definition*  :  `this` refers to the current object that is executing the current function or **what i understand that this refers to that thing which is calling him **

So if this is being used inside the function and that function or method is inside an object then this refers to the that object itself

And if this is inside a regular function `exception in case of arrow function` then this refers to the global object (`window object in browser and global in Node JS`)

```js
const video = {
 title : 'a',
 play(){
  console.log(this)
 }
};

video.play();

//By this we are adding a property in the object
video.stop = function(){
 console.log(this);
}
```

Here in the above code since this is used inside a method which is an part of  video object so this refers to the video object.

And when we are adding a property inside the object so in this case if we call `video.stop()` here this will refer to video object

```js
function getName(){
 console.log(this)
}

getName()
```

Here when we are using this inside the regular function then in that case this is refering to the global object which is  `window object in browser and global in Node JS`



```js
function Video(title){
  this.title = title;
  console.log(this);
}

const v = new Video('uday');
```

In case of constructor function created using `new` keyword then this refers to newly created object which is `v` here because in case of new keyword it creates an empty object and made this point to empty object and by writing `this.title = title` we are basically adding property to this empty object created


When we refer to `this keyword`  in **node enviroment**  it refers  _`to the empty object`_  and when `this keyword` is refer in *browser*  it refers to the `global object`  which is _**Windows Object in browser**_

> In Node.js, `this` at the top level of a module (not inside any function or other context) refers to an empty object, not a global object like `window` in the browser. But when `this` is used inside a function or other context, it refers to that current context. ==*This behavior helps keep each module’s variables and functions separate from each other, preventing conflicts*== 



Sure, here are a few more situations where `this` in JavaScript might cause issues:

1. **Event Handlers**: In event handlers, `this` refers to the element that fired the event, not necessarily the object that the method belongs to.

```javascript
let button = document.querySelector('button');
button.addEventListener('click', video.showTags);  // 'this' inside 'showTags' will be 'button', not 'video'
```

2. **Nested Objects**: In nested objects, `this` inside a method refers to the innermost object.

```javascript
let nestedObject = {
  inner: {
    method: function() {
      console.log(this);  // 'this' will refer to 'inner', not 'nestedObject'
    }
  };
};
```

3. **Returning `this` from a Constructor**: If a constructor function returns an object, `this` will refer to that object, not the newly created object. If it returns a non-object, `this` will still refer to the new object.

```javascript
function MyObject() {
  this.value = "Hello";
  return { value: "Goodbye" };
}

let obj = new MyObject();
console.log(obj.value);  // "Goodbye", not "Hello"
```


Consider the below code 

```js
Const Video =  {
  title : 'a',
  tags : ['a' , 'b' , 'c'],
  showTags(){
    this.tags.forEach(function(tag){
      console.log(this.title ,tag)
    }, this)
  }
}
```

Here in this code `this inside the showTags` is refering to the *Video Object*. And `this inside forEach loop` function is _**not refering to Video Object instead it refering Global Object**_  so doing **this.title** will give error of `undefined` because _`title is not defined inside the global object`_

So if we want that `this.title` to refer to our Video Object then second argument of forEach comes in. If we pass this ( *refering to our video object* ) as the second argument it is like saying  `"Hey remember this inside the ForEach also refers to our video object"`

Consider the below code :

```js
 let title = 'uday';

const video = {
  title : 'a',
  tags : ['a' ,'b' ,'c'],
  showTags(){
    this.tags.forEach(function(tag) {
      console.log(this.title,tag);
    })
  }
}
 
video.showTags()
/* Output
  uday a
  uday b
  uday c

*/

```

>Since global variables in a browser are properties of the `window` object, `this.title` inside the `forEach` function will refer to the global `title` variable

So `this inside the forEach` function refers to the global object and doing `this.title` will give us result as `uday`

And if we write *this.title = "uday"*  in the place of *let title = 'uday'* we will also get the same output because writing `this.title = 'uday'`  this here is refering to the global object which is `window object`  and we are adding a property `title` to the window object. 