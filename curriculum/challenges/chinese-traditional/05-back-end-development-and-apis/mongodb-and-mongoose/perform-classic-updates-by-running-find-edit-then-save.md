---
id: 587d7fb8367417b2b2512c0e
title: '通過執行查詢、編輯、保存來執行經典更新流程'
challengeType: 2
forumTopicId: 301541
dashedName: perform-classic-updates-by-running-find-edit-then-save
---

# --description--

In the good old days, this was what you needed to do if you wanted to edit a document, and be able to use it somehow (e.g. sending it back in a server response). Mongoose has a dedicated updating method: `Model.update()`. It is bound to the low-level mongo driver. It can bulk-edit many documents matching certain criteria, but it doesn’t send back the updated document, only a 'status' message. Furthermore, it makes model validations difficult, because it just directly calls the mongo driver.

# --instructions--

在這個挑戰中，請使用參數 `personId` 作爲字段，修改 `findEditThenSave` 方法，以在數據庫中通過 `_id` 找到相應的 person（你可以使用之前挑戰中的任何一種方法）。 將 `"hamburger"` 添加到它的 `favoriteFoods` 清單中（你可以使用 `Array.push()`）。 然後，在查詢數據庫的方法的回調裏通過 `save()` 方法更新 `Person` 的數據。

**提示：** 如果你在 Schema 中將 `favoriteFoods` 聲明爲一個 Array（數組）並且沒有指定數組的類型(如 `[String]`)， 那麼此時，`favoriteFoods` 就會是默認的 Mixed 類型。如果想編輯它，就必須執行 `document.markModified('edited-field')`。 查看我們的 <a href="https://www.freecodecamp.org/news/introduction-to-mongoose-for-mongodb-d2a7aa593c57/" target="_blank" rel="noopener noreferrer nofollow">Mongoose 文章</a>。

# --hints--

應成功地對一條數據進行查找、編輯和更新

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

