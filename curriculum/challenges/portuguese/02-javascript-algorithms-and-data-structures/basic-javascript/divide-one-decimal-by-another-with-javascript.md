---
id: bd7993c9ca9feddfaeb7bdef
title: Dividir um decimal por outro com JavaScript
challengeType: 1
forumTopicId: 18255
dashedName: divide-one-decimal-by-another-with-javascript
---

# --description--

Now let's divide one decimal by another.

# --instructions--

Modifique `0.0` para que a variável `quotient` seja igual a `2.2`.

# --hints--

A variável `quotient` deve ser igual a `2.2`

```js
assert(quotient === 2.2);
```

Você deve usar o operador `/` para dividir 4.4 por 2

```js
assert(/4\.40*\s*\/\s*2\.*0*/.test(__helpers.removeJSComments(code)));
```

A variável quotient deve ser atribuída apenas uma vez

```js
assert(__helpers.removeJSComments(code).match(/quotient\s*=/g).length === 1);
```

# --seed--

## --seed-contents--

```js
const quotient = 0.0 / 2.0; // Change this line
```

# --solutions--

```js
const quotient = 4.4 / 2.0;
```
