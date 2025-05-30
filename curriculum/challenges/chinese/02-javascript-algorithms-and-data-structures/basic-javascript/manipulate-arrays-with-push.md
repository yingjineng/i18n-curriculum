---
id: 56bbb991ad1ed5201cd392cb
title: 使用 push 方法操作数组
challengeType: 1
forumTopicId: 18237
dashedName: manipulate-arrays-with-push
---

# --description--

An easy way to append data to the end of an array is via the `push()` method.

`push()` 方法需要一个或多个 <dfn>参数</dfn> 并将它们根据出现顺序追加到数组的末尾。 它返回数组的新长度。

示例：

```js
const arr1 = [1, 2, 3];
arr1.push(4, 5);

const arr2 = ["Stimpson", "J", "cat"];
arr2.push(["happy", "joy"]);
```

`arr1` 现在值为 `[1, 2, 3, 4, 5]`，`arr2` 的值为 `["Stimpson", "J", "cat", ["happy", "joy"]]`。

# --instructions--

把`["dog", 3]` 压入到 `myArray` 变量的末尾。

# --hints--

`myArray` 现在应该等于 `[["John", 23], ["cat", 2], ["dog", 3]]`。

```js
assert(
  (function (d) {
    if (
      d[2] != undefined &&
      d[0][0] == 'John' &&
      d[0][1] === 23 &&
      d[2][0] == 'dog' &&
      d[2][1] === 3 &&
      d[2].length == 2
    ) {
      return true;
    } else {
      return false;
    }
  })(myArray)
);
```

# --seed--

## --after-user-code--

```js
(function(z){return 'myArray = ' + JSON.stringify(z);})(myArray);
```

## --seed-contents--

```js
// Setup
const myArray = [["John", 23], ["cat", 2]];

// Only change code below this line

```

# --solutions--

```js
const myArray = [["John", 23], ["cat", 2]];
myArray.push(["dog",3]);
```
