---
id: 587d7fb9367417b2b2512c12
title: Concatenare gli helper delle query per restringere i risultati di ricerca
challengeType: 2
forumTopicId: 301533
dashedName: chain-search-query-helpers-to-narrow-search-results
---

# --description--

If you don’t pass the callback as the last argument to `Model.find()` (or to the other search methods), the query is not executed. You can store the query in a variable for later use. This kind of object enables you to build up a query using chaining syntax. The actual db search is executed when you finally chain the method `.exec()`. You always need to pass your callback to this last method. There are many query helpers, here we'll use the most commonly used.

# --instructions--

Modifica la funzione `queryChain` per trovare persone a cui piace il cibo specificato dalla variabile denominata `foodToSearch`. Ordina per `name`, limita i risultati a due documenti e nascondi la loro età. Concatena `.find()`, `.sort()`, `.limit()`, `.select()`, e quindi `.exec()`. Passa la callback `done(err, data)` a `exec()`.

# --hints--

La concatenazione degli helper delle query dovrebbe avere successo

```js
  $.ajax({
    url: code + '/_api/query-tools',
    type: 'POST',
    contentType: 'application/json',
    data: JSON.stringify([
      { name: 'Pablo', age: 26, favoriteFoods: ['burrito', 'hot-dog'] },
      { name: 'Bob', age: 23, favoriteFoods: ['pizza', 'nachos'] },
      { name: 'Ashley', age: 32, favoriteFoods: ['steak', 'burrito'] },
      { name: 'Mario', age: 51, favoriteFoods: ['burrito', 'prosciutto'] }
    ])
  }).then(
    (data) => {
      assert.isArray(data, 'the response should be an Array');
      assert.equal(
        data.length,
        2,
        'the data array length is not what expected'
      );
      assert.notProperty(
        data[0],
        'age',
        'The returned first item has too many properties'
      );
      assert.equal(
        data[0].name,
        'Ashley',
        'The returned first item name is not what expected'
      );
      assert.notProperty(
        data[1],
        'age',
        'The returned second item has too many properties'
      );
      assert.equal(
        data[1].name,
        'Mario',
        'The returned second item name is not what expected'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

