
If we want to select a element in JS we can use the following syntax

```js
  // For selecting through class name
  document.querySelector('.class name')

 // For selecting through id 
 document.querySelector('#id')
```

And if we want to select the text content of that element then we can use `.textContent` as below

```js
document.querySelector('.message').textContent
```

How these work is `document.querySelector('.message')` represent the element and *.textContent* represent text inside that element

>[!NOTE]
>In case of multiple dot operator then they are executed from left to right
>_document.querySelector('.class')_ will be done first then `.textContent` will get performed
 

#### What's DOM and DOM manipulation


In the context of web development and JavaScript, `document` is a built-in object that represents the webpage. It acts as an entry point to the web page’s content, which is also known as the Document Object Model (DOM).


_`DOM manipulation`_ is nothing but making JS interactive with the web page

And `DOM` stands for `Document Object Model` and is a structured representation of of HTML document and allows us to manipulate them using JS

DOM and DOM methods are part of something called as `Web API`  


**JavaScript** is a programming language that you can use to make web pages interactive. It’s like the director of a play, telling the actors (HTML elements) what to do and when.

**DOM** (Document Object Model), on the other hand, is a representation of your web page that JavaScript can understand and interact with. It’s like the script of the play, describing the actors and the stage (HTML elements and their structure).


So with the help of `script` director can direct the movie so it can be engaging 

<hr>

#### Selecting and Manipulating Elements

```js
document.querySelector('.message').textContent = 'value'
```

With the help of above code we can also change the content  like above and above is called as **DOM Manipulation , where we have manipulated the content of the web page**


If we want to manipulate the input data which we recieved from the user we can use the following syntax

```js
document.querySelector('selector').value = value to be given
```

Here selector means either we have to provide the id or class name


#### Handling Click Events

Event means when something happens as a result of doing something in webpage and handeling this we require `Event Listeners`

To do this firstly we need to select that thing through which event can happen

```js
target.addEventListener(type, listener, options);
```

where ,

`target` is the object to which the event is sent.
`type` is a string representing the event type to listen for (like ‘click’, ‘mouseover’, etc.)
`listener` is the function to be called when the event occurs

 
