---
id: 587d7fb6367417b2b2512c07
title: 创建一个模型（Model）
challengeType: 2
forumTopicId: 301535
dashedName: create-a-model
---

# --description--

**C**RUD Part I - CREATE

首先，我们需要一个 Schema。 每一个 Schema 都对应一个 MongoDB 的 collection， 并且在相应的 collection 里定义 documents 的“样子”。 Schema 用于组成模型（Model）。 我们甚至可以通过嵌套 Schema 来创建复杂的模型。目前我们先从简。 我们可以根据模型创建实例，模型实例化后的对象称为 documents。

In servers, the interactions with the database happen in handler functions. 这些函数会在特定事件（比如有人调用了我们的服务器 API）发生时执行。 We'll follow the same approach in these exercises. `done()` 是一个回调函数，它的作用是在一个异步操作（比如对数据库进行插入、查询、更新或删除）执行完成时，通知我们可以继续执行后续的其它代码。 这与 Node.js 中的处理方式十分类似，在 Node.js 中，我们会在（异步操作）成功时调用 `done(null, data)`，在失败时调用 `done(err)`。

注意：与远程服务器进行交互时，我们需要考虑到发生错误的可能！

```js
/* Example */

const someFunc = function(done) {
  //... do something (risky) ...
  if (error) return done(error);
  done(null, result);
};
```

# --instructions--

按下面的信息创建一个名为 `personSchema` 的人员模式：

* A required `name` field of type `String`
* `age` 字段，类型为 `Number`
* `favoriteFoods` 字段，类型为 `[String]`

采用 Mongoose 基础 schema 类型。 你如果还想添加更多的键，就请使用 required 或 unique 等简单的验证器（validators），并设置默认值。 查看我们的 <a href="https://www.freecodecamp.org/news/introduction-to-mongoose-for-mongodb-d2a7aa593c57/" target="_blank" rel="noopener noreferrer nofollow">Mongoose 文章</a>。

现在，从 `personSchema` 创建一个模型，并将它分配给现有变量 `Person`。

# --hints--

应当成功地通过 Mongoose schema 创建实例

```js
  $.post(code + '/_api/mongoose-model', {
    name: 'Mike',
    age: 28,
    favoriteFoods: ['pizza', 'cheese']
  }).then(
    (data) => {
      assert.equal(data.name, 'Mike', '"model.name" is not what expected');
      assert.equal(data.age, '28', '"model.age" is not what expected');
      assert.isArray(
        data.favoriteFoods,
        '"model.favoriteFoods" is not an Array'
      );
      assert.include(
        data.favoriteFoods,
        'pizza',
        '"model.favoriteFoods" does not include the expected items'
      );
      assert.include(
        data.favoriteFoods,
        'cheese',
        '"model.favoriteFoods" does not include the expected items'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

