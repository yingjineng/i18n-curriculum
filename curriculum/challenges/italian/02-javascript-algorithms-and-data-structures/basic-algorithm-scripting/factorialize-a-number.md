---
id: a302f7aae1aa3152a5b413bc
title: Fattoriale di un numero
challengeType: 1
forumTopicId: 16013
dashedName: factorialize-a-number
---

# --description--

Return the factorial of the provided integer.

Se l'intero è rappresentato con la lettera `n`, un fattoriale è il prodotto di tutti gli interi positivi minori o uguali a `n`.

I fattoriali sono spesso rappresentati con la notazione abbreviata `n!`

For example: `5! = 1 * 2 * 3 * 4 * 5 = 120`

Verranno passati alla funzione solo interi maggiori o uguali a zero.

# --hints--

`factorialize(5)` dovrebbe restituire un numero.

```js
assert.isNumber(factorialize(5));
```

`factorialize(5)` dovrebbe restituire `120`.

```js
assert.strictEqual(factorialize(5), 120);
```

`factorialize(10)` dovrebbe restituire `3628800`.

```js
assert.strictEqual(factorialize(10), 3628800);
```

`factorialize(20)` dovrebbe restituire `2432902008176640000`.

```js
assert.strictEqual(factorialize(20), 2432902008176640000);
```

`factorialize(0)` dovrebbe restituire `1`.

```js
assert.strictEqual(factorialize(0), 1);
```

# --seed--

## --seed-contents--

```js
function factorialize(num) {
  return num;
}

factorialize(5);
```

# --solutions--

```js
function factorialize(num) {
  return num < 1 ? 1 : num * factorialize(num - 1);
}

factorialize(5);
```
