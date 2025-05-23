---
id: a24c1a4622e3c05097f71d67
title: Qual è il mio posto
challengeType: 1
forumTopicId: 16094
dashedName: where-do-i-belong
---

# --description--

Return the lowest index at which a value (second argument) should be inserted into an array (first argument) once it has been sorted. The returned value should be a number.

Per esempio, `getIndexToIns([1,2,3,4], 1.5)` dovrebbe restituire `1` perché è maggiore di `1` (indice 0), ma minore di `2` (indice 1).

Allo stesso modo, `getIndexToIns([20,3,5], 19)` dovrebbe restituire `2` perché l'array ordinato sarà `[3,5,20]` e `19` è minore di `20` (indice 2) e maggiore di `5` (indice 1).

# --hints--

`getIndexToIns([10, 20, 30, 40, 50], 35)` dovrebbe restituire un numero.

```js
assert.isNumber(getIndexToIns([10, 20, 30, 40, 50], 35));
```

`getIndexToIns([10, 20, 30, 40, 50], 35)` dovrebbe restituire `3`.

```js
assert.strictEqual(getIndexToIns([10, 20, 30, 40, 50], 35), 3);
```

`getIndexToIns([10, 20, 30, 40, 50], 30)` dovrebbe restituire un numero.

```js
assert.isNumber(getIndexToIns([10, 20, 30, 40, 50], 30));
```

`getIndexToIns([10, 20, 30, 40, 50], 30)` dovrebbe restituire `2`.

```js
assert.strictEqual(getIndexToIns([10, 20, 30, 40, 50], 30), 2);
```

`getIndexToIns([40, 60], 50)` dovrebbe restituire un numero.

```js
assert.isNumber(getIndexToIns([40, 60], 50));
```

`getIndexToIns([40, 60], 50)` dovrebbe restituire `1`.

```js
assert.strictEqual(getIndexToIns([40, 60], 50), 1);
```

`getIndexToIns([3, 10, 5], 3)` dovrebbe restituire un numero.

```js
assert.isNumber(getIndexToIns([3, 10, 5], 3));
```

`getIndexToIns([3, 10, 5], 3)` dovrebbe restituire `0`.

```js
assert.strictEqual(getIndexToIns([3, 10, 5], 3), 0);
```

`getIndexToIns([5, 3, 20, 3], 5)` dovrebbe restituire un numero.

```js
assert.isNumber(getIndexToIns([5, 3, 20, 3], 5));
```

`getIndexToIns([5, 3, 20, 3], 5)` dovrebbe restituire `2`.

```js
assert.strictEqual(getIndexToIns([5, 3, 20, 3], 5), 2);
```

`getIndexToIns([2, 20, 10], 19)` dovrebbe restituire `2`.

```js
assert.strictEqual(getIndexToIns([2, 20, 10], 19), 2);
```

`getIndexToIns([2, 20, 10], 19)` dovrebbe restituire un numero.

```js
assert.isNumber(getIndexToIns([2, 20, 10], 19));
```

`getIndexToIns([2, 5, 10], 15)` dovrebbe restituire `3`.

```js
assert.strictEqual(getIndexToIns([2, 5, 10], 15), 3);
```

`getIndexToIns([2, 5, 10], 15)` dovrebbe restituire un numero.

```js
assert.isNumber(getIndexToIns([2, 5, 10], 15));
```

`getIndexToIns([], 1)` dovrebbe restituire un numero.

```js
assert.isNumber(getIndexToIns([], 1));
```

`getIndexToIns([], 1)` dovrebbe restituire `0`.

```js
assert.strictEqual(getIndexToIns([], 1), 0);
```

# --seed--

## --seed-contents--

```js
function getIndexToIns(arr, num) {
  return num;
}

getIndexToIns([40, 60], 50);
```

# --solutions--

```js
function getIndexToIns(arr, num) {
  arr = arr.sort((a, b) => a - b);

  for (let i = 0; i < arr.length; i++) {
    if (arr[i] >= num) {
      return i;
    }
  }

  return arr.length;
}

getIndexToIns([40, 60], 50);
```
