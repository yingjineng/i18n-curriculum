---
id: 56533eb9ac21ba0edf2244b2
title: Assegnazione composta con divisione aumentata
challengeType: 1
forumTopicId: 16659
dashedName: compound-assignment-with-augmented-division
---

# --description--

The `/=` operator divides a variable by another number.

```js
myVar = myVar / 5;
```

Dividerà `myVar` per `5`. Ciò può essere riscritto come:

```js
myVar /= 5;
```

# --instructions--

Converti le assegnazioni per `a`, `b` e `c` in modo da utilizzare l'operatore `/=`.

# --hints--

`a` dovrebbe essere uguale a `4`.

```js
assert(a === 4);
```

`b` dovrebbe essere uguale a `27`.

```js
assert(b === 27);
```

`c` dovrebbe essere uguale a `3`.

```js
assert(c === 3);
```

Dovresti usare l'operatore `/=` per ogni variabile.

```js
assert(__helpers.removeJSComments(code).match(/\/=/g).length === 3);
```

Non dovresti modificare il codice sopra il commento specificato.

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
