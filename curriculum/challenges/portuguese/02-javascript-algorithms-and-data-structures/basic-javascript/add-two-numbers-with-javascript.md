---
id: cf1111c1c11feddfaeb3bdef
title: Adicionar dois números com JavaScript
challengeType: 1
forumTopicId: 16650
dashedName: add-two-numbers-with-javascript
---

# --description--

`Number` is a data type in JavaScript which represents numeric data.

Agora, vamos tentar adicionar dois números usando JavaScript.

JavaScript utiliza o símbolo `+` como um operador de adição quando colocado entre dois números.

**Exemplo:**

```js
const myVar = 5 + 10;
```

`myVar` agora tem o valor de `15`.

# --instructions--

Modifique o `0` para que a soma seja igual a `20`.

# --hints--

`soma` deve ser igual a `20`.

```js
assert(sum === 20);
```

Você deve usar o operador `+`.

```js
assert(/\+/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'sum = '+z;})(sum);
```

## --seed-contents--

```js
const sum = 10 + 0;
```

# --solutions--

```js
const sum = 10 + 10;
```
