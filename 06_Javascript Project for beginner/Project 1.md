`.addEventListener` is a method which help us to listen to the event and will do the work after that after that event has occur.

Here event means anything happen inside the browser hovering the mouse ,closing the tab ,clicking on something

And the above method takes two argument first `type of event` and second `what should we do when this event happen or rather the callback function`. *And when the event happen we have to carry out the event as well*

#### Syntax for event listener

```
element.addEventListener(argument1,argument2);

//argument1 : type of event we want to listen
//argument2 : what should we do after this event i.e callback function
```

Consider this code
```
<body>

    <div class="canvas">
    
      <h1>Color Scheme Switcher</h1>

      <span class="button" id="grey"></span>
      <span class="button" id="white"></span>
      <span class="button" id="blue"></span>
      <span class="button" id="yellow"></span>
      
      <h2>
        Try clicking on one of the colors above
        <span>to change the background color of this page!</span>
      </h2>

    </div>

    <script src="ChaiaurCode.js"></script>
  </body>
```

Here if we want to apply event listener to span element with class button then in that case firstly we have to select that element and then apply event listener

```js
//This will give nodeList collection so we can use forEach loop
const myBtns = document.querySelectorAll('button');

myBtns.forEach((btn)=>{
   btn.addEventListener('click' ,function(event){
      console.log(event);
      console.log(event.target);
   })
})
```

>[!NOTE]
>Here the callback function inside the addEventListener will only be called only when the click event has happened
>
>1. `console.log(event);`: This line logs the entire event object to the console. The event object contains all the information about the click event, such as the target element, the type of the event, the time the event happened, and more.
>   
>   2. `console.log(event.target);`: This line tells us who initated the click event
