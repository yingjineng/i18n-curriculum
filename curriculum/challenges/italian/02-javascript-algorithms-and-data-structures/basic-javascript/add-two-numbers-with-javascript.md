---
id: cf1111c1c11feddfaeb3bdef
title: Sommare due numeri con JavaScript
challengeType: 1
forumTopicId: 16650
dashedName: add-two-numbers-with-javascript
---

# --description--

`Number` is a data type in JavaScript which represents numeric data.

Ora proviamo a sommare due numeri usando JavaScript.

JavaScript utilizza il simbolo `+` come operatore di addizione quando è posizionato tra due numeri.

**Esempio:**

```js
const myVar = 5 + 10;
```

`myVar` ora ha il valore `15`.

# --instructions--

Modificare lo `0` in modo che la somma sia uguale a `20`.

# --hints--

`sum` dovrebbe essere uguale a `20`.

```js
assert(sum === 20);
```

Dovresti usare l'operatore `+`.

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
