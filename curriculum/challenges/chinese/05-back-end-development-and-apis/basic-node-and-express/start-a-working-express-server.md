---
id: 587d7fb0367417b2b2512bee
title: 启动一个 Express 服务
challengeType: 2
forumTopicId: 301519
dashedName: start-a-working-express-server
---

# --description--

In the first two lines of the file `myApp.js`, you can see how easy it is to create an Express app object. This object has several methods, and you will learn many of them in these challenges. One fundamental method is `app.listen(port)`. It tells your server to listen on a given port, putting it in running state. For testing reasons, we need the app to be running in the background so we added this method in the `server.js` file for you.

让我们在服务端输出第一个字符串！ 在 Express 中，路由采用这种结构：`app.METHOD(PATH, HANDLER)`， METHOD 是 http 请求方法的小写形式， PATH 是服务器上的相对路径（它可以是一个字符串，甚至可以是正则表达式）， HANDLER 是匹配路由时 Express 调用的函数， 处理函数采用这种形式：`function(req, res) {...}`，其中 req 是请求对象，res 是响应对象， 例如：

```js
function(req, res) {
  res.send('Response String');
}
```

将会响应一个字符串“Response String”。

# --instructions--

当 GET 请求 `/`（根路由 ）时，使用 `app.get()` 方法响应一个“Hello Express”字符串。 Be sure that your code works by looking at the logs.

**注意：** 这些课程的所有代码应该放在开始给出的几行代码之间。

# --hints--

应用应该返回字符串“Hello Express”

```js
  $.get(code).then(
    (data) => {
      assert.equal(
        data,
        'Hello Express',
        'Your app does not serve the text "Hello Express"'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

