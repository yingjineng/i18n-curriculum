---
id: a39963a4c10bc8b4d4f06d7e
title: Procurar e destruir
challengeType: 1
forumTopicId: 16046
dashedName: seek-and-destroy
---

# --description--

You will be provided with an initial array as the first argument to the `destroyer` function, followed by one or more arguments. Remove all elements from the initial array that are of the same value as these arguments.

A função deve aceitar um número indeterminado de argumentos. Em outras palavras, ela deve ser uma função variádica. Você poderá acessar os argumentos adicionais colocando um parâmetro rest na definição da função ou usando o objeto `arguments`.

# --hints--

`destroyer([1, 2, 3, 1, 2, 3], 2, 3)` deve retornar `[1, 1]`.

```js
assert.deepEqual(destroyer([1, 2, 3, 1, 2, 3], 2, 3), [1, 1]);
```

`destroyer([1, 2, 3, 5, 1, 2, 3], 2, 3)` deve retornar `[1, 5, 1]`.

```js
assert.deepEqual(destroyer([1, 2, 3, 5, 1, 2, 3], 2, 3), [1, 5, 1]);
```

`destroyer([3, 5, 1, 2, 2], 2, 3, 5)` deve retornar `[1]`.

```js
assert.deepEqual(destroyer([3, 5, 1, 2, 2], 2, 3, 5), [1]);
```

`destroyer([2, 3, 2, 3], 2, 3)` deve retornar `[]`.

```js
assert.deepEqual(destroyer([2, 3, 2, 3], 2, 3), []);
```

`destroyer(["tree", "hamburger", 53], "tree", 53)` deve retornar `["hamburger"]`.

```js
assert.deepEqual(destroyer(['tree', 'hamburger', 53], 'tree', 53), [
  'hamburger'
]);
```

`destroyer(["possum", "trollo", 12, "safari", "hotdog", 92, 65, "grandma", "bugati", "trojan", "yacht"], "yacht", "possum", "trollo", "safari", "hotdog", "grandma", "bugati", "trojan")` deve retornar `[12,92,65]`.

```js
assert.deepEqual(
  destroyer(
    [
      'possum',
      'trollo',
      12,
      'safari',
      'hotdog',
      92,
      65,
      'grandma',
      'bugati',
      'trojan',
      'yacht'
    ],
    'yacht',
    'possum',
    'trollo',
    'safari',
    'hotdog',
    'grandma',
    'bugati',
    'trojan'
  ),
  [12, 92, 65]
);
```

# --seed--

## --seed-contents--

```js
function destroyer(arr) {
  return arr;
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);
```

# --solutions--

```js
function destroyer(arr) {
  var hash = Object.create(null);
  [].slice.call(arguments, 1).forEach(function(e) {
    hash[e] = true;
  });
  return arr.filter(function(e) { return !(e in hash);});
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);
```
