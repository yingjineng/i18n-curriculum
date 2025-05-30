---
id: 587d7b7e367417b2b2512b22
title: Usar a função parseInt com um radix
challengeType: 1
forumTopicId: 301182
dashedName: use-the-parseint-function-with-a-radix
---

# --description--

The `parseInt()` function parses a string and returns an integer. It takes a second argument for the radix, which specifies the base of the number in the string. The radix can be an integer between 2 and 36.

A chamada da função se parece com:

```js
parseInt(string, radix);
```

Exemplo:

```js
const a = parseInt("11", 2);
```

A variável radix diz que `11` está no sistema binário, ou base 2. Esse exemplo converte a string `11` para um inteiro `3`.

# --instructions--

Use `parseInt()` na função `convertToInteger` para que ela converta um número binário em um inteiro e o retorne.

# --hints--

`convertToInteger` deve usar a função `parseInt()`

```js
assert(/parseInt/g.test(__helpers.removeJSComments(code)));
```

`convertToInteger("10011")` deve retornar um número

```js
assert(typeof convertToInteger('10011') === 'number');
```

`convertToInteger("10011")` deve retornar 19

```js
assert(convertToInteger('10011') === 19);
```

`convertToInteger("111001")` deve retornar 57

```js
assert(convertToInteger('111001') === 57);
```

`convertToInteger("JamesBond")` deve retornar `NaN`

```js
assert.isNaN(convertToInteger('JamesBond'));
```

# --seed--

## --seed-contents--

```js
function convertToInteger(str) {

}

convertToInteger("10011");
```

# --solutions--

```js
function convertToInteger(str) {
  return parseInt(str, 2);
}
```
