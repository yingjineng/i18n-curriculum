---
id: cf1231c1c11feddfaeb5bdef
title: 乘法運算
challengeType: 1
forumTopicId: 18243
dashedName: multiply-two-numbers-with-javascript
---

# --description--

We can also multiply one number by another.

JavaScript 使用 `*` 符號表示兩數相乘。

**示例**

```js
const myVar = 13 * 13;
```

現在，變量 `myVar` 的值爲 `169`。

# --instructions--

改變數值 `0` 來讓變量 product 的值等於`80`。

# --hints--

變量 `product` 的值應該等於 80。

```js
assert(product === 80);
```

使用 `*` 運算符。

```js
assert(/\*/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'product = '+z;})(product);
```

## --seed-contents--

```js
const product = 8 * 0;
```

# --solutions--

```js
const product = 8 * 10;
```
