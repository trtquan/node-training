are functions that take 3 arguments: the requestion object, response object, and the next function in the application's request resoponse cycle

```
function(req, res, next) {
	next()
}
```

middleware can be mounted at a specific route using app.METHOD(path, middlewareFunc)

### Chain Middleware

Middleware can also be chained inside route definition

This approach is useful to split the server operations into smaller units. That leads to a better app structure, and the possibility to reuse code in different places. This approach can also be used to perform some validation on the data. At each point of the middleware stack you can block the execution of the current chain and pass control to functions specifically designed to handle errors. Or you can pass control to the next matching route, to handle special cases. We will see how in the advanced Express section.

