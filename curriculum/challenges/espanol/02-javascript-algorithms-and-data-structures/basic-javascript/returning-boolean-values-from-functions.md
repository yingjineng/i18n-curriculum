---
id: 5679ceb97cbaa8c51670a16b
title: Devuelve valores booleanos desde funciones
challengeType: 1
forumTopicId: 18273
dashedName: returning-boolean-values-from-functions
---

# --description--

You may recall from <a href="/learn/javascript-algorithms-and-data-structures/basic-javascript/comparison-with-the-equality-operator" target="_blank" rel="noopener noreferrer nofollow">Comparison with the Equality Operator</a> that all comparison operators return a boolean `true` or `false` value.

A veces la gente usa una sentencia `if/else` para hacer una comparación, como esta:

```js
function isEqual(a, b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}
```

Pero hay una mejor manera de hacer esto. Puesto que `===` devuelve `true` o `false`, podemos devolver el resultado de la comparación:

```js
function isEqual(a, b) {
  return a === b;
}
```

# --instructions--

Corrige la función `isLess` para eliminar las sentencias `if/else`.

# --hints--

`isLess(10, 15)` debe devolver `true`

```js
assert(isLess(10, 15) === true);
```

`isLess(15, 10)` debe devolver `false`

```js
assert(isLess(15, 10) === false);
```

No debes utilizar las sentencias `if` o `else`

```js
assert(!/if|else/g.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
function isLess(a, b) {
  // Only change code below this line
  if (a < b) {
    return true;
  } else {
    return false;
  }
  // Only change code above this line
}

isLess(10, 15);
```

# --solutions--

```js
function isLess(a, b) {
  return a < b;
}
```
