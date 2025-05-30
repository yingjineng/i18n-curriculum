---
id: 587d7fb8367417b2b2512c11
title: 使用 model.remove() 刪除多個 document
challengeType: 2
forumTopicId: 301538
dashedName: delete-many-documents-with-model-remove
---

# --description--

`Model.remove()` is useful to delete all the documents matching given criteria.

# --instructions--

修改 `removeManyPeople` 函數，使用 `nameToRemove` 刪除所有姓名是變量 `Model.remove()` 的人。 給它傳入一個帶有 `name` 字段的查詢 document 和一個回調函數。

**注意：** `Model.remove()` 不會返回被刪除的 document，而是會返回一個包含操作結果以及受影響的數據數量的 JSON 對象。 不要忘記將它傳入 `done()` 回調函數，因爲我們需要在挑戰的測試中調用它。

# --hints--

應一次性成功刪除多條數據

```js
  $.ajax({
    url: code + '/_api/remove-many-people',
    type: 'POST',
    contentType: 'application/json',
    data: JSON.stringify([
      { name: 'Mary', age: 16, favoriteFoods: ['lollipop'] },
      { name: 'Mary', age: 21, favoriteFoods: ['steak'] }
    ])
  }).then(
    (data) => {
      assert.isTrue(!!data.ok, 'The mongo stats are not what expected');
      assert.equal(
        data.n,
        2,
        'The number of items affected is not what expected'
      );
      assert.equal(data.count, 0, 'the db items count is not what expected');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

