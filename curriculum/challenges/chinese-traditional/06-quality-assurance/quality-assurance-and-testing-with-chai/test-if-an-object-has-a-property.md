---
id: 587d824e367417b2b2512c55
title: 測試對象是否具有某個屬性
challengeType: 2
forumTopicId: 301604
dashedName: test-if-an-object-has-a-property
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

`property` 斷言一個對象含有給定屬性。

# --instructions--

在 `tests/1_unit-tests.js` 中，在測試標籤 `#16`下，將每個`Objects` 下的`assert` 修改成`assert.property` 或`assert.notProperty`以確保通過測試 (結果應返回“ `true`”). 不要修改傳給斷言的參數。

# --hints--

不應有未通過的測試

```js
  $.get(code + '/_api/get-tests?type=unit&n=15').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

應該爲第一個斷言選擇正確的方法：`property` 或 `notProperty`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=15').then(
    (data) => {
      assert.equal(
        data.assertions[0].method,
        'notProperty',
        'A car has not wings'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

應該爲第二個斷言選擇正確的方法：`property` 或 `notProperty`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=15').then(
    (data) => {
      assert.equal(
        data.assertions[1].method,
        'property',
        'planes have engines'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

應該爲第三個斷言選擇正確的方法：`property` 或 `notProperty`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=15').then(
    (data) => {
      assert.equal(data.assertions[2].method, 'property', 'Cars have wheels');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

