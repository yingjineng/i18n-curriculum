---
id: 66edcdd18a4ef8df16e6bb7e
title: JavaScript 高阶函数测验
challengeType: 8
dashedName: quiz-javascript-higher-order-functions
---

# --description--

要通过本测验，你必须正确回答以下 20 道题中的至少 18 道。

# --quizzes--

## --quiz--

### --question--

#### --text--

以下关于 JavaScript 高阶函数的说法，哪一项是不正确的？

#### --distractors--

高阶函数通过实现函数式编程技术，可以极大地提升代码的可读性和可维护性。

---

像 map、filter 和 reduce 这样的高阶函数是数组操作的强大工具，但它们并非函数式编程独有。

---

高阶函数可能会增加代码理解的复杂性，但也能带来更简洁和富有表现力的解决方案。

#### --answer--

所有 JavaScript 函数，包括那些不接收或返回其他函数的，都可以被归类为高阶函数。

### --question--

#### --text--

在高阶函数的语境下，什么是工厂函数（factory function）？

#### --distractors--

一个创建新变量的函数。

---

一个只适用于字符串的函数。

---

一个自动生成代码注释的函数。

#### --answer--

一个根据特定参数返回新函数的函数

### --question--

#### --text--

代码执行后，`forEachRes` 和 `mapRes` 的值分别是多少？

```js
const numbers = [1, 1, 1, 1, 1];
let sum = 0;
const forEachRes = numbers.forEach(num => {
  return (sum += num);
});
const mapRes = numbers.map(num => {
  return (sum += num);
});
```

#### --distractors--

`forEachRes` 是 `undefined`，`mapRes` 是 `[1,2,3,4,5]`

---

`forEachRes` 是 `0`，`mapRes` 是 `[1,2,3,4,5]`

---

`forEachRes` 是 `5`，`mapRes` 是 `[1,2,3,4,5]`

#### --answer--

`forEachRes` 是 `undefined`，`mapRes` 是 `[6,7,8,9,10]`

### --question--

#### --text--

以下代码的结果是什么？

```js
[, undefined, 'a', 'b', { 20: 5 }].sort();
```

#### --distractors--

数组包含不支持排序的元素，因此报错。

---

未提供回调函数，因此报错。

---

```js
[empty, 'a', 'b', undefined, { '20': 5 }]
```

#### --answer--

```js
[{ '20': 5 }, 'a', 'b', undefined, empty]
```

### --question--

#### --text--

以下哪项描述了 JavaScript 中的回调函数？

#### --distractors--

声明后立即调用的函数。

---

以特定上下文调用的函数。

---

返回另一个函数的函数。

#### --answer--

作为参数传递给另一个函数，由该函数逻辑执行的函数。

### --question--

#### --text--

在数组上使用 `reduce()` 方法的结果是什么？

#### --distractors--

一个布尔值，表示是否有元素满足条件。

---

一个所有元素都被回调函数处理后的新数组。

---

一个布尔值数组。

#### --answer--

结果取决于累加器的初始值和回调函数。

### --question--

#### --text--

如果在数值排序时未提供比较函数，`sort()` 方法的行为是什么？

#### --distractors--

它会用 `null` 填充空位。

---

它返回一个包含特殊字符的数组。

---

它会将数组倒序排列。

#### --answer--

它会将数组元素按 UTF-16 码元以字符串方式排序。

### --question--

#### --text--

JavaScript 中 `some()` 方法的作用是什么？

#### --distractors--

创建一个新数组，将函数应用于每个元素后的结果组成。

---

遍历数组但不产生结果。

---

根据回调函数将数组归约为单个值。

#### --answer--

判断数组中是否有元素通过指定测试。

### --question--

#### --text--

以下哪项是方法链式调用的有效示例？

#### --distractors--

```js
Math.random();
```

---

```js
array.push(1).pop();
```

---

```js
console.log('Hello');
```

#### --answer--

```js
str.toLowerCase().trim().replace(' ', '_');
```

### --question--

#### --text--

以下代码的输出是什么？

```js
let numbers = [2, 4, 8, 10];

numbers.forEach(function(number) {
    console.log(number % 2);
});
```

#### --distractors--

`2 4 8 10`

---

`null null null null`

---

`1 2 4 5`

#### --answer--

`0 0 0 0`

### --question--

#### --text--

方法链式调用的一个好处是什么？

#### --distractors--

它本质上通过减少函数执行时间来优化性能。

---

它消除了临时变量的需求，但有时可能增加内存使用。

---

它让错误处理和调试变得更直接。

#### --answer--

它通过允许在单个表达式中进行多次操作，简化语法并提升代码可读性。

### --question--

#### --text--

如何使用 `sort` 方法按对象的某个属性对对象数组进行排序？

#### --distractors--

`sort` 方法无法对对象排序。

---

排序后使用 `reverse` 方法。

---

将对象转换为字符串后排序。

#### --answer--

使用比较函数比较属性值。

### --question--

#### --text--

在方法链式调用中，为了增强代码清晰度和调试性，常见做法是什么？

#### --distractors--

减少链中的方法数量。

---

避免链式调用只返回原始值的方法。

---

只使用内置方法。

#### --answer--

将较长的链拆分为多个步骤。

### --question--

#### --text--

过度使用方法链式调用可能带来的潜在问题是什么？

#### --distractors--

会让代码运行变慢。

---

无法添加注释。

---

会让文件体积变大。

#### --answer--

可能让代码更难调试。

### --question--

#### --text--

要判断数组中所有元素是否都是字符串，应使用哪个方法？

#### --distractors--

`some()`

---

`everyInstance()`

---

`filter()`

#### --answer--

`every()`

### --question--

#### --text--

以下代码执行后，`originalArray` 的值是多少？

```js
const originalArray = [{ id: 1 }, { id: 2 }, { id: 3 }];
const filteredArray = originalArray.filter(item => item.id > 1);
filteredArray[0].id = 4;
```

#### --distractors--

`[{ id: 1 }, { id: 2 }, { id: 3 }]`

---

`[{ id: 1 }]`

---

`[{ id: 4 }, { id: 2 }, { id: 3 }]`

#### --answer--

`[{ id: 1 }, { id: 4 }, { id: 3 }]`
### --question--

#### --text--

以下代码的输出是什么？

```js
const multiply = (a) => (b) => a * b;
const operations = [multiply(2), multiply(3)];
const result = operations.reduce((acc, fn) => fn(acc), 5);

console.log(result);
```

#### --distractors--

`10`

---

`100`

---

`20`

#### --answer--

`30`

### --question--

#### --text--

在 `reduce()` 方法中提供初始值的主要目的是什么？

#### --distractors--

设置数组的长度。

---

限制迭代次数。

---

指定函数的返回类型。

#### --answer--

定义累加器的起始值。

### --question--

#### --text--

`map` 方法可以用于非数组对象吗？

#### --distractors--

可以，对任何对象都适用。

---

可以，但仅适用于具有数字属性的对象。

---

取决于 JavaScript 版本。

#### --answer--

不可以，它专为数组设计。

### --question--

#### --text--

JavaScript 中 `map` 方法的主要作用是什么？

#### --distractors--

对数组排序并返回一个保持原顺序的新数组。

---

根据条件过滤数组元素并移除或添加元素。

---

查找数组中特定元素并返回其索引及元素。

#### --answer--

创建一个新数组，包含对原数组每个元素调用指定函数后的结果。

