---
id: 56533eb9ac21ba0edf2244c2
title: Retornar um valor de uma função com return
challengeType: 1
forumTopicId: 18271
dashedName: return-a-value-from-a-function-with-return
---

# --description--

We can pass values into a function with <dfn>arguments</dfn>. You can use a `return` statement to send a value back out of a function.

**Exemplo**

```js
function plusThree(num) {
  return num + 3;
}

const answer = plusThree(5);
```

`answer` tem o valor de `8`.

`plusThree` recebe um <dfn>argumento</dfn> para `num` e retorna um valor igual a `num + 3`.

# --instructions--

Crie uma função `timesFive` que aceita um argumento, multiplica ele por `5` e retorna o novo valor.

# --hints--

`timesFive` deve ser uma função

```js
assert(typeof timesFive === 'function');
```

`timesFive(5)` deve retornar `25`

```js
assert(timesFive(5) === 25);
```

`timesFive(2)` deve retornar `10`

```js
assert(timesFive(2) === 10);
```

`timesFive(0)` deve retornar `0`

```js
assert(timesFive(0) === 0);
```

# --seed--

## --seed-contents--

```js

```

# --solutions--

```js
function timesFive(num) {
  return num * 5;
}
timesFive(10);
```
