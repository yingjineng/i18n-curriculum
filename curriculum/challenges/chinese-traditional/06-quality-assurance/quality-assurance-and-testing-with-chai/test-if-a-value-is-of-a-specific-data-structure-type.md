---
id: 587d824e367417b2b2512c56
title: 測試值是否爲特定數據結構類型
challengeType: 2
forumTopicId: 301601
dashedName: test-if-a-value-is-of-a-specific-data-structure-type
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

`#typeOf` 斷言一個值的類型符合給定的類型，這個類型與 `Object.prototype.toString` 一致。

# --instructions--

Within `tests/1_unit-tests.js` under the test labeled `#17` in the `Objects` suite, change each `assert` to either `assert.typeOf` or `assert.notTypeOf` to make the test pass (should evaluate to `true`). 不要修改傳給斷言的參數。

# --hints--

不應有未通過的測試

```js
  $.get(code + '/_api/get-tests?type=unit&n=16').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

應該爲第一個斷言選擇正確的方法：`typeOf` 或 `notTypeOf`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=16').then(
    (data) => {
      assert.equal(
        data.assertions[0].method,
        'typeOf',
        'myCar is typeOf Object'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

應該爲第二個斷言選擇正確的方法：`typeOf` 或 `notTypeOf`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=16').then(
    (data) => {
      assert.equal(
        data.assertions[1].method,
        'typeOf',
        'Car.model is a String'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

應該爲第三個斷言選擇正確的方法：`typeOf` 或 `notTypeOf`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=16').then(
    (data) => {
      assert.equal(
        data.assertions[2].method,
        'notTypeOf',
        'Plane.wings is a Number (not a String)'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

應該爲第四個斷言選擇正確的方法：`typeOf` 或 `notTypeOf`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=16').then(
    (data) => {
      assert.equal(
        data.assertions[3].method,
        'typeOf',
        'Plane.engines is an Array'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

應該爲第五個斷言選擇正確的方法：`typeOf` 或 `notTypeOf`。

```js
  $.get(code + '/_api/get-tests?type=unit&n=16').then(
    (data) => {
      assert.equal(
        data.assertions[4].method,
        'typeOf',
        'Car.wheels is a Number'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

