---
id: cf1231c1c11feddfaeb5bdef
title: Multiplicar dois números com JavaScript
challengeType: 1
forumTopicId: 18243
dashedName: multiply-two-numbers-with-javascript
---

# --description--

We can also multiply one number by another.

JavaScript usa o símbolo `*` para multiplicação de dois números.

**Exemplo**

```js
const myVar = 13 * 13;
```

`myVar` teria o valor `169`.

# --instructions--

Altere o `0` para que o produto seja igual a `80`.

# --hints--

A variável `product` deve ser igual a 80.

```js
assert(product === 80);
```

Você deve usar o operador `*`.

```js
assert(/\*/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'product = '+z;})(product);
```

## --seed-contents--

```js
const product = 8 * 0;
```

# --solutions--

```js
const product = 8 * 10;
```
