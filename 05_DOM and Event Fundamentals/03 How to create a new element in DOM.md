```
 <div class="parent">

        <div class="day 🚫🙅🏼NONVEG">Monday</div>

        <div class="day 🚫🙅🏼NONVEG">Tuesday</div>

        <div class="day">Wednesday</div>

        <div class="day">Thrusday</div>

    </div>
```

```js
 const parent = document.querySelector('.parent')
 console.log(parent.children)
 console.log(parent.children[0])
```

Here by doing `parent.children` it will display all the direct children of div with class parent. And it will return a array containing all the children so to access them we can use indexing.

If we want that we should select those div's or days in which we don't eat non-veg then in that case we can use the below code


```js
const parent = document.querySelector('.parent')
const childArray = Array.fromt(parent.children)

childArray.filter((item) => {

    let className = item.className;
    
    if(className.split(' ')[1] === '🚫🙅🏼NONVEG') {
        console.log(item.innerHTML)
        item.style.color = 'red'
    }
 })
```


We can also access the first or last child of the parent using `parent.firstChildElement`  and `parent.lastElementChild`. So they will give output like this

```
console.log(parent.firstElementChild) // <div class="day 🚫🙅🏼NONVEG">Monday</div>

console.log(parent.lastElementChild) <div class="day 🚫🙅🏼NONVEG">Thrusday</div>

```


Suppose if we have the first child of a given parent  and if we want to select the parent element then in that case again using querySelector is not a good idea because `it's a costly operation as it's scan the whole DOM Tree and try to find element with given selector`. So instead what we can do is

```js
 const firstChild = document.querySelector('.day');

  //By this we are accessing the parent 
  console.log(firstChild.parentElement)

 //By this we are accessing the next sibling
 console.log(firstChild.nextElementSibling)
```


#### Interesting thing
`parent.children` is a way to access all the direct children of an element in your HTML document.

In JavaScript, `parent.childNodes` returns a `NodeList` containing all the direct child nodes of the `parent` node.

So if we try to print the nodeList a weird (as i don't know about it) thing happen below :

```js
console.log(`NODES : ${Array.from(parent.childNodes)}`); //Output1
console.log("NODES",parent.childNodes) // Output2
```

In case of output1 we will get `NODES : [object NodeList]` and in case of output2

we will get `NodeList(9) [text, div.day.🚫🙅🏼NONVEG, text, div.day.🚫🙅🏼NONVEG, text, div.day, text, div.day, text]`  i.e the entire content of the nodeList

 Using string interpolation (template literals) with `NodeList` objects in JavaScript will not display the contents of the `NodeList`. Instead, it will return `[object NodeList]` because the `toString()` method for `NodeList` objects returns this string.


>[!NOTE]
>Here by doing `parent.childNodes` if we except to get all the children of the parent then we are not 100% right because in this case what browser does behind the scene is  [Explanation](https://youtu.be/xAvTgCsCHLs?si=tjElPlWVqpyOhtDa&t=796)



<hr>


If we want to create element in DOM we can take the help of `.createElement` and provide the element as string to the method

```js
const div = document.createElement('div')
```

 And if we want to add class name and id to the above div we can do that by using (`.className and .id`)  and (`.setAttribute()`)


But by above it will not be displayed in the screen because it is **being present in the memory and is not attached to the DOM** but still we can manipulate this but the changes will not be get reflected in the screen.

And if we want to add some content inside the div then we have two choices to do that 

```js
div.innerText = "Chai aur code" // Option1

const addText = document.createTextNode('Chai aur Code') //Option2
div.appendChild(addText)
```

In case of option1 what it is doing is that it firstly get the refernce of that place where we want to override the text and then it override the value.

But in case of option2 it first create a text node with value `Chai aur Code` and then it appends in that div

So by both the option it is taking 2 steps to do that so it's a debatable topic which one is better

>[!NOTE]
>The `document.createTextNode()` method creates a new text node, and text nodes in the DOM do not have a `style` property. The `style` property is available on element nodes, not text nodes. That’s why you’re getting a `TypeError` when you try to set `addText.style.color`.

