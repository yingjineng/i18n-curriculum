---
id: 587d7dab367417b2b2512b6f
title: 使用 some 方法檢查數組中是否有元素是否符合條件
challengeType: 1
forumTopicId: 301314
dashedName: use-the-some-method-to-check-that-any-elements-in-an-array-meet-a-criteria
---

# --description--

The `some` method works with arrays to check if *any* element passes a particular test. It returns a Boolean value - `true` if any of the values meet the criteria, `false` if not.

舉個例子，下面的代碼檢測數組`numbers`中是否有元素小於 10：

```js
const numbers = [10, 50, 8, 220, 110, 11];

numbers.some(function(currentValue) {
  return currentValue < 10;
});
```

`some` 方法將返回 `true`。

# --instructions--

在 `checkPositive` 函數值中使用 `some` 檢查 `arr` 中是否有元素爲正數。 函數應返回一個布爾值。

# --hints--

應該使用 `some` 方法。

```js
assert(__helpers.removeJSComments(code).match(/\.some/g));
```

`checkPositive([1, 2, 3, -4, 5])` 應返回 `true`。

```js
assert(checkPositive([1, 2, 3, -4, 5]));
```

`checkPositive([1, 2, 3, 4, 5])` 應返回 `true`。

```js
assert(checkPositive([1, 2, 3, 4, 5]));
```

`checkPositive([-1, -2, -3, -4, -5])` 應返回 `false`。

```js
assert(!checkPositive([-1, -2, -3, -4, -5]));
```

# --seed--

## --seed-contents--

```js
function checkPositive(arr) {
  // Only change code below this line


  // Only change code above this line
}

checkPositive([1, 2, 3, -4, 5]);
```

# --solutions--

```js
function checkPositive(arr) {
  return arr.some(elem => elem > 0);
}
```
