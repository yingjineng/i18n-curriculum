---
id: cf1111c1c11feddfaeb3bdef
title: 加法运算
challengeType: 1
forumTopicId: 16650
dashedName: add-two-numbers-with-javascript
---

# --description--

`Number` is a data type in JavaScript which represents numeric data.

现在我们来尝试在 JavaScript 中做加法运算。

JavaScript 中，我们通过符号 `+` 来进行加法运算。

**代码示例:**

```js
const myVar = 5 + 10;
```

现在，变量 `myVar` 的值为 `15`。

# --instructions--

请改变数字 `0` 让变量 sum 的值为 `20`。

# --hints--

`sum` 的值应该等于 `20`。

```js
assert(sum === 20);
```

请使用 `+` 运算符。

```js
assert(/\+/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'sum = '+z;})(sum);
```

## --seed-contents--

```js
const sum = 10 + 0;
```

# --solutions--

```js
const sum = 10 + 10;
```
