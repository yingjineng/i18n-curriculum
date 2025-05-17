---
id: 66edcccbba6dacdb65a59067
title: JavaScript 数组测验
challengeType: 8
dashedName: quiz-javascript-arrays
---

# --description--

要通过本测验，你必须正确回答以下 20 道题中的至少 18 道。

# --quizzes--

## --quiz--

### --question--

#### --text--

以下代码的输出是什么？

```js
const numbers = [1, 2, 3];
console.log(numbers[10]);
```

#### --distractors--

`[1, 2, 3]`

---

`null`

---

`10`

#### --answer--

`undefined`

### --question--

#### --text--

以下哪种方式可以正确地从 `developers` 数组中访问字符串 `"Jessica"`？

#### --distractors--

```js
const developers = ["Jessica", "Naomi", "Tom"];
developers[1]
```

---

```js
const developers = ["Jessica", "Naomi", "Tom"];
developers[2]
```

---

```js
const developers = ["Jessica", "Naomi", "Tom"];
developers[-1]
```

#### --answer--

```js
const developers = ["Jessica", "Naomi", "Tom"];
developers[0]
```

### --question--

#### --text--

`index` 变量将被赋予什么值？

```js
const numbers = [10, 20, 30, 40];
const index = numbers.indexOf(20);
console.log(index);
```

#### --distractors--

2

---

3

---

-1

#### --answer--

1

### --question--

#### --text--

剩余语法（rest syntax）是做什么用的？

#### --distractors--

用于将字符串分割为子字符串数组。

---

用于在数组的任意位置添加或删除元素。

---

用于向数组末尾添加元素，并返回新的长度。

#### --answer--

用于将数组中的剩余元素收集到一个新数组中。

### --question--

#### --text--

什么是数组解构（array destructuring）？

#### --distractors--

用于将数组的所有元素连接成一个字符串。

---

用于检查数组是否包含特定值。

---

用于移除数组的最后一个元素，并返回被移除的元素。

#### --answer--

用于从数组中提取值并以更简洁、可读的方式赋值给变量。

### --question--

#### --text--

`arr2` 变量将被赋予什么值？

```js
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];
console.log(arr2);
```

#### --distractors--

`[4, 5, 1, 2, 3]`

---

`[1, 2, [3, 4, 5]]`

---

`[1, 2, 3]`

#### --answer--

`[1, 2, 3, 4, 5]`

### --question--

#### --text--

以下代码会在控制台输出什么？

```js
const colors = ["red", "blue", "green", "yellow"];
colors.splice(1, 2, "purple");
console.log(colors);
```

#### --distractors--

`["red", "blue", "green", "yellow"]`

---

`["red", "blue", "yellow"]`

---

`["red", "yellow"]`

#### --answer--

`["red", "purple", "yellow"]`

### --question--

#### --text--

`slicedArr` 变量将被赋予什么值？

```js
const arr = ["apple", "banana", "cherry", "date"];
const slicedArr = arr.slice(1, 3);
console.log(slicedArr);
```

#### --distractors--

`["apple", "banana"]`

---

`["cherry", "date"]`

---

`["apple", "cherry"]`

#### --answer--

`["banana", "cherry"]`

### --question--

#### --text--

哪个方法返回数组中给定元素的第一个索引？

#### --distractors--

`firstIndex()`

---

`lastIndex()`

---

`searchIndex()`

#### --answer--

`indexOf()`

### --question--

#### --text--

哪个方法用于移除数组的第一个元素，并返回被移除的元素？

#### --distractors--

`pop()`

---

`slice()`

---

`splice()`

#### --answer--

`shift()`

### --question--

#### --text--

`concat()` 方法的作用是什么？

#### --distractors--

将数组元素连接成一个字符串。

---

向数组开头添加一个元素。

---

从数组中移除一个元素。

#### --answer--

将两个数组合并为一个新数组。

### --question--

#### --text--

以下代码的输出是什么？

```js
const fruits = ["apple", "banana", "cherry", "apple", "orange"];

fruits.splice(0, 1);

console.log(fruits);
```

#### --distractors--

`["apple", "banana", "cherry", "apple", "orange"]`

---

`["apple", "banana", "cherry"]`

---

`["cherry", 'apple']`

#### --answer--

`["banana", "cherry", "apple", "orange"]`

### --question--

#### --text--

`includes()` 方法的作用是什么？

#### --distractors--

用于将字符串分割为子字符串数组。

---

用于将数组的所有元素连接成一个字符串。

---

用于在数组的任意位置添加或删除元素。

#### --answer--

用于检查数组是否包含特定值。

### --question--

#### --text--

以下哪个方法用于原地反转数组？

#### --distractors--

`reversed()`

---

`reverseArr()`

---

`reversing()`

#### --answer--

`reverse()`

### --question--

#### --text--

什么是二维数组？

#### --distractors--

只包含对象字面量的数组。

---

长度固定的数组。

---

浮点数数组。

#### --answer--

数组的数组。

### --question--

#### --text--

关于数组的 `indexOf()` 方法，以下哪项是正确的？

#### --distractors--

它总是返回元素的最后一次出现。

---

如果找不到元素会抛出错误。

---

要求数组必须排序。

#### --answer--

如果找不到元素，则返回 `-1`。

### --question--

#### --text--

以下哪一个不是数组方法？

#### --distractors--

`includes()`

---

`pop()`

---

`push()`

#### --answer--

`keys()`

### --question--

#### --text--

以下代码的输出是什么？

```js
const arr = ["o", "l", "l", "e", "h"];
console.log(arr.join(""));
```

#### --distractors--

`["o", "l", "l", "e", "h"]`

---

`"hello"`

---

`undefined`

#### --answer--

`"olleh"`

### --question--

#### --text--

对空数组使用 `shift()` 方法会得到什么结果？

#### --distractors--

`TypeError`

---

`[]`

---

`null`

#### --answer--

`undefined`

### --question--

#### --text--

哪个方法会返回一个新数组，而不会改变原数组？

#### --distractors--

`shift()`

---

`pop()`

---

`push()`

#### --answer--

`slice()`
