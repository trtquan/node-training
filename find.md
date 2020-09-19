Finds documents.

Mongoose casts the filter to match the model's schema before the command is sent. See our query casting tutorial for more information on how Mongoose casts filter.

```js
// find all documents
await MyModel.find({});

// find all documents named john and at least 18
await MyModel.find({ name: 'john', age: { $gte: 18 } }).exec();

// executes, passing results to callback
MyModel.find({ name: 'john', age: { $gte: 18 }}, function (err, docs) {});

// executes, name LIKE john and only selecting the "name" and "friends" fields
await MyModel.find({ name: /john/i }, 'name friends').exec();

// passing options
await MyModel.find({ name: /john/i }, null, { skip: 10 }).exec();
```

### Model.findById()
Parameters
* id «Any» value of _id to query by
* \[projection\] «Object|String|Array\<String\>» optional fields to return, see Query.prototype.select()
* \[options\] «Object» optional see Query.prototype.setOptions()
* \[callback\] «Function»
Returns:
* *«Query»
Finds a single document by its _id field. findById(id) is almost* equivalent to findOne({ _id: id }). If you want to query by a document's _id, use findById() instead of findOne().

The id is cast based on the Schema before sending the command.

This function triggers the following middleware.

* findOne()
* Except for how it treats undefined. If you use findOne(), you'll see that findOne(undefined) and findOne({ _id: undefined }) are equivalent to findOne({}) and return arbitrary documents. However, mongoose translates findById(undefined) into findOne({ _id: null }).

Example:

```js
// Find the adventure with the given `id`, or `null` if not found
await Adventure.findById(id).exec();

// using callback
Adventure.findById(id, function (err, adventure) {});

// select only the adventures name and length
await Adventure.findById(id, 'name length').exec();
```