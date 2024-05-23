Here we would learn about submit event

To stop the default behaviour of form we can write the below code
```js
myForm.addEventListener('submit',function(event){

  //To stop the default behaviour of submitting the form
  event.preventDefault(); // right way
  myForm.preventDefault(); // wrong way
})
```

Here  doing `myForm.preventDefault()` is wrong way because it means *we are stopping the form itself to submit*. But `preventDefault() is a method object`  i.e means we want that when that event occurs it should not submit the form


- The `elements` property of a form returns an **HTMLFormControlsCollection** of all the form controls contained in the form

```js
const myFormElements = myForm.element
```

Since the above is array (Not true one) so if we want to select the element we have to write like this

```js
const element = myFormElements['name']

//Where name is the name given to the input field
```

The modern way to check if a given number is `NaN` or not according to modern JS Syntax is
`
```js
 if(isNaN(number)) print('Given number is NaN')
 print('Given number is not NaN')
```

