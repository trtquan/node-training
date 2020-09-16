Routing refers to how an application's endpoints (URIs) respond to client request


## Basic

Routing refers to determing how and application reponds to a client request to a particular endpoint, which is a URI (or path) and a specific HTTP request method (GET, POST, and so on)

Each rout can have one or more handler functions, which are executed when the route is matched
structure

```js
app.METHOD(PATH, HANDLER)
```

Where:

* app is an instance of express.
* METHOD is an HTTP request method, in lowercase.
* PATH is a path on the server.
* HANDLER is the function executed when the route is matche

The following examples illustrate defining simple routes.

Respond with Hello World! on the homepage:

```js
app.get('/', function(req, res) {
	res.send("Hello World!")
})
```

Respond to POST request on the root route (/), the application’s home page:

```js
app.post.('/', function(req, res) {
	res.send("Got a Post Request")
})
```

Respond to PUT request ro the `/user` route

```js
app.put('/user', function(req, res) {
	res.send("Got a Put request at /user")
})
```

Respond to a DELETE request to the /user route:

```js
app.delete('/user', function(req, res) {
	res.send("Got a Delete request at /user")
})
```

You can also use app.all() to handle all HTTP methods and app.use() to specify middleware as the callback function (See Using [Ex-Middleware] for details).

the application “listens” for requests that match the specified route(s) and method(s), and when it detects a match, it calls the specified callback function

In fact, the routing methods can have more than one callback function as arguments. With multiple callback functions, it is important to provide `next` as an argument to the callback function and then call next() within the body of the function to hand off control to the next callback

There is a special routing method, app.all(), used to load middleware functions at a path for all HTTP request methods. For example, the following handler is executed for requests to the route “/secret” whether using GET, POST, PUT, DELETE, or any other HTTP request method supported in the [[Http-Module]].

[[Route-Paths]]