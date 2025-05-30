---
id: cf1111c1c12feddfaeb1bdef
title: Generare numeri interi casuali con JavaScript
challengeType: 1
forumTopicId: 18186
dashedName: generate-random-whole-numbers-with-javascript
---

# --description--

You can generate random decimal numbers with `Math.random()`, but sometimes you need to generate random whole numbers. The following process will give you a random whole number less than `20`:

1. Use `Math.random()` to generate a random decimal number.
2. Moltiplica quel numero decimale casuale per `20`.
3. Usa `Math.floor()` per arrotondare il numero per difetto al numero intero più vicino.

Ricorda che `Math.random()` non può mai restituire `1`, quindi non è possibile ottenere `20` dato che stai arrotondando con `Math.floor()`. Questo procedimento ti darà un numero intero casuale nell'intervallo da `0` a `19`.

Mettendo tutto insieme, questo è il codice:

```js
Math.floor(Math.random() * 20);
```

Stai chiamando `Math.random()`, moltiplicando il risultato per 20, quindi passando il valore a `Math.floor()` per arrotondare il valore per difetto al numero intero più vicino.

# --instructions--

Usa questa tecnica per generare e restituire un numero intero casuale nell'intervallo tra `0` e `9`.

# --hints--

Il risultato di `randomWholeNum` dovrebbe essere un numero intero.

```js
assert(
  typeof randomWholeNum() === 'number' &&
    (function () {
      var r = randomWholeNum();
      return Math.floor(r) === r;
    })()
);
```

Dovresti usare `Math.random` per generare un numero casuale.

```js
assert(__helpers.removeJSComments(code).match(/Math.random/g).length >= 1);
```

Dovresti moltiplicare il risultato di `Math.random` per 10 per ottenere un numero nell'intervallo tra zero e nove.

```js
assert(
  __helpers.removeJSComments(code).match(/\s*?Math.random\s*?\(\s*?\)\s*?\*\s*?10[\D]\s*?/g) ||
    __helpers.removeJSComments(code).match(/\s*?10\s*?\*\s*?Math.random\s*?\(\s*?\)\s*?/g)
);
```

Dovresti usare `Math.floor` per rimuovere la parte decimale del numero.

```js
assert(__helpers.removeJSComments(code).match(/Math.floor/g).length >= 1);
```

# --seed--

## --after-user-code--

```js
(function(){return randomWholeNum();})();
```

## --seed-contents--

```js
function randomWholeNum() {
  return Math.random();
}
```

# --solutions--

```js
function randomWholeNum() {
  return Math.floor(Math.random() * 10);
}
```
