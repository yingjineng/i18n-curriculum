---
id: 56533eb9ac21ba0edf2244d9
title: 逻辑或运算符
challengeType: 1
forumTopicId: 16800
dashedName: comparisons-with-the-logical-or-operator
---

# --description--

The <dfn>logical or</dfn> operator (`||`) returns `true` if either of the <dfn>operands</dfn> is `true`. Otherwise, it returns `false`.

<dfn>逻辑或</dfn>运算符由两个竖线（`||`）组成。 这个按键位于退格键和回车键之间。

下面这个模式看起来应该很熟悉：

```js
if (num > 10) {
  return "No";
}
if (num < 5) {
  return "No";
}
return "Yes";
```

如果 `num` 在 `5` 和 `10` 之间（包括 `5` 和 `10`），这段代码将返回 `Yes`。 可以使用<dfn>逻辑 or</dfn> 操作符写出同样的逻辑。

```js
if (num > 10 || num < 5) {
  return "No";
}
return "Yes";
```

# --instructions--

请使用逻辑或运算符把两个 `if` 语句合并为一个语句，如果 `val` 不在 `10` 和 `20` 之间（包括不是 10 和 不是 20），返回 `Outside`。 否则，返回 `Inside`。

# --hints--

应该使用一次 `||` 操作符。

```js
assert(__helpers.removeJSComments(code).match(/\|\|/g).length === 1);
```

应该只有一个 `if` 表达式。

```js
assert(__helpers.removeJSComments(code).match(/if/g).length === 1);
```

`testLogicalOr(0)` 应该返回字符串 `Outside`

```js
assert(testLogicalOr(0) === 'Outside');
```

`testLogicalOr(9)` 应该返回字符串 `Outside`

```js
assert(testLogicalOr(9) === 'Outside');
```

`testLogicalOr(10)` 应该返回字符串 `Inside`

```js
assert(testLogicalOr(10) === 'Inside');
```

`testLogicalOr(15)` 应该返回字符串 `Inside`

```js
assert(testLogicalOr(15) === 'Inside');
```

`testLogicalOr(19)` 应该返回字符串 `Inside`

```js
assert(testLogicalOr(19) === 'Inside');
```

`testLogicalOr(20)` 应该返回字符串 `Inside`

```js
assert(testLogicalOr(20) === 'Inside');
```

`testLogicalOr(21)` 应该返回字符串 `Outside`

```js
assert(testLogicalOr(21) === 'Outside');
```

`testLogicalOr(25)` 应该返回字符串 `Outside`

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
