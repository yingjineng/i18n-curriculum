---
id: 587d7b89367417b2b2512b48
title: 使用 spread 運算符展開數組項
challengeType: 1
forumTopicId: 301222
dashedName: use-the-spread-operator-to-evaluate-arrays-in-place
---

# --description--

ES6 introduces the <dfn>spread operator</dfn>, which allows us to expand arrays and other expressions in places where multiple parameters or elements are expected.

下面的 ES5 代碼使用了 `apply()` 來計算數組的最大值：

```js
var arr = [6, 89, 3, 45];
var maximus = Math.max.apply(null, arr);
```

`maximus` 的值爲 `89`。

我們必須使用 `Math.max.apply(null, arr)`，因爲 `Math.max(arr)` 返回 `NaN`。 `Math.max()` 函數中需要傳入的是一系列由逗號分隔的參數，而不是一個數組。 展開操作符可以提升代碼的可讀性，使代碼易於維護。

```js
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr);
```

`maximus` 的值應該是 `89`。

`...arr` 返回一個解壓縮的數組。 換句話說，它展開了數組。 然而，展開操作符只能夠在函數的參數中或者數組中使用。 例如：

```js
const spreaded = [...arr];
```

下面的代碼將不能運行：

```js
const spreaded = ...arr;
```

# --instructions--

使用展開操作符將 `arr1` 中的全部內容複製到另一個數組 `arr2` 中。

# --hints--

`arr2` 應該是從 `arr1` 複製而來。

```js
assert(arr2.every((v, i) => v === arr1[i]) && arr2.length);
```

應使用展開操作符 `...` 來複制 `arr1`。

```js
assert(__helpers.removeJSComments(code).match(/Array\(\s*\.\.\.arr1\s*\)|\[\s*\.\.\.arr1\s*\]/));
```

當 `arr1` 改變的時候，`arr2` 應保持不變。

```js
assert((arr1, arr2) => {
  arr1.push('JUN');
  return arr2.length < arr1.length;
});
```

# --seed--

## --seed-contents--

```js
const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
let arr2;

arr2 = [];  // Change this line

console.log(arr2);
```

# --solutions--

```js
const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
let arr2;

arr2 = [...arr1];
```
