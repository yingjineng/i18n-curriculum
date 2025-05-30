---
id: a24c1a4622e3c05097f71d67
title: 找出元素在排序后数组中的索引
challengeType: 1
forumTopicId: 16094
dashedName: where-do-i-belong
---

# --description--

Return the lowest index at which a value (second argument) should be inserted into an array (first argument) once it has been sorted. The returned value should be a number.

例如，`getIndexToIns([1,2,3,4], 1.5)` 应该返回 `1` 因为1.5 大于 `1`（索引为 0）且小于 `2`（索引为 1）。

同样地，`getIndexToIns([20,3,5], 19)` 应该返回 `2`。 因为数组排序后会变成 `[3,5,20]`，而 `19` 小于 `20`（索引为 2）且大于 `5`（索引为 1）。

# --hints--

`getIndexToIns([10, 20, 30, 40, 50], 35)` 应返回一个数字。

```js
assert.isNumber(getIndexToIns([10, 20, 30, 40, 50], 35));
```

`getIndexToIns([10, 20, 30, 40, 50], 35)` 应返回 `3`。

```js
assert.strictEqual(getIndexToIns([10, 20, 30, 40, 50], 35), 3);
```

`getIndexToIns([10, 20, 30, 40, 50], 30)` 应返回一个数字。

```js
assert.isNumber(getIndexToIns([10, 20, 30, 40, 50], 30));
```

`getIndexToIns([10, 20, 30, 40, 50], 30)` 应返回 `2`。

```js
assert.strictEqual(getIndexToIns([10, 20, 30, 40, 50], 30), 2);
```

`getIndexToIns([40, 60], 50)` 应返回一个数字。

```js
assert.isNumber(getIndexToIns([40, 60], 50));
```

`getIndexToIns([40, 60], 50)` 应返回 `1`。

```js
assert.strictEqual(getIndexToIns([40, 60], 50), 1);
```

`getIndexToIns([3, 10, 5], 3)` 应返回一个数字。

```js
assert.isNumber(getIndexToIns([3, 10, 5], 3));
```

`getIndexToIns([3, 10, 5], 3)` 应返回 `0`。

```js
assert.strictEqual(getIndexToIns([3, 10, 5], 3), 0);
```

`getIndexToIns([5, 3, 20, 3], 5)` 应返回一个数字。

```js
assert.isNumber(getIndexToIns([5, 3, 20, 3], 5));
```

`getIndexToIns([5, 3, 20, 3], 5)` 应返回 `2`。

```js
assert.strictEqual(getIndexToIns([5, 3, 20, 3], 5), 2);
```

`getIndexToIns([2, 20, 10], 19)` 应返回 `2`。

```js
assert.strictEqual(getIndexToIns([2, 20, 10], 19), 2);
```

`getIndexToIns([2, 20, 10], 19)` 应返回一个数字。

```js
assert.isNumber(getIndexToIns([2, 20, 10], 19));
```

`getIndexToIns([2, 5, 10], 15)` 应返回 `3`。

```js
assert.strictEqual(getIndexToIns([2, 5, 10], 15), 3);
```

`getIndexToIns([2, 5, 10], 15)` 应返回一个数字。

```js
assert.isNumber(getIndexToIns([2, 5, 10], 15));
```

`getIndexToIns([], 1)` 应返回一个数字。

```js
assert.isNumber(getIndexToIns([], 1));
```

`getIndexToIns([], 1)`应该返回 `0`。

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
