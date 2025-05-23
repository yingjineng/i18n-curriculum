---
id: 56533eb9ac21ba0edf2244c3
title: Atribuir com o valor retornado
challengeType: 1
forumTopicId: 16658
dashedName: assignment-with-a-returned-value
---

# --description--

If you'll recall from our discussion about <a href="/learn/javascript-algorithms-and-data-structures/basic-javascript/storing-values-with-the-assignment-operator" target="_blank" rel="noopener noreferrer nofollow">Storing Values with the Assignment Operator</a>, everything to the right of the equal sign is resolved before the value is assigned. This means we can take the return value of a function and assign it to a variable.

Assuma que temos uma função definida chamada `sum`, que soma dois números.

```js
ourSum = sum(5, 12);
```

Chamar a função `sum` com os argumentos `5` e `12` produz um valor de retorno de `17`. Esse valor de retorno é atribuído à variável `ourSum`.

# --instructions--

Chame a função `processArg` com um argumento de `7` e atribui o retorno do seu valor para a variável `processed`.

# --hints--

`processed` deve ter o valor `2`

```js
assert(processed === 2);
```

Você deve atribuir `processArg` para `processed`

```js
assert(/processed\s*=\s*processArg\(\s*7\s*\)/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(){return "processed = " + processed})();
```

## --seed-contents--

```js
// Setup
let processed = 0;

function processArg(num) {
  return (num + 3) / 5;
}

// Only change code below this line

```

# --solutions--

```js
var processed = 0;

function processArg(num) {
  return (num + 3) / 5;
}

processed = processArg(7);
```
