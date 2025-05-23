---
id: 5f8884f4c46685731aabfc41
title: 使用 无头浏览器 II 运行功能测试
challengeType: 2
forumTopicId: 301594
dashedName: run-functional-tests-using-a-headless-browser-ii
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

# --instructions--

在 `tests/2_functional-tests.js` 中，在 `'Submit the surname "Vespucci" in the HTML form'` 测试（`// #6`），自动执行以下操作：

1.  Fill in the form with the surname `Vespucci`
2.  Press the submit button

在 `pressButton` 回调中：

1.  Assert that status is OK `200`
2.  断言元素 `span#name` 中的文本是 `'Amerigo'`。
3.  断言元素 `span#surname` 元素中的文本是 `'Vespucci'`。
4.  断言有 `span#dates` 元素，它们的计数是 `1`。

不要忘记删除 `assert.fail()` 调用。

# --hints--

应通过所有测试。

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

应断言无头浏览器成功执行请求。

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'browser.success');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

应断言元素 `span#name` 中的文本是 `'Amerigo'`。

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'browser.text');
      assert.match(data.assertions[1].args[0], /('|")span#name\1/);
      assert.match(data.assertions[1].args[1], /('|")Amerigo\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

应断言元素 `span#surname` 中的文本是 `'Vespucci'`。

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[2].method, 'browser.text');
      assert.match(data.assertions[2].args[0], /('|")span#surname\1/);
      assert.match(data.assertions[2].args[1], /('|")Vespucci\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

应该断言元素 `span#dates` 存在，且它的值为 1。

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[3].method, 'browser.elements');
      assert.match(data.assertions[3].args[0], /('|")span#dates\1/);
      assert.equal(data.assertions[3].args[1], 1);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

