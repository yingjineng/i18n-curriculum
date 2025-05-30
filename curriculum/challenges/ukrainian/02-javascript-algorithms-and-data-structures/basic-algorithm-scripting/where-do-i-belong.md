---
id: a24c1a4622e3c05097f71d67
title: Куди я належу
challengeType: 1
forumTopicId: 16094
dashedName: where-do-i-belong
---

# --description--

Return the lowest index at which a value (second argument) should be inserted into an array (first argument) once it has been sorted. The returned value should be a number.

Наприклад, `getIndexToIns([1,2,3,4], 1.5)` має повертати `1`, оскільки він більший за `1` (індекс 0), але менший за `2` (індекс 1).

Аналогічно, `getIndexToIns([20,3,5], 19)` має повертати `2`, оскільки після сортування масиву він виглядатиме як `[3,5,20]`, а `19` менше за `20` (індекс 2) та більше за `5` (індекс 1).

# --hints--

`getIndexToIns([10, 20, 30, 40, 50], 35)` має повертати число.

```js
assert.isNumber(getIndexToIns([10, 20, 30, 40, 50], 35));
```

`getIndexToIns([10, 20, 30, 40, 50], 35)` має повертати `3`.

```js
assert.strictEqual(getIndexToIns([10, 20, 30, 40, 50], 35), 3);
```

`getIndexToIns([10, 20, 30, 40, 50], 30)` має повертати число.

```js
assert.isNumber(getIndexToIns([10, 20, 30, 40, 50], 30));
```

`getIndexToIns([10, 20, 30, 40, 50], 30)` має повертати `2`.

```js
assert.strictEqual(getIndexToIns([10, 20, 30, 40, 50], 30), 2);
```

`getIndexToIns([40, 60], 50)` має повертати число.

```js
assert.isNumber(getIndexToIns([40, 60], 50));
```

`getIndexToIns([40, 60], 50)` має повертати `1`.

```js
assert.strictEqual(getIndexToIns([40, 60], 50), 1);
```

`getIndexToIns([3, 10, 5], 3)` має повертати число.

```js
assert.isNumber(getIndexToIns([3, 10, 5], 3));
```

`getIndexToIns([3, 10, 5], 3)` має повертати `0`.

```js
assert.strictEqual(getIndexToIns([3, 10, 5], 3), 0);
```

`getIndexToIns([5, 3, 20, 3], 5)` має повертати число.

```js
assert.isNumber(getIndexToIns([5, 3, 20, 3], 5));
```

`getIndexToIns([5, 3, 20, 3], 5)` має повертати `2`.

```js
assert.strictEqual(getIndexToIns([5, 3, 20, 3], 5), 2);
```

`getIndexToIns([2, 20, 10], 19)` має повертати `2`.

```js
assert.strictEqual(getIndexToIns([2, 20, 10], 19), 2);
```

`getIndexToIns([2, 20, 10], 19)` має повертати число.

```js
assert.isNumber(getIndexToIns([2, 20, 10], 19));
```

`getIndexToIns([2, 5, 10], 15)` має повертати `3`.

```js
assert.strictEqual(getIndexToIns([2, 5, 10], 15), 3);
```

`getIndexToIns([2, 5, 10], 15)` має повертати число.

```js
assert.isNumber(getIndexToIns([2, 5, 10], 15));
```

`getIndexToIns([], 1)` має повертати число.

```js
assert.isNumber(getIndexToIns([], 1));
```

`getIndexToIns([], 1)` має повертати `0`.

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
