---
id: cf1231c1c11feddfaeb5bdef
title: Множення двох чисел з JavaScript
challengeType: 1
forumTopicId: 18243
dashedName: multiply-two-numbers-with-javascript
---

# --description--

We can also multiply one number by another.

JavaScript використовує символ `*` для множення двох чисел.

**Приклад**

```js
const myVar = 13 * 13;
```

`myVar` мало б значення `169`.

# --instructions--

Змініть `0` так, щоб добуток дорівнював `80`.

# --hints--

Змінна `product` повинна дорівнювати 80.

```js
assert(product === 80);
```

Ви повинні використати оператор `*`.

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
