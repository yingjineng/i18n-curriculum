---
id: 587d824f367417b2b2512c59
title: 使用 Chai-HTTP II 在 API 端上运行功能测试
challengeType: 2
forumTopicId: 301592
dashedName: run-functional-tests-on-api-endpoints-using-chai-http-ii
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

# --instructions--

在 `tests/2_functional-tests.js` 中，修改 `'Test GET /hello with your name'` 测试（`// #2`），对响应的 `status` 和 `text` 使用断言来通过测试。

通过将 `?name=<your_name>` 附加到路由，将你的姓名作为 URL 查询发送。 端点响应 `'hello <your_name>'`。

# --hints--

应通过所有测试。

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

应该测试 `res.status` 为 200

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'equal');
      assert.equal(data.assertions[0].args[0], 'res.status');
      assert.equal(data.assertions[0].args[1], '200');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

应该测试 `res.text` == `'hello <your_name>'`

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'equal');
      assert.equal(data.assertions[1].args[0], 'res.text');
      assert.match(data.assertions[1].args[1], /hello [\w\d_-]/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

