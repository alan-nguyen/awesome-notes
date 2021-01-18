# Working with REST API's in JS
> By: Alan Nguyen

A REST API is a way of easily accessing web services. When a RESTful API is called, the server will transfer to the client a representation of the state of the requested resource. A RESTful API is stateless, separates concerns between client-server, allows caching of data client-side and it utilizes standardized base URLs and methods to perform the actions required to manipulate, add or delete data.
## A - JS REST APIs - The Big Picture

> taylonr.com 
### 1. Overview
- The REST design principles
- Acessing an API via a JS client
- Create an API via Node.js

### 2. How REST helps build applications

**#What is REST?**
- Representational State Transfer 

**#What is Resource?**
- Information transfered between clients and server 
- A client and server communicating about the state of the object 

**#Key contraints for REST**
- Client-Server architecture
  - Server - how to store data
  - Client - how to represent that data
- Stateless (all information needed to fulfill the request is sent by client each time)
- Cacheability 
- Layered (can be on a server that sits behind a load balancer or a proxy)
- Code on demand (API could return a block of JS that could be used to extend the client if necessary)
- Uniform interface (use uniform resource identifier - URIs)

Load balancer - can be responsible for sending request to servers

**#Communicating errors with response**
- Key points about status codes
  - can communicate with simple status codes
  - 404 - a client error
  - 4xx - client errors
    - 400 - bad request
    - 401 - un authorized
  - 5xx - server errors 
    - 500 - internal server error 
  
**#Communicating success with response**
- 2xx - Success
  - 200 OK
  - 201 - Created 
  - 204 - No content

**#Communicating with requests**

HTTP Verbs
- GET - asking the server to fetch data and send it back to the client
  - should only retrieve data
- POST - add a new object
- PUT - replaces the entire object
- PATCH - only update supplied fields 
- DELETE - remove a piece of data

**#Putting it all together**


### 3. Using JS with REST

**#Consuming REST with JS**

XML HTTP Request (XHR) Object
- A JS API to create AJAX requests
- provide the ability to send network requests between the browser and a server
- XHR can receive any type of data

**#Using Express to Create an API**
- a web framework, not just an API framework
```js
router.route("/products")
  .get((req, res) => {
    res.json(getProducts());
  })

  .post((req, res) => {
    res.json(createProduct(req));
  })
```
**#Using a Database with an API**
One common REST approach
| REST Request | Database |
| --- | --- |
| /products | Product table |
| GET | select * from products|

- Database Types
  - Relational
  - Document - MongoDB (JSON like)
  - Text files

## B - JS REST APIs - Getting Started

## C - Building CRUD Actions in a JS REST API

## D - Uploading Files with a JS REST API

## E - Securing a JS REST API with JSON Web Tokens

## F - Caching JS REST API Data with Local Storage