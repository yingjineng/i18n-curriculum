---
id: cf1111c1c11feddfaeb4bdef
title: Resta un número de otro con JavaScript
challengeType: 1
forumTopicId: 18314
dashedName: subtract-one-number-from-another-with-javascript
---

# --description--

También podemos restar un número de otro.

JavaScript utiliza el símbolo `-` para restar.

**Ejemplo**

```js
const myVar = 12 - 6;
```

`myVar` tendrá el valor `6`.
# --instructions--

Cambia el `0` para que la diferencia sea `12`.

# --hints--

La variable `difference` debe ser igual a `12`.

```js
assert(difference === 12);
```

Solo debes restar un número de `45`.

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
