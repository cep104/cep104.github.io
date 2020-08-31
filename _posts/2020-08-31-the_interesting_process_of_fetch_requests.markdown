---
layout: post
title:      "The interesting process of fetch requests"
date:       2020-08-31 04:08:09 +0000
permalink:  the_interesting_process_of_fetch_requests
---


 
Making my JavaScript project was a very long and difficult process for me. One thing that I was struggling with the most was fetch requests and making sure it would append to the DOM correctly. After my project review, I decided to dive a little deeper and challenge myself to make sure I understood all the steps of making a post request enough where I could explain it to someone else. 
When making a fetch request you need to pass in a URL as its first property and then there is a second property which is optional, however, this is where you can do things like make a post, patch or delete request instead of a get request. 

`fetch(`http://localhost:3000/movies`)`

Fetch is promised based which means you can use.then and .catch. A promise is very similar to how you would make a promise in real life. There are three ways a promise can end up it is completed, resolved, or failed/rejected. You make a statement and then something will happen. So in this case it's the fetch URL request that we are making the promise on. If the promise gets resolved, it will make something happen if it gets rejected the .catch will happen. When you put the first, .then for a fetch request it will return a response object. If you console.log the response you can see a bunch of information for example, the status number or your request, your body(all of your data), and if ok = true (which means that your promise is resolved and your fetch was successful).
Once your fetch is successful, you will chain another .then to view your body of data. The body of data isn't accessible directly from the response object. So to access the data, we need to call a method on it to convert the response to json since we are using json data. We do this by adding the .json( ) method on the response. This will then return another promise. We use .then again on the actual data. If you console.log the data you should see all the data you are trying to receive from the API. 

`.then(response => response.json( ) )
.then( data => console.log(data))` 

If you are just trying to get the data from the API, the next step is appending the data to your DOM through mapping or using a class constructer method. If you want to do more than just getting data there will be some extra steps you will need to take. First, we will talk about creating new data by using a post request. To make a post request the easiest and cleanest way to do this is by making an object and storing all the extra information you will need inside of it. You will then take this object and pass it as a second argument in your fetch request. The first thing you put in the object is the method you would like to use so in this case, it will be "POST". Then you will need to pass that data for your new object, you pass this information through the body key. If you just tried passing the data by itself, it wouldn't work, you would get your data back but it wont save the data properly. Fetch works by sending the data JSON so you need to make sure you JSON.stringify and actually stringify the object you are passing to the API. There is still one last step to make sure your object gets sent properly and created you have to add your headers. The headers tell fetch that you are passing it JSON. When making a Post fetch request in a function it is also important to remeber to pass an event into your function and adding the preventDefault method. This will prevent the typical submit action of opening a new page when submit is hit on the create action. 

```
const createMovie = (e) => {
e.preventDefault()

fetch(`${BASE_URL}/movies`, configObj)

const configObj = {
method:"POST",
headers: {
"Content-Type": "application/json",
"Accept": "application/json"
},
body: JSON.stringify({
img_src: img_src,
title: title,
description: description,
rating: rating,
list_id: list_id
})
}
```

To grab the data that you would like to post you can do this by making a form on your HTML page and using the values of the answers someone might make as the attributes for your new object by assigning it to a variable. 

HTML form:
```


Title: 


Description: 



Rating: 


Image: 





```
Assigning the variables in JavaScript in the create function: 
```
let title = e.target.title.value
let description = e.target.description.value
let rating = e.target.rating.value
let img_src = e.target.img_src.value
let listAttribute = e.target.parentElement.attributes[1].value
let list_id = parseInt(listAttribute)
```

Once you have your data working from the backend, it's time to append your new data to the DOM. To do this you want to create an HTML environment for your data to live and be shown. This can be achieved by either writing your HTML code right in the HTML or you can create it in your JavaScript document. 

```
const ul = document.querySelector(`div[data-id = '${movie.list_id}'] ol`)
const li = document.createElement('li')
const image = document.createElement('div')
const button = document.createElement('button')
const editButton = document.createElement('button')
const editFormContainer = document.createElement('div')
```

Once you have your elements created, you want to put goes inside of them and set some attributes as well. This can be accomplished by assigning the innerHTML, innerTEXT, or textContent. For setting an attribute to your element, you put two arguments. First argument is the type of attribute such as class or Id. The second argument will be the name of the newly formed attribute or the value. 

```
li.innerHTML = `

${movie.title}



Rating: ${movie.rating}/10



Description: ${movie.description}

`

image.innerHTML = ``

button.setAttribute('class', 'remove')
button.setAttribute('data-movie-id', movie.id)
editButton.setAttribute('data-movie-id', movie.id)
editButton.setAttribute('class', 'editButton')
li.setAttribute('data-id', movie.id)

button.innerHTML = 'Delete Movie'
editButton.innerHTML = 'Edit Movie'
```

Last you will need to append these newly formed elements with their new values to the DOM you do this by using the appendChild method where you apply it to the parent element and use the new child element as the argument. 

```
li.appendChild(image)
li.appendChild(button)
li.appendChild(editButton)
li.appendChild(editFormContainer)
ul.appendChild(li)
```

Once all of this is done, you should have been able to do a fetch request for creating a new object and be able to see it on your HTML page. It was a difficult process to really dive deep and explore step by step the stages of the fetch request, but now I feel like I have a full understanding of how fetch requests work and how to perform them.


