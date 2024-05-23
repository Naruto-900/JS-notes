The main sources of data are 

1. *From the program itself* : Data written directly in the source code (e.g status message)
2. *From the UI* : Data input from the user or data written in DOM (e.g task in todo app)
3. *From external sources* : Data fetched for example from web API 


![[Drawing 2024-04-24 23.32.29.excalidraw 1.png]]


# Arrays vs. Sets and Objects vs. Maps


## Array vs. Sets

  We can use arrays and set when it's `not important to describe the values`

#### We can use arrays when

- When we need to have _**ordered**_ list of values (might contain duplicates);
- Use when we need to _**manipulate**_ data because there are ton of useful array methods


#### We can use sets when

- When we need to work with _**unique**_ values

- When _**high performance**_ is really important because searching and finding is very much fast in set

- When we want to _**remove duplicates**_ from array

<hr>


## Objects vs. Map

We can use map or object when we want to `store some infromation regarding values in the form of key and values`

#### We can use objects when

- More traditional key/value store 
- Easier to write and access values with `.` and `[]`
- Use when we need to include _**functions**_ (methods)
- Use when working with JSON ( can convert to map)


#### We can use maps when

- Better performance
- Keys can be of any type
- Easy to iterate
- Easy to compute size
- Use when we simply need to map key and values
- Use when we need keys that are not strings