---
id: 56533eb9ac21ba0edf2244d8
title: 邏輯與運算符
challengeType: 1
forumTopicId: 16799
dashedName: comparisons-with-the-logical-and-operator
---

# --description--

Sometimes you will need to test more than one thing at a time. The <dfn>logical and</dfn> operator (`&&`) returns `true` if and only if the <dfn>operands</dfn> to the left and right of it are true.

可以通過在一個 `if` 語句中嵌套另一個 `if` 語句來實現同樣的效果。

```js
if (num > 5) {
  if (num < 10) {
    return "Yes";
  }
}
return "No";
```

當 `num` 的值大於 `5` 並且小於`10`，代碼會返回 `Yes`。 可以使用<dfn>邏輯 and</dfn> 操作符寫出相同的邏輯。

```js
if (num > 5 && num < 10) {
  return "Yes";
}
return "No";
```

# --instructions--

請使用 `&&` 運算符把兩個 if 語句合併爲一個 if 語句，如果 `val` 小於或等於 `50` 並且大於或等於 `25` 時，返回 `Yes`。 否則，將返回 `No`。

# --hints--

你應該使用 `&&` 運算符一次。

```js
assert(__helpers.removeJSComments(code).match(/&&/g).length === 1);
```

你應該只有一個 `if` 表達式。

```js
assert(__helpers.removeJSComments(code).match(/if/g).length === 1);
```

`testLogicalAnd(0)` 應該返回字符串 `No`

```js
assert(testLogicalAnd(0) === 'No');
```

`testLogicalAnd(24)` 應該返回字符串 `No`

```js
assert(testLogicalAnd(24) === 'No');
```

`testLogicalAnd(25)` 應該返回字符串 `Yes`

```js
assert(testLogicalAnd(25) === 'Yes');
```

`testLogicalAnd(30)` 應該返回字符串 `Yes`

```js
assert(testLogicalAnd(30) === 'Yes');
```

`testLogicalAnd(50)` 應該返回字符串 `Yes`

```js
assert(testLogicalAnd(50) === 'Yes');
```

`testLogicalAnd(51)` 應該返回字符串 `No`

```js
assert(testLogicalAnd(51) === 'No');
```

`testLogicalAnd(75)` 應該返回字符串 `No`

```js
assert(testLogicalAnd(75) === 'No');
```

`testLogicalAnd(80)` 應該返回字符串 `No`

```js
assert(testLogicalAnd(80) === 'No');
```

# --seed--

## --seed-contents--

```js
function testLogicalAnd(val) {
  // Only change code below this line

  if (val) {
    if (val) {
      return "Yes";
    }
  }

  // Only change code above this line
  return "No";
}

testLogicalAnd(10);
```

# --solutions--

```js
function testLogicalAnd(val) {
  if (val >= 25 && val <= 50) {
    return "Yes";
  }
  return "No";
}
```
