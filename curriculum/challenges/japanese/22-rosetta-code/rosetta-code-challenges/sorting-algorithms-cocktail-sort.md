---
id: 5a23c84252665b21eecc8004
title: ソートアルゴリズム / カクテルシェーカーソート
challengeType: 1
forumTopicId: 302312
dashedName: sorting-algorithmscocktail-sort
---

# --description--

<a href="https://rosettacode.org/wiki/Sorting_algorithms/Cocktail_sort" target="_blank" rel="noopener noreferrer nofollow">カクテルシェーカーソート</a>は、バブルソートの改良版です。 カクテルソートでは、与えられた数値配列について、先頭から末尾まで横断し、最大の数値を末尾に移動します。 次に、配列を逆行して、最小の数値を先頭に移動します。 これら 2 つのパスを繰り返して、次の最大 / 最小の数を配列内の正しい位置に移動し、それをソートされるまで繰り返します。

# --instructions--

カクテルシェーカーソートを使って、与えられた配列をソートする関数を記述してください。

# --hints--

`cocktailSort` は関数とします。

```js
assert(typeof cocktailSort == 'function');
```

`cocktailSort([25, 32, 12, 7, 20])` は配列を返す必要があります。

```js
assert(Array.isArray(cocktailSort([25, 32, 12, 7, 20])));
```

`cocktailSort([25, 32, 12, 7, 20])` は `[7, 12, 20, 25, 32]` を返す必要があります。

```js
assert.deepEqual(cocktailSort([25, 32, 12, 7, 20]), [7, 12, 20, 25, 32]);
```

`cocktailSort([38, 45, 35, 8, 13])` は `[8, 13, 35, 38, 45]` を返す必要があります。

```js
assert.deepEqual(cocktailSort([38, 45, 35, 8, 13]), [8, 13, 35, 38, 45]);
```

`cocktailSort([43, 36, 20, 34, 24])` は `[20, 24, 34, 36, 43]` を返す必要があります。

```js
assert.deepEqual(cocktailSort([43, 36, 20, 34, 24]), [20, 24, 34, 36, 43]);
```

`cocktailSort([12, 33, 26, 18, 1, 16, 38])` は `[1, 12, 16, 18, 26, 33, 38]` を返す必要があります。

```js
assert.deepEqual(cocktailSort([12, 33, 26, 18, 1, 16, 38]), [
  1,
  12,
  16,
  18,
  26,
  33,
  38
]);
```

`cocktailSort([3, 39, 48, 16, 1, 4, 29])` は `[1, 3, 4, 16, 29, 39, 48]` を返す必要があります。

```js
assert.deepEqual(cocktailSort([3, 39, 48, 16, 1, 4, 29]), [
  1,
  3,
  4,
  16,
  29,
  39,
  48
]);
```

# --seed--

## --seed-contents--

```js
function cocktailSort(arr) {

}
```

# --solutions--

```js
function cocktailSort(arr) {
  let isSorted = true;
  while (isSorted) {
    for (let i = 0; i < arr.length - 1; i++) {
      if (arr[i] > arr[i + 1]) {
        let temp = arr[i];
        arr[i] = arr[i + 1];
        arr[i + 1] = temp;
        isSorted = true;
      }
    }

    if (!isSorted) break;

    isSorted = false;

    for (let j = arr.length - 1; j > 0; j--) {
      if (arr[j - 1] > arr[j]) {
        let temp = arr[j];
        arr[j] = arr[j - 1];
        arr[j - 1] = temp;
        isSorted = true;
      }
    }
  }

  return arr;
}
```
