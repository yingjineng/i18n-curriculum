---
id: cf1111c1c11feddfaeb3bdef
title: 加法運算
challengeType: 1
forumTopicId: 16650
dashedName: add-two-numbers-with-javascript
---

# --description--

`Number` is a data type in JavaScript which represents numeric data.

現在我們來嘗試在 JavaScript 中做加法運算。

JavaScript 中，我們通過符號 `+` 來進行加法運算。

**代碼示例:**

```js
const myVar = 5 + 10;
```

現在，變量 `myVar` 的值爲 `15`。

# --instructions--

請改變數字 `0` 讓變量 sum 的值爲 `20`。

# --hints--

`sum` 的值應該等於 `20`。

```js
assert(sum === 20);
```

請使用 `+` 運算符。

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
