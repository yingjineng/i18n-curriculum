---
id: cf1231c1c11feddfaeb5bdef
title: Moltiplicare due numeri con JavaScript
challengeType: 1
forumTopicId: 18243
dashedName: multiply-two-numbers-with-javascript
---

# --description--

We can also multiply one number by another.

JavaScript utilizza il simbolo `*` per la moltiplicazione di due numeri.

**Esempio**

```js
const myVar = 13 * 13;
```

`myVar` dovrebbe avere il valore `169`.

# --instructions--

Cambia lo `0` in modo che il prodotto sia uguale a `80`.

# --hints--

La variabile `product` dovrebbe essere uguale a 80.

```js
assert(product === 80);
```

Dovresti usare l'operatore `*`.

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
