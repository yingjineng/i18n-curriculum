---
id: 587d824c367417b2b2512c4f
title: 値が特定の範囲内かどうかをテストする
challengeType: 2
forumTopicId: 301598
dashedName: test-if-a-value-falls-within-a-specific-range
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

```javascript
.approximately(actual, expected, delta, [message])
```

`actual` が `expected`に等しく +/- `delta` の範囲内であることをアサートします。

# --instructions--

Within `tests/1_unit-tests.js` under the test labeled `#10` in the `Comparisons` suite, change each `assert` to `assert.approximately` to make the test pass (should evaluate to `true`).

テストを常に成功させるには、最小範囲 (3 番目のパラメータ) を選択してください。 範囲は、1 未満でなければなりません。

# --hints--

すべてのテストが成功する必要があります。

```js
  $.get(code + '/_api/get-tests?type=unit&n=9').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

最初のアサーションに対して、正しい範囲を選ぶ必要があります - `approximately(actual, expected, range)` です。

```js
  $.get(code + '/_api/get-tests?type=unit&n=9').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'approximately');
      assert.equal(
        data.assertions[0].args[2],
        0.5,
        "weirdNumbers(0.5) is in the range (0.5, 1.5]. It's within 1 +/- 0.5"
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

2 番目のアサーションに対して、正しい範囲を選ぶ必要があります - `approximately(actual, expected, range)` です。

```js
  $.get(code + '/_api/get-tests?type=unit&n=9').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'approximately');
      assert.equal(
        data.assertions[1].args[2],
        0.8,
        "weirdNumbers(0.2) is in the range (0.2, 1.2]. It's within 1 +/- 0.8"
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

