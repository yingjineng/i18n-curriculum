---
id: cf1111c1c11feddfaeb4bdef
title: Sottrarre un numero da un altro con JavaScript
challengeType: 1
forumTopicId: 18314
dashedName: subtract-one-number-from-another-with-javascript
---

# --description--

We can also subtract one number from another.

JavaScript utilizza il simbolo `-` per la sottrazione.

**Esempio**

```js
const myVar = 12 - 6;
```

`myVar` avrà il valore `6`.
# --instructions--

Modifica lo `0` in modo che la differenza sia `12`.

# --hints--

La variabile `difference` dovrebbe essere uguale a `12`.

```js
assert(difference === 12);
```

Devi solo sottrarre un numero da `45`.

```js
assert(/difference=45-33;?/.test(__helpers.removeWhiteSpace(__helpers.removeJSComments(code))));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'difference = '+z;})(difference);
```

## --seed-contents--

```js
const difference = 45 - 0;
```

# --solutions--

```js
const difference = 45 - 33;
```
