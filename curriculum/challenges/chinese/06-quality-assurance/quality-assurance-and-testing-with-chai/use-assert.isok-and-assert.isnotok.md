---
id: 587d824b367417b2b2512c48
title: 使用 Assert.isOk() 和 Assert.isNotOK()
challengeType: 2
forumTopicId: 301607
dashedName: use-assert-isok-and-assert-isnotok
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

`isOk()` 用来测试值是否为真值，`isNotOk()` 用来测试值是否为假值。

可以在<a href="https://chinese.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-algorithm-scripting/falsy-bouncer" target="_blank" rel="noopener noreferrer nofollow">过滤数组中的假值</a>这个挑战中了解更多关于真值和假值的信息。

# --instructions--

在 `tests/1_unit-tests.js` 中，`Basic Assertions` 套件中标注为 `#3` 的测试下，修改每个 `assert` 为 `assert.isOk()` 或 `assert.isNotOk()`，通过测试（结果应为 `true`）。 不要修改传入断言的参数。

# --hints--

应通过所有测试。

```js
  $.get(code + '/_api/get-tests?type=unit&n=2').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

应该第一个断言选择正确的方法：`isOk` 或 `isNotOk`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=2').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'isNotOk', 'Null is falsy');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

应该第二个断言选择正确的方法：`isOk` 或 `isNotOk`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=2').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'isOk', 'A string is truthy');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

应该第三个断言选择正确的方法：`isOk` 或 `isNotOk`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=2').then(
    (data) => {
      assert.equal(data.assertions[2].method, 'isOk', 'true is truthy');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

