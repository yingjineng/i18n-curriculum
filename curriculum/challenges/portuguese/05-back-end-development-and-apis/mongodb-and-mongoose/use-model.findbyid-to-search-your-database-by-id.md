---
id: 587d7fb7367417b2b2512c0d
title: Usar model.findById() para procurar no seu banco de dados por _id
challengeType: 2
forumTopicId: 301544
dashedName: use-model-findbyid-to-search-your-database-by-id
---

# --description--

When saving a document, MongoDB automatically adds the field `_id`, and set it to a unique alphanumeric key. Searching by `_id` is an extremely frequent operation, so Mongoose provides a dedicated method for it.

# --instructions--

Modifique `findPersonById` para encontrar a única pessoa com um `_id` dado, usando `Model.findById() -> Person`. Use o argumento `personId` da função como chave de pesquisa.

# --hints--

Você deve ter sucesso em encontrar um item por Id

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

