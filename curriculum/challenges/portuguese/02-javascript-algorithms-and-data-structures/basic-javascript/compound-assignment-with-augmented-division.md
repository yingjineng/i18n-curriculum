---
id: 56533eb9ac21ba0edf2244b2
title: Atribuir de modo composto com divisão aumentada
challengeType: 1
forumTopicId: 16659
dashedName: compound-assignment-with-augmented-division
---

# --description--

The `/=` operator divides a variable by another number.

```js
myVar = myVar / 5;
```

dividirá `myVar` por `5`. Isto pode ser reescrito como:

```js
myVar /= 5;
```

# --instructions--

Converta as atribuições para `a`, `b` e `c` para usar o operador `/=`.

# --hints--

`a` deve ser igual a `4`.

```js
assert(a === 4);
```

`b` deve ser igual a `27`.

```js
assert(b === 27);
```

`c` deve ser igual a `3`.

```js
assert(c === 3);
```

Você deve usar o operador `/=` para cada variável.

```js
assert(__helpers.removeJSComments(code).match(/\/=/g).length === 3);
```

Você não deve modificar o código acima do comentário especificado.

```js
assert(
  /let a = 48;/.test(__helpers.removeJSComments(code)) &&
    /let b = 108;/.test(__helpers.removeJSComments(code)) &&
    /let c = 33;/.test(__helpers.removeJSComments(code))
);
```

# --seed--

## --after-user-code--

```js
(function(a,b,c){ return "a = " + a + ", b = " + b + ", c = " + c; })(a,b,c);
```

## --seed-contents--

```js
let a = 48;
let b = 108;
let c = 33;

// Only change code below this line
a = a / 12;
b = b / 4;
c = c / 11;
```

# --solutions--

```js
let a = 48;
let b = 108;
let c = 33;

a /= 12;
b /= 4;
c /= 11;
```
