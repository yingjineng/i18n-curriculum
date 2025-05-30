---
id: 587d7fb7367417b2b2512c0c
title: Usar model.findOne() para retornar um único documento correspondente a partir do seu banco de dados
challengeType: 2
forumTopicId: 301545
dashedName: use-model-findone-to-return-a-single-matching-document-from-your-database
---

# --description--

`Model.findOne()` behaves like `Model.find()`, but it returns only one document (not an array), even if there are multiple items. It is especially useful when searching by properties that you have declared as unique.

# --instructions--

Modifique a função `findOneByFood` para encontrar apenas uma pessoa que tenha uma certa comida nos seus favoritos, usando o modelo `Model.findOne() -> Person`. Use o argumento `food` da função como chave de pesquisa.

# --hints--

Você deve ter sucesso em encontrar um item

```js
  $.post(code + '/_api/find-one-by-food', {
    name: 'Gary',
    age: 46,
    favoriteFoods: ['chicken salad']
  }).then(
    (data) => {
      assert.equal(data.name, 'Gary', 'item.name is not what expected');
      assert.deepEqual(
        data.favoriteFoods,
        ['chicken salad'],
        'item.favoriteFoods is not what expected'
      );
      assert.equal(data.__v, 0, 'The item should be not previously edited');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

