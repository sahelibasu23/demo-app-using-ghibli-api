# QUICK OVERVIEW

API stands for Application Program Interface, which can be defined as a set of methods of communication between various software components. 
In other words, an API allows software to communicate with another software.

We'll be focusing specifically on Web APIs, which allow a web server to interact with third-party software. 
In this case, the web server is using HTTP requests to communicate to a publicly available URL endpoint containing JSON data. 
If this is confusing now, it will make sense by the end of the tutorial.

You may be familiar with the concept of a CRUD app, which stands for Create, Read, Update, Delete. 
Any programming language can be used to make a CRUD app with various methods. 
A web API uses HTTP requests that correspond to the CRUD verbs.

| Action  | HTTP Method | Description 
| ------------- | ------------- | ------------- |
| Create  | POST  | Creates a new resource
| Read  | GET  | Retrieves a resource 
| Update  | PUT/PATCH  | Updates an existing resource 
| Delete  | DELETE  | Deletes a resource 

REST and RESTful APIs, is simply referring to a set of standards that conform to a specific architectural style. 
Most web apps do, or aim to conform to REST standards. 
Overall, there are a lot of terms, acronyms and concepts to understand - HTTP, API, REST - so it's normal to feel confused and frustrated, 
especially when API documentation assumes you already know what to do.

# SETTING UP
What is our objective? We want to get the data for all Studio Ghibli films and display the titles and descriptions in a grid. 
For some background knowledge, Studio Ghibli is a Japanese animation studio that produced several films, such as Spirited Away,etc.

We're going to start by creating an index.html file in a new directory. 
The project will only consist of index.html, style.css, and scripts.js at the end. 
This HTML skeleton just links to a CSS and JavaScript file, loads in a font, and contains a div with a root id. 
This file is complete and will not change. We'll be using JavaScript to add everything from here out.

#### index.html

```

```

Since this article is focused on the concepts of APIs and JavaScript, I will not be explaining how the CSS works. We will create a style.css that will be used to create a grid. 

#### style.css

```

```

# CONNECTING TO THE API
Let's take a look at the Studio Ghibli API documentation. This API was created to help developers learn how to interact with resources using HTTP requests, which is perfect for us here. Since an API can be accessed by many different methods - JavaScript, PHP, Ruby, Python and so on - the documentation for most APIs doesn't tend to give specific instructions for how to connect.

We can see from this documentation that it tells us we can make requests with curl or regular REST calls, but we might not have a clue how to do that yet.

# OBTAINING THE API ENDPOINT
To get started, let's scroll to the films section. On the right you'll see `GET /films`. It will show us the URL of our API endpoint, https://ghibliapi.herokuapp.com/films. Clicking on that link will display an array of objects in JSON.

If you do not have an extension on your browser for viewing JSON files, add one now, such as JSON View. This will make reading JSON much, much easier. Remember, if you've never worked with JSON, read this [prerequisite article]().

# RETRIEVING THE DATA WITH AN HTTP REQUEST
Before we try to put anything on the front end of the website, let's open a connection the API. We'll do so using XMLHttpRequest objects, which is a way to open files and make an HTTP request.

We'll create a request variable and assign a new XMLHttpRequest object to it. Then we'll open a new connection with the open() method - in the arguments we'll specify the type of request as GET as well as the URL of the API endpoint. The request completes and we can access the data inside the onload function. When we're done, we'll send the request.

#### scripts.js

```

```
Alternatively, you can use the fetch API and async/await.
```

```
# WORKING WITH THE JSON RESPONSE
Now we've received a response from our HTTP request, and we can work with it. However, the response is in JSON, and we need to convert that JSON in to JavaScript objects in order to work with it.

We're going to use JSON.parse() to parse the response, and create a data variable that contains all the JSON as an array of JavaScript objects. Using forEach(), we'll console log out the title of each film to ensure it's working properly.

Using Inspect on index.html and viewing the console, you should see the titles of 20 Ghibli films. Success!

The only thing we're missing here is some way to deal with errors. What if the wrong URL is used, or the URL broke and nothing was being displayed? When an HTTP request is made, the response returns with HTTP status codes. 404 is the most well-known response, meaning Not Found, and 200 OK is a successful request.

Let's just wrap our code in an if statement, succeeding on any response in the 200-300 range, and log out an error if the request fails. You can mess up the URL to test the error.

```

```
Here is the entire code so far.

```

```
We've successfully used a GET HTTP request to retrieve (or consume) the API endpoint, which consisted of data in JSON format. However, we're still stuck in the console - we want to display this data on the front end of the website, which we'll do by modifying the DOM.
