---
id: 587d7fb0367417b2b2512bed
title: 认识 Node 的控制台
challengeType: 2
forumTopicId: 301515
dashedName: meet-the-node-console
---

# --description--

Working on these challenges will involve you writing your code using one of the following methods:

- Clone <a href="https://github.com/freeCodeCamp/boilerplate-express/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete these challenges locally.
- 使用你选择的网站生成器来完成项目。 需要包含我们 GitHub 仓库的所有文件。

During the development process, it is important to be able to check what’s going on in your code.

Node is just a JavaScript environment. Like client side JavaScript, you can use the console to display useful debug information. On your local machine, you would see console output in a terminal.

We recommend to keep the terminal open while working at these challenges. By reading the output in the terminal, you can see any errors that may occur.

更改文件后必须重新启动服务器。

你可以使用 `Ctrl + C` 从终端停止服务器，然后直接使用 Node（`node mainEntryFile.js`）或使用 `package.json` 文件中的运行脚本 `npm run` 启动服务器。

例如，可以使用 `npm run start` 在终端运行 `"start": "node server.js"` 脚本。

要实现保存文件时服务器自动重启，你可以将 Node 的 `--watch` 标志添加到你的启动脚本 `"start": "node --watch server.js"`，或者你可以安装一个 npm 包，例如 `nodemon`。 我们将把这作为一项练习留给你。

# --instructions--

Modify the `myApp.js` file to log "Hello World" to the console.

# --hints--

`"Hello World"` should be in the console

```js
  $.get(code + '/_api/hello-console').then(
    (data) => {
      assert.isTrue(data.passed, '"Hello World" is not in the server console');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

