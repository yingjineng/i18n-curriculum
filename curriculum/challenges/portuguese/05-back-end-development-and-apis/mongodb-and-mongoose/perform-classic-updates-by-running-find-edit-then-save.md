---
id: 587d7fb8367417b2b2512c0e
title: 'Realizar atualizações clássicas executando Find, Edit e Save'
challengeType: 2
forumTopicId: 301541
dashedName: perform-classic-updates-by-running-find-edit-then-save
---

# --description--

In the good old days, this was what you needed to do if you wanted to edit a document, and be able to use it somehow (e.g. sending it back in a server response). Mongoose has a dedicated updating method: `Model.update()`. It is bound to the low-level mongo driver. It can bulk-edit many documents matching certain criteria, but it doesn’t send back the updated document, only a 'status' message. Furthermore, it makes model validations difficult, because it just directly calls the mongo driver.

# --instructions--

Modifique a função `findEditThenSave` para encontrar uma pessoa por `_id` (use qualquer um dos métodos acima) com o parâmetro `personId` como chave de pesquisa. Adicione `"hamburger"` à lista dos `favoriteFoods` da pessoa (você pode usar `Array.push()`). Em seguida, dentro do callback de find, use `save()` para salvar a `Person` atualizada.

**Observação:** isso pode ser complicado, se em seu Schema você declarou as `favoriteFoods` como um array, sem especificar o tipo (por exemplo, `[String]`). Nesse caso, `favoriteFoods` tem como padrão o tipo Mixed e você precisa marcá-lo manualmente como editado usando `document.markModified('edited-field')`. Veja nosso <a href="https://www.freecodecamp.org/news/introduction-to-mongoose-for-mongodb-d2a7aa593c57/" target="_blank" rel="noopener noreferrer nofollow">artigo sobre o Mongoose</a>.

# --hints--

Você deve ter sucesso em encontrar, editar e atualizar um item

```js
  $.post(code + '/_api/find-edit-save', {
    name: 'Poldo',
    age: 40,
    favoriteFoods: ['spaghetti']
  }).then(
    (data) => {
      assert.equal(data.name, 'Poldo', 'item.name is not what is expected');
      assert.equal(data.age, 40, 'item.age is not what expected');
      assert.deepEqual(
        data.favoriteFoods,
        ['spaghetti', 'hamburger'],
        'item.favoriteFoods is not what expected'
      );
      assert.equal(data.__v, 1, 'The item should be previously edited');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

