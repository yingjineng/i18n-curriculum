---
id: 587d7b7e367417b2b2512b22
title: Usare la funzione ParseInt con una base
challengeType: 1
forumTopicId: 301182
dashedName: use-the-parseint-function-with-a-radix
---

# --description--

The `parseInt()` function parses a string and returns an integer. It takes a second argument for the radix, which specifies the base of the number in the string. The radix can be an integer between 2 and 36.

La chiamata alla funzione apparirà così:

```js
parseInt(string, radix);
```

Ecco un esempio:

```js
const a = parseInt("11", 2);
```

La variabile radix dice che `11` è nel sistema binario, o in base 2. Questo esempio converte la stringa `11` in un intero `3`.

# --instructions--

Usa `parseInt()` nella funzione `convertToInteger` in modo che converta un numero binario in un intero e lo restituisca.

# --hints--

`convertToInteger` dovrebbe utilizzare la funzione `parseInt()`

```js
assert(/parseInt/g.test(__helpers.removeJSComments(code)));
```

`convertToInteger("10011")` dovrebbe restituire un numero

```js
assert(typeof convertToInteger('10011') === 'number');
```

`convertToInteger("10011")` dovrebbe restituire 19

```js
assert(convertToInteger('10011') === 19);
```

`convertToInteger("111001")` dovrebbe restituire 57

```js
assert(convertToInteger('111001') === 57);
```

`convertToInteger("JamesBond")` dovrebbe restituire `NaN`

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
