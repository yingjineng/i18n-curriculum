---
id: 587d7fb0367417b2b2512bef
title: 提供 HTML 文件服务
challengeType: 2
forumTopicId: 301516
dashedName: serve-an-html-file
---

# --description--

You can respond to requests with a file using the `res.sendFile(path)` method. You can put it inside the `app.get('/', ...)` route handler. Behind the scenes, this method will set the appropriate headers to instruct your browser on how to handle the file you want to send, according to its type. Then it will read and send the file. This method needs an absolute file path. We recommend you to use the Node global variable `__dirname` to calculate the path like this:

```js
absolutePath = __dirname + '/relativePath/file.ext'
```

# --instructions--

发送文件 `/views/index.html` 作为 `/` 的 GET 请求的响应。 如果实时查看应用，你会看到一个大的 HTML 标题（以及我们稍后将使用的表单……），目前它们还没有任何样式。

**注意：** 你可以编辑上一个挑战的解题代码，或者创建一个新的代码片段。 如果你创建一个新的代码片段，请记住 Express 会从上到下匹配路由，并执行第一个匹配的处理程序， 你必须注释掉前面的代码，否则服务器还是响应之前的字符串。

# --hints--

应用应该响应 views/index.html 文件

```js
  $.get(code).then(
    (data) => {
      assert.match(
        data,
        /<h1>.*<\/h1>/,
        'Your app does not serve the expected HTML'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

