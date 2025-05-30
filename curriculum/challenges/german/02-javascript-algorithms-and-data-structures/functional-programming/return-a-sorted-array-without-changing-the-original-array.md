---
id: 587d7da9367417b2b2512b6a
title: Ein sortiertes Array zurückgeben, ohne das ursprüngliche Array zu verändern
challengeType: 1
forumTopicId: 301237
dashedName: return-a-sorted-array-without-changing-the-original-array
---

# --description--

A side effect of the `sort` method is that it changes the order of the elements in the original array. In other words, it mutates the array in place. One way to avoid this is to first concatenate an empty array to the one being sorted (remember that `slice` and `concat` return a new array), then run the `sort` method.

# --instructions--

Verwende die Methode `sort` in der Funktion `nonMutatingSort`, um die Elemente eines Arrays in aufsteigender Reihenfolge zu sortieren. Die Funktion sollte ein neues Array zurückgeben und die Variable `globalArray` nicht verändern.

# --hints--

Dein Code sollte die Methode `sort` verwenden.

```js
assert(nonMutatingSort.toString().match(/\.sort/g));
```

Die Variable `globalArray` sollte sich nicht ändern.

```js
assert(JSON.stringify(globalArray) === JSON.stringify([5, 6, 3, 2, 9]));
```

`nonMutatingSort(globalArray)` sollte `[2, 3, 5, 6, 9]` zurückgeben.

```js
assert(
  JSON.stringify(nonMutatingSort(globalArray)) ===
    JSON.stringify([2, 3, 5, 6, 9])
);
```

`nonMutatingSort(globalArray)` sollte nicht hart kodiert sein.

```js
assert(!nonMutatingSort.toString().match(/\[.*?[23569].*?\]/gs));
```

Die Funktion sollte ein neues Array zurückgeben, nicht das Array, das ihr übergeben wurde.

```js
assert(nonMutatingSort(globalArray) !== globalArray);
```

`nonMutatingSort([1, 30, 4, 21, 100000])` sollte `[1, 4, 21, 30, 100000]` zurückgeben.

```js
assert(JSON.stringify(nonMutatingSort([1, 30, 4, 21, 100000])) ===
    JSON.stringify([1, 4, 21, 30, 100000]))
```

`nonMutatingSort([140000, 104, 99])` sollte `[99, 104, 140000]` zurückgeben.

```js
assert(JSON.stringify(nonMutatingSort([140000, 104, 99])) ===
    JSON.stringify([99, 104, 140000]))
```

# --seed--

## --seed-contents--

```js
const globalArray = [5, 6, 3, 2, 9];

function nonMutatingSort(arr) {
  // Only change code below this line


  // Only change code above this line
}

nonMutatingSort(globalArray);
```

# --solutions--

```js
const globalArray = [5, 6, 3, 2, 9];
function nonMutatingSort(arr) {
  return [].concat(arr).sort((a,b) => a-b);
}
```
