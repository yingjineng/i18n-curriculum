---
id: 56533eb9ac21ba0edf2244b1
title: Assegnazione composta con moltiplicazione aumentata
challengeType: 1
forumTopicId: 16662
dashedName: compound-assignment-with-augmented-multiplication
---

# --description--

The `*=` operator multiplies a variable by a number.

```js
myVar = myVar * 5;
```

moltiplicherà `myVar` per `5`. Ciò può essere riscritto come:

```js
myVar *= 5;
```

# --instructions--

Converti le assegnazioni per `a`, `b` e `c` in modo da utilizzare l'operatore `*=`.

# --hints--

`a` dovrebbe essere uguale a `25`.

```js
assert(a === 25);
```

`b` dovrebbe essere uguale a `36`.

```js
assert(b === 36);
```

`c` dovrebbe essere uguale a `46`.

```js
assert(c === 46);
```

Dovresti usare l'operatore `*=` per ogni variabile.

```js
assert(__helpers.removeJSComments(code).match(/\*=/g).length === 3);
```

Non dovresti modificare il codice sopra il commento specificato.

```js
assert(
  /let a = 5;/.test(__helpers.removeJSComments(code)) &&
    /let b = 12;/.test(__helpers.removeJSComments(code)) &&
    /let c = 4\.6;/.test(__helpers.removeJSComments(code))
);
```

# --seed--

## --after-user-code--

```js
(function(a,b,c){ return "a = " + a + ", b = " + b + ", c = " + c; })(a,b,c);
```

## --seed-contents--

```js
let a = 5;
let b = 12;
let c = 4.6;

// Only change code below this line
a = a * 5;
b = 3 * b;
c = c * 10;
```

# --solutions--

```js
let a = 5;
let b = 12;
let c = 4.6;

a *= 5;
b *= 3;
c *= 10;
```
