---
id: 587d824c367417b2b2512c4d
title: 2 つの要素のプロパティを比較する
challengeType: 2
forumTopicId: 301588
dashedName: compare-the-properties-of-two-elements
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

# --instructions--

Within `tests/1_unit-tests.js` under the test labeled `#8` in the `Comparisons` suite, change each `assert` to either `assert.isAbove` or `assert.isAtMost` to make the test pass (should evaluate to `true`). アサートに渡された引数を変更しないでください。

# --hints--

すべてのテストが成功する必要があります。

```js
  $.get(code + '/_api/get-tests?type=unit&n=7').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

最初のアサーションに、正しいメソッドを選ぶ必要があります - `isAbove` もしくは `isAtMost` です。

```js
  $.get(code + '/_api/get-tests?type=unit&n=7').then(
    (data) => {
      assert.equal(
        data.assertions[0].method,
        'isAtMost',
        '5 is at most (<=) 5'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

2 番目のアサーションに、正しいメソッドを選ぶ必要があります - `isAbove` もしくは `isAtMost` です。

```js
  $.get(code + '/_api/get-tests?type=unit&n=7').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'isAbove', '1 is greater than 0');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

3 番目のアサーションに、正しいメソッドを選ぶ必要があります - `isAbove` もしくは `isAtMost` です。

```js
  $.get(code + '/_api/get-tests?type=unit&n=7').then(
    (data) => {
      assert.equal(
        data.assertions[2].method,
        'isAbove',
        'Math.PI = 3.14159265 is greater than 3'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

4 番目のアサーションに、正しいメソッドを選ぶ必要があります - `isAbove` もしくは `isAtMost` です。

```js
  $.get(code + '/_api/get-tests?type=unit&n=7').then(
    (data) => {
      assert.equal(
        data.assertions[3].method,
        'isAtMost',
        '1 - Math.random() is > 0 and <= 1. It is atMost 1 !'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

