Model.create()
Parameters
docs «Array|Object» Documents to insert, as a spread or array
[options] «Object» Options passed down to save(). To specify options, docs must be an array, not a spread.
[callback] «Function» callback
Returns:
«Promise»
Shortcut for saving one or more documents to the database. MyModel.create(docs) does new MyModel(doc).save() for every doc in docs.

This function triggers the following middleware.

save()
Example:

```js
// Insert one new `Character` document
await Character.create({ name: 'Jean-Luc Picard' });

// Insert multiple new `Character` documents
await Character.create([{ name: 'Will Riker' }, { name: 'Geordi LaForge' }]);

// Create a new character within a transaction. Note that you **must**
// pass an array as the first parameter to `create()` if you want to
// specify options.
await Character.create([{ name: 'Jean-Luc Picard' }], { session });
```

Model.createCollection()
Parameters
[options] «Object» see MongoDB driver docs
[callback] «Function»
Create the collection for this model. By default, if no indexes are specified, mongoose will not create the collection for the model until any documents are created. Use this method to create the collection explicitly.

Note 1: You may need to call this before starting a transaction See https://docs.mongodb.com/manual/core/transactions/#transactions-and-operations

Note 2: You don't have to call this if your schema contains index or unique field. In that case, just use Model.init()

Example:
```js
const userSchema = new Schema({ name: String })
const User = mongoose.model('User', userSchema);

User.createCollection().then(function(collection) {
  console.log('Collection is created!');
});
```