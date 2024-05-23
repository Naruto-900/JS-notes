consider below both the code 

```
function addLanguage(langName){
       const li = document.createElement('li');

       li.innerHTML = langName;
       const parent = document.querySelector('.language');
       parent.appendChild(li);
    }

function OptimiseAddLanguage(langName){
        const li = document.createElement('li');
        li.appendChild(document.createTextNode(langName));
        document.querySelector('.language').appendChild(li);
    }
```

Here both the function are doing same thing that adding an li but `OptimisedAddLanguage`  is optimised as compare to `addLanguage` because the difference get's created **by adding text to the li element**.


- The `OptimiseAddLanguage` function may have a minor performance benefit as it bypasses the HTML parsing step involved with `innerHTML`.
- This performance gain is typically insignificant, particularly if `langName` doesn’t include complex HTML.
- `OptimiseAddLanguage` enhances security by using `createTextNode`, which can help prevent potential Cross-Site Scripting (XSS) vulnerabilities that could occur when setting `innerHTML` with user-generated content.


#### Edit the element 

Here one thing i notice that we can't simply replace the text of the element as we have done in the below code instead `what is happening that by doing that it is not replacing the text instead it is concatenating the text`


```
<body style="background-color: #212121; color: #fff;">

    <ul class="language">

        <li>JavaScript</li>

    </ul>

</body>

<script>

    function addLanguage(langName){
       const li = document.createElement('li');
       li.innerHTML = langName;
       const parent = document.querySelector('.language');
       parent.appendChild(li);
    }
    
    addLanguage('java');
    addLanguage('ruby');
    addLanguage('c++');

    function OptimiseAddLanguage(langName){

        const li = document.createElement('li');
        li.appendChild(document.createTextNode(langName));

        document.querySelector('.language').appendChild(li);
    }
    OptimiseAddLanguage('typescript');
    
    //Edit
    const secondLang = document.querySelector('li:nth-child(2)');
    secondLang.appendChild(document.createTextNode('Mojo'));
</script>
```


here in this code when we have selected the `secondLang` then in that case there are two option of replacing the text 


```js
//Option1
secondLang.innerHTML = "text"

//Option2
secondLang.textContent = "text"
```

Here if we are _dealing with text both will same result_ as they would replace the text but there is a `important difference` between them which is in case of innerHTML when we use it to replace the text it will replace the entire HTML code there although providing only text will only replace the text inside the html code but if we pass some thing like this

```js
 secondLang.innerHTML = "<li>text</li>"
```

it will replace the second lang with the above code although it will only display text as the older one is gone but internally it creates a new DOM nodes then  it replaces.

But in case of` option2 it treats it like raw text` so if we write something like this

```js
secondLang.textContent = "<li>text</li>"
```

 it will replace the second lang text with this entire HTML code so in place of text the entire code will be displayed.

So the best way of replacing : 

1. 
```js
 const newli = document.createElement('li');
 newli.appendChild(document.createTextNode(text));
 secondLang.replaceWith(newli);
```


2. 
```js
const newli = document.createElement('li');
newli.textContent = "text";
secondLang.replaceWith(newli);
```

One more way of replacing text of secondLang

```js
secondLang.textContent = "text";
```

Here one thing we must remember that `replaceWith` method replaces the entire element, not just its text content. If you want to replace only the text content, we can use the `textContent` property.