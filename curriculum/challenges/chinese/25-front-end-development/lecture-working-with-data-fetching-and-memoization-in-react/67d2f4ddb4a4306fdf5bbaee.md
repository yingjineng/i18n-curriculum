---
id: 67d2f4ddb4a4306fdf5bbaee
title: 什么是记忆化（Memoization），useMemo Hook 如何工作？
challengeType: 11
videoId: 2X7LD_6P4eI
dashedName: what-is-memoization-and-how-does-the-usememo-hook-work
---

# --description--

观看视频或阅读文字稿并回答下方问题。

# --transcript--

什么是记忆化（memoization），以及 `useMemo` hook 是如何工作的？

随着你的 React 应用变得越来越大，不必要的重新渲染和昂贵的计算会拖慢性能，导致 UI 更新变慢和资源使用增加。

这在具有复杂状态管理、大型列表、需要大量计算的函数以及许多拥有同一个父组件的组件的应用中尤其突出。

因此，我们需要优化 React 应用的性能，减少重复计算，确保交互更加流畅。

React 通过一种叫做记忆化（memoization）的过程来解决这个问题。这是一种缓存值和函数以防止不必要重复计算的技术，从而让你的应用更快、更灵敏。

记忆化的定义是：一种优化技术，将昂贵函数调用的结果基于特定参数进行缓存（记住）。当再次传入相同参数时，直接返回缓存结果，而不是重新计算。

记忆化的过程如下：

- 存储函数调用的结果以及它们的输入参数。
- 在执行函数前，检查当前参数的结果是否已存在于缓存中。
- 如果存在，直接返回缓存结果，而不是再次计算。
- 如果不存在，计算结果，存入缓存，然后返回。

为了提升开发体验，React 提供了三种记忆化工具 —— `React.memo`（或 `memo`）、`useMemo` 和 `useCallback`。

你可能已经猜到，`useMemo` 和 `useCallback` 都是 hooks，而 `React.memo` 是一个组件包装器，也就是高阶函数（HOC）。

在下一讲中，我们会学习 `useCallback` hook 和 `React.memo` 的工作方式。

`useMemo` 用于记忆化计算值，而 `useCallback` 用于记忆化函数引用。

如果你在疑惑什么是计算值和函数引用，计算值指的是函数执行后的结果，而函数引用是指向函数的指针——即内存中的函数对象。

我们先来看一下 `useMemo` hook 的基本用法：

```js
const memoizedValue = useMemo(
 function () {
  return computeExpensiveValue(a, b);
 },
 [a, b]
);
```

你可以看到，只需要用 `useMemo` 包裹函数即可。

下面是一个 `ExpensiveSquare` 组件，它接收一个 `num` 属性并计算它的平方：

```js
function ExpensiveSquare({ num }) {
 function calculateSquare(n) {
  console.log("Calculating square...");
  return n * n;
 }

 const squared = calculateSquare(num);
 return (
  <p>
    Square of {num}: {squared}
  </p>
 );
}
export default ExpensiveSquare;
```

这是在 `App` 组件中使用 `ExpensiveSquare` 的例子：

```js
import { useState, useEffect } from "react";
import ExpensiveSquare from "./components/ExpensiveSquare";

function App() {
 const [timer, setTimer] = useState(0);
 const [num, setNum] = useState(0);

 useEffect(() => {
  const interval = setInterval(() => setTimer((c) => c + 1), 1000);
  return () => clearInterval(interval);
 }, []);

 return (
  <div>
    <h1>Timer: {timer} seconds gone</h1>
    <ExpensiveSquare num={num} />
    <button onClick={() => setNum((n) => n + 1)}>Increase Number</button>
  </div>
 );
}

export default App;
```

`useEffect` 中的 `timer` 每秒都会更新，这会导致 `calculateSquare` 每次都运行，即使你没有增加 `num` 状态变量。

为了解决这个问题，我们可以用 `useMemo` hook 包裹函数调用，并将 `num` 作为依赖项：

```js
// 导入 useMemo hook
import { useMemo } from "react";

function ExpensiveSquare({ num }) {
  function calculateSquare(n) {
   console.log("Calculating square...");
   return n * n;
  }

  // const squared = calculateSquare(num);
  // 用 useMemo 包裹函数调用
  const squared = useMemo(() => calculateSquare(num), [num]);

  return (
   <p>
    Square of {num}: {squared}
   </p>
  );
}

export default ExpensiveSquare;
```

这样可以确保函数被记忆化并缓存结果，只有当 `num` 变量变化时才会重新计算，而不是每次组件更新时都计算。

现在，`calculateSquare` 只会在初次渲染和 `num` 变化时运行，而不会因为 `timer` 变化而运行。

# --questions--

## --text--

React 中的记忆化（memoization）是什么？

## --answers--

一种缓存值和函数以防止不必要重复计算的技术。

---

一种让你管理组件状态更新以防止不必要重复计算的技术。

### --feedback--

它通过存储之前计算的结果来优化性能。

---

将虚拟 DOM 与实际 DOM 对比的过程。

### --feedback--

它通过存储之前计算的结果来优化性能。

---

在函数组件中处理副作用的方法。

### --feedback--

它通过存储之前计算的结果来优化性能。

## --video-solution--

1

## --text--

计算值（computed values）和函数引用（function references）有什么区别？

## --answers--

计算值是函数对象，函数引用是执行结果。

### --feedback--

一个是函数的输出，另一个只是指向函数的指针。

---

计算值是函数执行的结果，函数引用是内存中的函数对象。

---

计算值和函数引用是同一个东西。

### --feedback--

一个是函数的输出，另一个只是指向函数的指针。

---

函数引用存储计算值。

### --feedback--

一个是函数的输出，另一个只是指向函数的指针。

## --video-solution--

2

## --text--

以下哪一个不是 React 提供的记忆化工具？

## --answers--

`React.memo`

### --feedback--

记忆化工具关注于缓存值和函数，而这个选项用于处理副作用。

---

`useMemo`

### --feedback--

记忆化工具关注于缓存值和函数，而这个选项用于处理副作用。

---

`useCallback`

### --feedback--

记忆化工具关注于缓存值和函数，而这个选项用于处理副作用。

---

`useEffect`

### --feedback--

记忆化工具关注于缓存值和函数，而这个选项用于处理副作用。

## --video-solution--

4

