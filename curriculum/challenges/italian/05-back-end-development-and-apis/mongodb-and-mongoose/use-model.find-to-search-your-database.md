---
id: 587d7fb7367417b2b2512c0b
title: Usare model.find() per fare ricerche nel database
challengeType: 2
forumTopicId: 301543
dashedName: use-model-find-to-search-your-database
---

# --description--

In its simplest usage, `Model.find()` accepts a query document (a JSON object) as the first argument, then a callback. It returns an array of matches. It supports an extremely wide range of search options. Read more in the docs.

# --instructions--

Modifica la funzione `findPeopleByName` per trovare tutte le persone che hanno un dato nome, usando <code>Model.find() -\> [Person]</code>

Usa l'argomento `personName` della funzione come chiave di ricerca.

# --hints--

La ricerca di tutti gli elementi corrispondenti a un criterio dovrebbe avere successo

```js
  $.post(code + '/_api/find-all-by-name', {
    name: 'r@nd0mN4m3',
    age: 24,
    favoriteFoods: ['pizza']
  }).then(
    (data) => {
      assert.isArray(data, 'the response should be an Array');
      assert.equal(
        data[0].name,
        'r@nd0mN4m3',
        'item.name is not what expected'
      );
      assert.equal(data[0].__v, 0, 'The item should be not previously edited');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

