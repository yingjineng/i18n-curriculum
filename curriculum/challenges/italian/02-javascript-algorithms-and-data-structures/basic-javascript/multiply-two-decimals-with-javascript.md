---
id: bd7993c9c69feddfaeb7bdef
title: Moltiplicare due decimali con JavaScript
challengeType: 1
forumTopicId: 301173
dashedName: multiply-two-decimals-with-javascript
---

# --description--

In JavaScript, you can also perform calculations with decimal numbers, just like whole numbers.

Moltiplichiamo due decimali insieme per ottenere il loro prodotto.

# --instructions--

Cambia lo `0.0` in modo che il prodotto sia uguale a `5.0`.

# --hints--

La variabile `product` dovrebbe essere uguale a `5.0`.

```js
assert(product === 5.0);
```

Dovresti usare l'operatore `*`

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
