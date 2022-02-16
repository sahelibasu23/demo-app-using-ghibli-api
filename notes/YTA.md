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

### index.html
