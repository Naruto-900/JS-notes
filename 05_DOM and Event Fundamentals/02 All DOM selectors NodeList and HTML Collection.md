while writing class for a html element although we write `class="value"` but while making the DOM JS will understand it by `className not class`

So if we want to get the class of a given element then we will have to do this

```js
 document.getElementById('id').className // not .class
```

With the help of `getAttribute method` we can also _get_ the attribute of a given element like this

```js
document.getElementById('id').getAttribute('attribute name')
```

suppose if we want the class attribute of a given element with id equals title then in that case we can write

```js
document.getElementById('title').getAttribute('class')
//This will give us the class of that element
```


In the same way we can also set some attribute to a given element by using  `setAttribute method` by below syntax

```js
document.getElementById('id').setAttribute('a' ,'b')
```

where a is the attribute we want to set and b is the attribute value we want to give _and also we can give multiple attribute separated by space_

> One thing we must know is that when we are setting any attribute and `if that attribute exist already` in that element then in that case that attribute value will be get override


If we dont want to write  `document.getElementById('id')` multiple times then in that case we can store it in a variable for easy access like this

```js
const title = document.getElementById('id')
```


#### Accessing the content 

To access the content we can use  `.textContent` , `.innerHTML` , `.innerText`  all of them will give same result but there is difference between them


`.textContent`  : In this case it will display all the text including those which are hidden by some css property

`.innerText` : In this case it will display only that text which is visible

`.innerHTML` : In this case _**if there are some html also inside that element then it will give that html also**_

>[!NOTE]
>Difference between HTMLCollection and NodeList is : 
>- HTMLCollection will return multiple HTML element that will share some common properties such as having same class or tag name
>  
>  
>  
>- For example, if you’re building a photo gallery, you might use `getElementsByClassName` to select all the images in the gallery. This returns an HTMLCollection.If you add or remove images, the HTMLCollection automatically updates because it’s live.
>  
>  
>  Since in DOM all the elements are called as node so nodeList will return list of all the nodes which might not be the html elements

 The type of list you get, either NodeList or HTMLCollection, depends on the method you use to select elements from the DOM :

1. **HTMLCollection**: You get an HTMLCollection when you use methods like `getElementsByClassName`, `getElementsByTagName`, or `getElementsByName`. These methods return a live collection, meaning it automatically updates when the document changes.

```javascript
 // Returns HTMLCollection
let divs = document.getElementsByTagName('div');
```


2. **NodeList**: You get a NodeList when you use methods like `querySelectorAll`. This method returns a static NodeList, meaning it does not automatically update when the document changes. However, some other methods like `childNodes` return a live NodeList.

```javascript
let divs = document.querySelectorAll('div'); // Returns NodeList
```



- With the help of `querySelector method`  we can select element  with the help of css selector but **it will only select the first html element which will match the given css selector**  and if that element doesn't exist then in that case it will return `null`

```js
document.querySelector('.class')
document.querySelector('#id')
```

By `querySelector` it is only selecting first single element but if we want to select all the elements then in that case we can use `querySelectorAll method`

So while when we get either `NodeList or HTMLCollection` we can't do styling like below

```js
//Selecting the elements

//This will give a nodeList of all the li
const tempList = document.querySelectorAll('li')

tempList.style.color = 'red' //This will give TypeError
```

The above will give error because `inside tempList` it contains many elements so we have to tell which element we should style by writing `[index]`

```js
const tempList = document.querySelectorAll('li')

tempList[0].style.color = 'red' // Now it will style the color red
```

>[!HINT]
>To convert HTML collections into array we can use `Array.from()` and pass the HTMLCollection as the argument to the method and it will return an array


```html
 <div>

       <h1 class="heading 1">hello I'm H1</h1>

       <h2 class="heading 2">hello I'm H2</h2>

       <h3 class="heading 3">hello I'm H3</h3>

       <h4 class="heading 4">hello I'm H4</h4>

    </div>
```


Here in the above code if we want to filter out the heading tag which are having even class name then in that case we can follow the below step

1. Firstly we need to select all the headings and get either in `HTMLCollections`  or `NodeList`

```js
//Gives HTMLCollection
const HTMLCollection_arr = document.getElementsByClassName('heading')

  // Give NodeList
const NodeList_arr = document.querySelectorAll('.heading') 
```

If we try to console the either of them in that case we will get output like below

```
NodeList(4) [h1.heading.1, h2.heading.2, h3.heading.3, h4.heading.4]

HTMLCollection(4) [h1.heading.1, h2.heading.2, h3.heading.3, h4.heading.4]
```


Here `NodeList(4)`  or   `HTMLCollection(4)`  denotes there are 4 element in the collections and *depending upon whether it is HTMLCollection or NodeList the elements will be HTML elements or nodeList*

Let’s take `h1.heading.1` as an example:

- `h1` is the HTML tag name of the element.
- `.heading.1` represents the class names of the `h1` element. It means this `h1` element has two classes, “heading” and “1”.

So, `h1.heading.1` represents an `h1` HTML element with the classes “heading” and “1”. The same goes for the other elements in the collection.


So depending upon whether we have choosen collection as HTMLCollection or nodeList we can traverse accordingly in the list. But if we choose `HTMLCollection` then in that case we can't *directly traverse because it is not an pure array* firstlty we have to convert it to array then we could traverse

And if we have choosen NodeList then in that case we will get the support of `forEach` so using that we can do traversal.

> And if we want to convert `HTMLCollection` to array we can use couple of methods which are
>- using Array.from(HTMLCollection) it will return a array then we could use all the features of array


So we will try with the NodeList using it's forEach then to _**filter out element with even class name we can write the following code**_

```js
NodeList_arr.forEach((item) => {
    let headingClass = item.className
    if(Number(headingClass.split(' ')[1]) % 2 == 0) console.log(item);
});

//Output 
<h2 class="heading 2">hello I'm H2</h2>
<h4 class="heading 4">hello I'm H4</h4>
```


Here we are calling each HTML element a item and doing 
` let headingClass = item.className` we are extracting class Name of the element which we will get as *heading 2* or *heading 1* or *heading 3* etc.

so after storing it in headingClass our next task is to extract the digit present in the string so for that we can do is firstly we **will split given headingClass which is a string into array on the basis of  '   ' by using headinClass.split('   ')**    so we will got our array as `[heading , 2]`

Since we got the array so we can easily access the number by doing *headingClass.split(' ')[1]*  we will got `2`. But one thing we have to take care that we got string not an actual number so we will have to convert it to number by wrapping it inside Number function as
`Number(headingClass.split(' ')[1])` 


>[!HINT]
>The above can also be done with the help of `filter` but for that firstly we have to convert it to array

