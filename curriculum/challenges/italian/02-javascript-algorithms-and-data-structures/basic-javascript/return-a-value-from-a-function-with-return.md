---
id: 56533eb9ac21ba0edf2244c2
title: Restituire un valore da una funzione con Return
challengeType: 1
forumTopicId: 18271
dashedName: return-a-value-from-a-function-with-return
---

# --description--

We can pass values into a function with <dfn>arguments</dfn>. You can use a `return` statement to send a value back out of a function.

**Esempio**

```js
function plusThree(num) {
  return num + 3;
}

const answer = plusThree(5);
```

`answer` ha il valore `8`.

`plusThree` prende un <dfn>argomento</dfn> per `num` e restituisce un valore pari a `num + 3`.

# --instructions--

Crea una funzione `timesFive` che accetta un argomento, lo moltiplica per `5`e restituisce il nuovo valore.

# --hints--

`timesFive` dovrebbe essere una funzione

```js
assert(typeof timesFive === 'function');
```

`timesFive(5)` dovrebbe restituire `25`

```js
assert(timesFive(5) === 25);
```

`timesFive(2)` dovrebbe restituire `10`

```js
assert(timesFive(2) === 10);
```

`timesFive(0)` dovrebbe restituire `0`

```js
assert(timesFive(0) === 0);
```

# --seed--

## --seed-contents--

```js

```

# --solutions--

```js
function timesFive(num) {
  return num * 5;
}
timesFive(10);
```
