---
id: bd7993c9c69feddfaeb7bdef
title: 兩個小數相乘
challengeType: 1
forumTopicId: 301173
dashedName: multiply-two-decimals-with-javascript
---

# --description--

In JavaScript, you can also perform calculations with decimal numbers, just like whole numbers.

把兩個小數相乘，並得到它們乘積。

# --instructions--

改變 `0.0` 的數值讓變量 product 的值等於 `5.0`。

# --hints--

變量 `product` 應該等於 `5.0`。

```js
assert(product === 5.0);
```

要使用 `*` 運算符。

```js
assert(/\*/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(y){return 'product = '+y;})(product);
```

## --seed-contents--

```js
const product = 2.0 * 0.0;
```

# --solutions--

```js
const product = 2.0 * 2.5;
```
