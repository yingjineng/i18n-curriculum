---
id: 6732b28eeadda1158cdbff7b
title: 如何检查数组是否包含某个值？
challengeType: 11
videoId: NjZI_TlIiXk
dashedName: how-can-you-check-if-an-array-contains-a-certain-value
---

# --description--

观看视频或阅读文字稿并回答下列问题。

# --transcript--

如何检查数组是否包含某个值？

在 JavaScript 中，`includes()` 方法是一种简单高效的方式，用于检查数组中是否包含特定的值。该方法会返回一个布尔值：如果数组包含指定元素，则返回 `true`，否则返回 `false`。

当你需要快速验证某个元素是否存在于数组中，而不需要知道它的具体位置时，`includes()` 方法非常有用。让我们来看一个使用 `includes()` 方法的例子：

```js
let fruits = ["apple", "banana", "orange", "mango"];
console.log(fruits.includes("banana")); // true
console.log(fruits.includes("grape"));  // false
```

在这个例子中，我们有一个水果数组。我们用 `includes()` 方法检查数组中是否有 `banana`。因为 `banana` 确实存在，所以返回 `true`。接着我们检查 `grape`，因为它不在数组中，所以返回 `false`。

当处理字符串时，`includes()` 方法是区分大小写的。这意味着 `Banana`（首字母大写）和 `banana`（全小写）被视为不同的值。下面是一个例子：

```js
let fruits = ["apple", "banana", "orange"];
console.log(fruits.includes("banana")); // true
console.log(fruits.includes("Banana")); // false
```

在这个例子中，`banana`（全小写）能在数组中找到，但 `Banana`（首字母大写）找不到，所以第二个 `includes()` 调用返回 `false`。

`includes()` 方法还可以接受一个可选的第二个参数，指定从数组的哪个位置开始搜索。如果你只想在数组的某一部分检查元素是否存在，这个参数就很有用。用法如下：

```js
let numbers = [10, 20, 30, 40, 50, 30, 60];
console.log(numbers.includes(30, 3)); // true
console.log(numbers.includes(30, 4)); // true
```

第一个 `console.log` 从索引 `3` 开始查找数字 `30`。在索引 `3` 之后确实有一个 `30`，所以返回 `true`。

第二个 `console.log` 从索引 `4` 开始查找，之后同样有 `30`，因此也返回 `true`。

需要注意的是，`includes()` 使用严格相等（`===`）进行比较，这意味着它能区分不同的数据类型。例如：

```js
let mixedArray = [1, "2", 3, "4", 5];
console.log(mixedArray.includes(2));  // false
console.log(mixedArray.includes("2")); // true
```

在这个例子中，数字 `2` 和字符串 `"2"` 被视为不同的数据类型。因此，第一个 `console.log` 返回 `false`，而第二个返回 `true`。

`includes()` 方法是检查数组中元素是否存在的强大工具。它简单易用、高效，能帮你避免编写更复杂的循环或条件语句来查找数组。无论你处理的是字符串、数字还是混合类型数据，`includes()` 都能为你提供一种直接验证值是否存在于数组中的方式。

# --questions--

## --text--

以下代码的输出是什么？

```js
let arr = [1, 2, 3, 4, 5];
console.log(arr.includes(3, 3));
```

## --answers--

`true`

### --feedback--

`includes()` 的第二个参数指定搜索的起始位置。

---

`false`

---

`undefined`

### --feedback--

`includes()` 的第二个参数指定搜索的起始位置。

---

这会抛出错误。

### --feedback--

`includes()` 的第二个参数指定搜索的起始位置。

## --video-solution--

2

## --text--

以下代码的输出是什么？

```js
let arr = ["a", "b", "c", "d", "e"];
console.log(arr.includes("C"));
```

## --answers--

`true`

### --feedback--

请记住，`includes()` 在处理字符串时是区分大小写的。

---

`false`

---

`undefined`

### --feedback--

请记住，`includes()` 在处理字符串时是区分大小写的。

---

这会抛出错误。

### --feedback--

请记住，`includes()` 在处理字符串时是区分大小写的。

## --video-solution--

2

## --text--

以下代码的输出是什么？

```js
let arr = [1, "2", 3, "4", 5];
console.log(arr.includes("3"));
```

## --answers--

`true`

### --feedback--

`includes()` 方法使用严格相等（`===`）进行比较。

---

`false`

---

`undefined`

### --feedback--

`includes()` 方法使用严格相等（`===`）进行比较。

---

这会抛出错误。

### --feedback--

`includes()` 方法使用严格相等（`===`）进行比较。

## --video-solution--

2

