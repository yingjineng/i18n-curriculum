---
id: cf1111c1c11feddfaeb6bdef
title: 除法運算
challengeType: 1
forumTopicId: 17566
dashedName: divide-one-number-by-another-with-javascript
---

# --description--

We can also divide one number by another.

JavaScript 中使用 `/` 符號做除法運算。

**示例**

```js
const myVar = 16 / 2;
```

現在，變量 `myVar` 的值爲 `8`。
# --instructions--

改變數值 `0` 來讓變量 `quotient` 的值等於 `2`。

# --hints--

要使 `quotient` 的值等於 2。

```js
assert(quotient === 2);
```

使用 `/` 運算符。

```js
assert(/\d+\s*\/\s*\d+/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'quotient = '+z;})(quotient);
```

## --seed-contents--

```js
const quotient = 66 / 0;
```

# --solutions--

```js
const quotient = 66 / 33;
```
