---
id: bd7993c9c69feddfaeb7bdef
title: 两个小数相乘
challengeType: 1
forumTopicId: 301173
dashedName: multiply-two-decimals-with-javascript
---

# --description--

In JavaScript, you can also perform calculations with decimal numbers, just like whole numbers.

把两个小数相乘，并得到它们乘积。

# --instructions--

改变 `0.0` 的数值让变量 product 的值等于 `5.0`。

# --hints--

变量 `product` 应该等于 `5.0`。

```js
assert(product === 5.0);
```

要使用 `*` 运算符。

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
