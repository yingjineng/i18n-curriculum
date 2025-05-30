---
id: 56592a60ddddeae28f7aa8e1
title: 使用索引操作多维数组
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

在这个例子中，`subarray` 的值为 `[[10, 11, 12], 13, 14]`， `nestedSubarray` 的值为 `[10, 11, 12]`，`element` 的值为 `11` 。

**注意：** 数组名与方括号之间不应该有任何空格，比如 `array [0][0]` 甚至是 `array [0] [0]` 都是不允许的。 尽管 JavaScript 能够正确处理这种情况，但是当其他程序员阅读你写的代码时，这可能让他们感到困惑。

# --instructions--

使用方括号从 `myArray` 中选取一个值，使得 `myData` 等于 `8`。

# --hints--

`myData` 应该等于 `8`。

```js
assert(myData === 8);
```

你应该使用方括号从 `myArray` 中读取正确的值。

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
