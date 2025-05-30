---
id: 56592a60ddddeae28f7aa8e1
title: 使用索引操作多維數組
challengeType: 1
forumTopicId: 16159
dashedName: access-multi-dimensional-arrays-with-indexes
---

# --description--

One way to think of a <dfn>multi-dimensional</dfn> array, is as an *array of arrays*. When you use brackets to access your array, the first set of brackets refers to the entries in the outermost (the first level) array, and each additional pair of brackets refers to the next level of entries inside.

**例如：**

```js
const arr = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
  [[10, 11, 12], 13, 14]
];

const subarray = arr[3];
const nestedSubarray = arr[3][0];
const element = arr[3][0][1];
```

在這個例子中，`subarray` 的值爲 `[[10, 11, 12], 13, 14]`， `nestedSubarray` 的值爲 `[10, 11, 12]`，`element` 的值爲 `11` 。

**注意：** 數組名與方括號之間不應該有任何空格，比如 `array [0][0]` 甚至是 `array [0] [0]` 都是不允許的。 儘管 JavaScript 能夠正確處理這種情況，但是當其他程序員閱讀你寫的代碼時，這可能讓他們感到困惑。

# --instructions--

使用方括號從 `myArray` 中選取一個值，使得 `myData` 等於 `8`。

# --hints--

`myData` 應該等於 `8`。

```js
assert(myData === 8);
```

你應該使用方括號從 `myArray` 中讀取正確的值。

```js
assert(/myData=myArray\[2\]\[1\]/.test(__helpers.removeWhiteSpace(__helpers.removeJSComments(code))));
```

# --seed--

## --after-user-code--

```js
if(typeof myArray !== "undefined"){(function(){return "myData: " + myData + " myArray: " + JSON.stringify(myArray);})();}
```

## --seed-contents--

```js
const myArray = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
  [[10, 11, 12], 13, 14],
];

const myData = myArray[0][0];
```

# --solutions--

```js
const myArray = [[1, 2, 3], [4, 5, 6], [7, 8, 9], [[10, 11, 12], 13, 14]];
const myData = myArray[2][1];
```
