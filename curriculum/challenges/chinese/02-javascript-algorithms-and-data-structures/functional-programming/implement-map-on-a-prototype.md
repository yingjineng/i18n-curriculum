---
id: 587d7b8f367417b2b2512b62
title: 在原型上实现 map 方法
challengeType: 1
forumTopicId: 301230
dashedName: implement-map-on-a-prototype
---

# --description--

As you have seen from applying `Array.prototype.map()`, or simply `map()` earlier, the `map` method returns an array of the same length as the one it was called on. It also doesn't alter the original array, as long as its callback function doesn't.

换句话说，`map` 是一个纯函数，它的输出仅取决于输入的数组和作为参数传入的回调函数。 此外，它接收另一个函数作为它的参数。

实现一个 `map`，加深对它的了解。 你可以用 `for` 循环或者 `Array.prototype.forEach()` 方法。

# --instructions--

写一个和 `Array.prototype.map()` 一样的 `Array.prototype.myMap()`。 不能使用内置的 `map` 方法。 在 `myMap` 方法内，可以使用 `this` 访问 `Array` 实例。

# --hints--

`[23, 65, 98, 5, 13].myMap(item => item * 2)` 应该等于 `[46, 130, 196, 10, 26]`。

```js
const _test_s = [23, 65, 98, 5, 13];
const _callback = item => item * 2;
assert(JSON.stringify(_test_s.map(_callback)) === JSON.stringify(_test_s.myMap(_callback)));
```

`["naomi", "quincy", "camperbot"].myMap(element => element.toUpperCase())` 应该返回 `["NAOMI", "QUINCY", "CAMPERBOT"]`。

```js
const _test_s = ["naomi", "quincy", "camperbot"];
const _callback = element => element.toUpperCase();
assert(JSON.stringify(_test_s.map(_callback)) === JSON.stringify(_test_s.myMap(_callback)));
```

`[1, 1, 2, 5, 2].myMap((element, index, array) => array[index + 1] || array[0])` 应该返回 `[1, 2, 5, 2, 1]`。

```js
const _test_s = [1, 1, 2, 5, 2];
const _callback = (element, index, array) => array[index + 1] || array[0];
assert(JSON.stringify(_test_s.map(_callback)) === JSON.stringify(_test_s.myMap(_callback)));
```

你的代码不应该使用 `map` 方法。

```js
assert(!__helpers.removeJSComments(code).match(/\.?[\s\S]*?map/g));
```

# --seed--

## --seed-contents--

```js
Array.prototype.myMap = function(callback) {
  const newArray = [];
  // Only change code below this line

  // Only change code above this line
  return newArray;
};
```

# --solutions--

```js
Array.prototype.myMap = function(callback) {
  const newArray = [];
  for (let i = 0; i < this.length; i++) {
    newArray.push(callback(this[i], i, this));
  }
  return newArray;
};

// Test case
const s = [23, 65, 98, 5];
const doubled_s = s.myMap(item => item * 2);
```
