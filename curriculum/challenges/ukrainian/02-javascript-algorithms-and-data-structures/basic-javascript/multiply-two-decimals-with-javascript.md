---
id: bd7993c9c69feddfaeb7bdef
title: Множення двох десяткових чисел з JavaScript
challengeType: 1
forumTopicId: 301173
dashedName: multiply-two-decimals-with-javascript
---

# --description--

In JavaScript, you can also perform calculations with decimal numbers, just like whole numbers.

Перемножимо два десяткових числа, щоб отримати їх добуток.

# --instructions--

Змініть `0.0` так, щоб добуток дорівнював `5.0`.

# --hints--

Змінна `product` повинна дорівнювати `5.0`.

```js
assert(product === 5.0);
```

Ви повинні використати оператор `*`

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
