---
id: 587d824b367417b2b2512c49
title: 測試真實性
challengeType: 2
forumTopicId: 301596
dashedName: test-for-truthiness
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

`isTrue()` 僅當給出的值爲 Boolean 的 `true` 時可以通過測試；`isNotTrue()` 則會在給出除 `true` 以外的值時通過測試。

```js
assert.isTrue(true, 'This will pass with the boolean value true');
assert.isTrue('true', 'This will NOT pass with the string value "true"');
assert.isTrue(1, 'This will NOT pass with the number value 1');
```

`isFalse()` 和 `isNotFalse()` 同樣存在，與上面提到的兩個方法類似，只不過它們針對值爲 `false` 的布爾值。

# --instructions--

Within `tests/1_unit-tests.js` under the test labeled `#4` in the `Basic Assertions` suite, change each `assert` to either `assert.isTrue` or `assert.isNotTrue` to make the test pass (should evaluate to `true`). 不要修改傳入斷言的參數。

# --hints--

應通過所有測試。

```js
  $.get(code + '/_api/get-tests?type=unit&n=3').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

應該爲第一個斷言選擇正確的方法：`isTrue` 或 `isNotTrue`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=3').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'isTrue', 'True is true');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

應該爲第二個斷言選擇正確的方法：`isTrue` 或 `isNotTrue`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=3').then(
    (data) => {
      assert.equal(
        data.assertions[1].method,
        'isTrue',
        'Double negation of a truthy value is true'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

應該爲第三個斷言選擇正確的方法：`isTrue` 或 `isNotTrue`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=3').then(
    (data) => {
      assert.equal(
        data.assertions[2].method,
        'isNotTrue',
        'A truthy object is not true - neither is a false one'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

