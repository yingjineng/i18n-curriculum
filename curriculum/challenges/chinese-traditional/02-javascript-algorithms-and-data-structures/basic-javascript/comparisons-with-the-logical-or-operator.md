---
id: 56533eb9ac21ba0edf2244d9
title: 邏輯或運算符
challengeType: 1
forumTopicId: 16800
dashedName: comparisons-with-the-logical-or-operator
---

# --description--

The <dfn>logical or</dfn> operator (`||`) returns `true` if either of the <dfn>operands</dfn> is `true`. Otherwise, it returns `false`.

<dfn>邏輯或</dfn>運算符由兩個豎線（`||`）組成。 這個按鍵位於退格鍵和回車鍵之間。

下面這個模式看起來應該很熟悉：

```js
if (num > 10) {
  return "No";
}
if (num < 5) {
  return "No";
}
return "Yes";
```

如果 `num` 在 `5` 和 `10` 之間（包括 `5` 和 `10`），這段代碼將返回 `Yes`。 可以使用<dfn>邏輯 or</dfn> 操作符寫出同樣的邏輯。

```js
if (num > 10 || num < 5) {
  return "No";
}
return "Yes";
```

# --instructions--

請使用邏輯或運算符把兩個 `if` 語句合併爲一個語句，如果 `val` 不在 `10` 和 `20` 之間（包括不是 10 和 不是 20），返回 `Outside`。 否則，返回 `Inside`。

# --hints--

應該使用一次 `||` 操作符。

```js
assert(__helpers.removeJSComments(code).match(/\|\|/g).length === 1);
```

應該只有一個 `if` 表達式。

```js
assert(__helpers.removeJSComments(code).match(/if/g).length === 1);
```

`testLogicalOr(0)` 應該返回字符串 `Outside`

```js
assert(testLogicalOr(0) === 'Outside');
```

`testLogicalOr(9)` 應該返回字符串 `Outside`

```js
assert(testLogicalOr(9) === 'Outside');
```

`testLogicalOr(10)` 應該返回字符串 `Inside`

```js
assert(testLogicalOr(10) === 'Inside');
```

`testLogicalOr(15)` 應該返回字符串 `Inside`

```js
assert(testLogicalOr(15) === 'Inside');
```

`testLogicalOr(19)` 應該返回字符串 `Inside`

```js
assert(testLogicalOr(19) === 'Inside');
```

`testLogicalOr(20)` 應該返回字符串 `Inside`

```js
assert(testLogicalOr(20) === 'Inside');
```

`testLogicalOr(21)` 應該返回字符串 `Outside`

```js
assert(testLogicalOr(21) === 'Outside');
```

`testLogicalOr(25)` 應該返回字符串 `Outside`

```js
assert(testLogicalOr(25) === 'Outside');
```

# --seed--

## --seed-contents--

```js
function testLogicalOr(val) {
  // Only change code below this line

  if (val) {
    return "Outside";
  }

  if (val) {
    return "Outside";
  }

  // Only change code above this line
  return "Inside";
}

testLogicalOr(15);
```

# --solutions--

```js
function testLogicalOr(val) {
  if (val < 10 || val > 20) {
    return "Outside";
  }
  return "Inside";
}
```
