---
id: 587d7b7b367417b2b2512b13
title: 使用展开运算符复制数组
challengeType: 1
forumTopicId: 301157
dashedName: copy-an-array-with-the-spread-operator
---

# --description--

While `slice()` allows us to be selective about what elements of an array to copy, among several other useful tasks, ES6's new <dfn>spread operator</dfn> allows us to easily copy *all* of an array's elements, in order, with a simple and highly readable syntax. The spread syntax simply looks like this: `...`

我们可以用展开运算符来复制数组：

```js
let thisArray = [true, true, undefined, false, null];
let thatArray = [...thisArray];
```

`thatArray` 等于 `[true, true, undefined, false, null]`。 `thisArray` 保持不变， `thatArray` 包含与 `thisArray` 相同的元素。

# --instructions--

我们已经定义了一个 `copyMachine` 函数，它接受 `arr`（一个数组）和 `num`（一个数字）作为输入参数。 该函数需要返回一个由 `num` 个 `arr` 组成的新的二维数组。 同时，我们写好了大致的流程，只是细节实现还没有写完。 请修改这个函数，使用展开语法，使该函数能正常工作（提示：我们已经学到过的一个方法很适合用在这里）！

# --hints--

`copyMachine([true, false, true], 2)` 应返回 `[[true, false, true], [true, false, true]]`。

```js
assert.deepEqual(copyMachine([true, false, true], 2), [
  [true, false, true],
  [true, false, true]
]);
```

`copyMachine([1, 2, 3], 5)` 应返回 `[[1, 2, 3], [1, 2, 3], [1, 2, 3], [1, 2, 3], [1, 2, 3]]`。

```js
assert.deepEqual(copyMachine([1, 2, 3], 5), [
  [1, 2, 3],
  [1, 2, 3],
  [1, 2, 3],
  [1, 2, 3],
  [1, 2, 3]
]);
```

`copyMachine([true, true, null], 1)` 应返回 `[[true, true, null]]`。

```js
assert.deepEqual(copyMachine([true, true, null], 1), [[true, true, null]]);
```

`copyMachine(["it works"], 3)` 应返回 `[["it works"], ["it works"], ["it works"]]`。

```js
assert.deepEqual(copyMachine(['it works'], 3), [
  ['it works'],
  ['it works'],
  ['it works']
]);
```

`copyMachine` 函数中应对 `arr` 使用展开运算符（`spread operator`）。

```js
assert(__helpers.removeJSComments(__helpers.removeJSComments(code)).match(/\.\.\.\s*arr/));
```

# --seed--

## --seed-contents--

```js
function copyMachine(arr, num) {
  let newArr = [];
  while (num >= 1) {
    // Only change code below this line

    // Only change code above this line
    num--;
  }
  return newArr;
}

console.log(copyMachine([true, false, true], 2));
```

# --solutions--

```js
function copyMachine(arr,num){
    let newArr=[];
    while(num >=1){
    newArr.push([...arr]);
    num--;
    }
    return newArr;
}
console.log(copyMachine([true, false, true], 2));
```
