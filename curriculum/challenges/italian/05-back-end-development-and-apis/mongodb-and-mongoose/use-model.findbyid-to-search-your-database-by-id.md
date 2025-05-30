---
id: 587d7fb7367417b2b2512c0d
title: Usare model.findById() per cercare nel database in base all'_id
challengeType: 2
forumTopicId: 301544
dashedName: use-model-findbyid-to-search-your-database-by-id
---

# --description--

When saving a document, MongoDB automatically adds the field `_id`, and set it to a unique alphanumeric key. Searching by `_id` is an extremely frequent operation, so Mongoose provides a dedicated method for it.

# --instructions--

Modifica il `findPersonById` per trovare l'unica persona che abbia un certo `_id` utilizzando `Model.findById() -> Person`. Usa l'argomento `personId` della funzione come chiave di ricerca.

# --hints--

La ricerca di un elemento per Id dovrebbe avere successo

```js
  $.get(code + '/_api/find-by-id').then(
    (data) => {
      assert.equal(data.name, 'test', 'item.name is not what expected');
      assert.equal(data.age, 0, 'item.age is not what expected');
      assert.deepEqual(
        data.favoriteFoods,
        ['none'],
        'item.favoriteFoods is not what expected'
      );
      assert.equal(data.__v, 0, 'The item should be not previously edited');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

