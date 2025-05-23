---
id: 5679ceb97cbaa8c51670a16b
title: Retornar valores booleanos das funções
challengeType: 1
forumTopicId: 18273
dashedName: returning-boolean-values-from-functions
---

# --description--

You may recall from <a href="/learn/javascript-algorithms-and-data-structures/basic-javascript/comparison-with-the-equality-operator" target="_blank" rel="noopener noreferrer nofollow">Comparison with the Equality Operator</a> that all comparison operators return a boolean `true` or `false` value.

Às vezes, as pessoas usam uma instrução `if/else` para fazer uma comparação, dessa forma:

```js
function isEqual(a, b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}
```

Mas há uma forma melhor de fazer isso. Já que `===` retorna `true` ou `false`, podemos retornar o resultado da comparação:

```js
function isEqual(a, b) {
  return a === b;
}
```

# --instructions--

Corrija a função `isLess` para remover as instruções `if/else`.

# --hints--

`isLess(10, 15)` deve retornar `true`

```js
assert(isLess(10, 15) === true);
```

`isLess(15, 10)` deve retornar `false`

```js
assert(isLess(15, 10) === false);
```

Você não deve usar nenhuma instrução do tipo `if` ou `else`

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
