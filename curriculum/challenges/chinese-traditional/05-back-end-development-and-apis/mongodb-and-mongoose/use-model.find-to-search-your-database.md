---
id: 587d7fb7367417b2b2512c0b
title: 使用 model.find() 查詢數據庫
challengeType: 2
forumTopicId: 301543
dashedName: use-model-find-to-search-your-database
---

# --description--

In its simplest usage, `Model.find()` accepts a query document (a JSON object) as the first argument, then a callback. It returns an array of matches. It supports an extremely wide range of search options. Read more in the docs.

# --instructions--

修改 `findPeopleByName` 函數使用 <code>Model.find() -\> [Person]</code> 查詢所有給定名字的人。

請使用函數參數中的 `personName` 作爲搜索條件。

# --hints--

應成功地找到所有符合條件的數據

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

