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