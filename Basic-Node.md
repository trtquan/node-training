One fundamental method is `app.listen(port)`

 It tells your server to listen on a given port, putting it in running state. You can see it at the bottom of the file. It is inside comments because, for testing reasons, we need the app to be running in the background. All the code that you may want to add goes between these two fundamental parts. Repl.it stores the port number in the environment variable `process.env.PORT`. Its value is `3000`.
 
 Node.js listening mean it's mean the server is on and waiting for different computers come and request information
 
 Let’s serve our first string! In Express, routes takes the following structure: `app.METHOD(PATH, HANDLER)`
 
 `METHOD` is an http method in lowercase. `PATH` is a relative path on the server (it can be a string, or even a regular expression). HANDLER is a function that Express calls when the route is matched.

Handlers take the form function(req, res) {...}, where req is the request object, and res is the response object

```js
function(req, res) {
  res.send('Response String');
}
```


We recommend you to use the Node global variable __dirname to calculate the path like this:
```js
absolutePath = __dirname + relativePath/file.ext
```