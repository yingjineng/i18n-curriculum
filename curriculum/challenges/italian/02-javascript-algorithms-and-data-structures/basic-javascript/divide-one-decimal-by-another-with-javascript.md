---
id: bd7993c9ca9feddfaeb7bdef
title: Dividere un decimale per un altro con JavaScript
challengeType: 1
forumTopicId: 18255
dashedName: divide-one-decimal-by-another-with-javascript
---

# --description--

Now let's divide one decimal by another.

# --instructions--

Modifica `0.0` in modo che `quotient` sia uguale a `2.2`.

# --hints--

La variabile `quotient` dovrebbe essere uguale a `2.2`

```js
assert(quotient === 2.2);
```

Dovresti usare l'operatore `/` per dividere 4.4 per 2

```js
assert(/4\.40*\s*\/\s*2\.*0*/.test(__helpers.removeJSComments(code)));
```

La variabile quotient deve essere assegnata solo una volta

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
