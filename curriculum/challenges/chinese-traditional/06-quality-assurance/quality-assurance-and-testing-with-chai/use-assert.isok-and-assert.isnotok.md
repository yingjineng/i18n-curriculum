---
id: 587d824b367417b2b2512c48
title: 使用 Assert.isOk() 和 Assert.isNotOK()
challengeType: 2
forumTopicId: 301607
dashedName: use-assert-isok-and-assert-isnotok
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

`isOk()` 用來測試值是否爲真值，`isNotOk()` 用來測試值是否爲假值。

可以在<a href="https://chinese.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-algorithm-scripting/falsy-bouncer" target="_blank" rel="noopener noreferrer nofollow">過濾數組中的假值</a>這個挑戰中瞭解更多關於真值和假值的信息。

# --instructions--

在 `tests/1_unit-tests.js` 中，`Basic Assertions` 套件中標註爲 `#3` 的測試下，修改每個 `assert` 爲 `assert.isOk()` 或 `assert.isNotOk()`，通過測試（結果應爲 `true`）。 不要修改傳入斷言的參數。

# --hints--

應通過所有測試。

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

應該第一個斷言選擇正確的方法：`isOk` 或 `isNotOk`。

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

應該第二個斷言選擇正確的方法：`isOk` 或 `isNotOk`。

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

應該第三個斷言選擇正確的方法：`isOk` 或 `isNotOk`。

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

