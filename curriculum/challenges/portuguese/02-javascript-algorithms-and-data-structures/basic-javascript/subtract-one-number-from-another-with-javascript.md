---
id: cf1111c1c11feddfaeb4bdef
title: Subtrair um número de outro com JavaScript
challengeType: 1
forumTopicId: 18314
dashedName: subtract-one-number-from-another-with-javascript
---

# --description--

We can also subtract one number from another.

JavaScript usa o símbolo `-` para subtração.

**Exemplo**

```js
const myVar = 12 - 6;
```

`myVar` teria o valor `6`.
# --instructions--

Altere o `0` para que a variável difference seja igual a `12`.

# --hints--

A variável `difference` deve ser igual a `12`.

```js
assert(difference === 12);
```

Você só deve subtrair um número de `45`.

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
