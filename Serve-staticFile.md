To serve static files such as images, CSS files, and JavaScript files, use the express.static built-in middleware function in Express.

The function signature is:


```js
express.static(root, [options])
```

The root argument specifies the root directory from which to serve static assets. For more information on the options argument, see express.static.

For example, use the following code to serve images, CSS files, and JavaScript files in a directory named public:

```js
app.use(express.static('public'))
```

http://localhost:3000/images/kitten.jpg
http://localhost:3000/css/style.css
http://localhost:3000/js/app.js
http://localhost:3000/images/bg.png
http://localhost:3000/hello.html

>Express looks up the files relative to the static directory, so the name of the static directory is not part of the URL.

To use multiple static assets directories, call the express.static middleware function multiple times:

