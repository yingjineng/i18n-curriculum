---
id: 67d1ad82cff954a854bcbcaa
title: 什么是 Prop Drilling？
challengeType: 11
videoId: 83LkOesFkWI
dashedName: what-is-prop-drilling
---

# --description--

观看视频或阅读文字稿并回答下方问题。

# --transcript--

什么是 prop drilling？

Prop drilling 是 React 应用中最基础的状态管理方式。它看起来很简单，但很快就会变得混乱，并且很难扩展。

让我们看看什么是 prop drilling、它为什么是个问题，以及当应用变大时有哪些更好的替代方案。

Prop drilling 指的是将 props 从父组件一层层传递到深层嵌套的子组件，即使有些中间组件并不需要这些 props。

举个例子，假设你有三个组件：`Parent`、`Child` 和 `Grandchild`。如果你想在 `Grandchild` 组件中使用一些数据，而这些数据在 `Parent` 组件中，你需要先把它从 `Parent` 传给 `Child`，再从 `Child` 传给 `Grandchild`。

如果数据在更高层的组件中，还需要先传到 `Parent` 组件。

这里，我想展示的数据是字符串 `Hello, Prop Drilling!`，它被赋值给根组件 `App` 里的 `greeting` 变量：

```jsx
import "./App.css";
import Parent from "./Parent";

function App() {
  const greeting = "Hello, Prop Drilling!";

  return <Parent greeting={greeting} />;
}

export default App;
```

你可以看到，`Parent` 组件也通过 `greeting` prop 接收了这个变量。下面是 `Parent` 组件把它作为 `greeting` prop 传递给 `Child` 组件：

```jsx
import Child from "./Child";

const Parent = ({ greeting }) => {
  return <Child greeting={greeting} />;
};

export default Parent;
```

接下来是 `Child` 组件把它传递给 `Grandchild` 组件：

```jsx
import Grandchild from "./Grandchild";

const Child = ({ greeting }) => {
  return <Grandchild greeting={greeting} />;
};

export default Child;
```

最后，`Grandchild` 组件接收到 `greeting`，并将其作为 `h1` 元素的内容：

```jsx
const Grandchild = ({ greeting }) => {
  return <h1>{greeting}</h1>;
};

export default Grandchild;
```

在浏览器中，你会看到页面上有一个 `h1` 元素，内容是 `Hello, Prop Drilling!`。

一开始，prop drilling 似乎没什么大问题。但随着应用变大，代码会变得难以理解、调试和维护。

如果你需要传递 props，尽量把它们都放在一个父组件中。这种集中管理所有必要数据的方法叫做“单一数据源”（single source of truth）。

比如，你想在 `Grandchild` 组件中同时使用 `greeting` 和一个新的 `response`。既然 `greeting` 已经在 `App` 组件里了，把 `response` 也放在这里，并一起往下传递：

```jsx
function App() {
  const greeting = "Hello, Prop Drilling!";
  const response = "I'm not here to play!";

  return <Parent greeting={greeting} response={response} />;
}

const Parent = ({ greeting, response }) => {
  return <Child greeting={greeting} response={response} />;
};

const Child = ({ greeting, response }) => {
  return <Grandchild greeting={greeting} response={response} />;
};

const Grandchild = ({ greeting, response }) => {
  return (
    <>
      <h1>{greeting}</h1>
      <h2>{response}</h2>
    </>
  );
};

export default App;
```

在浏览器中，你会看到页面上有一个 `h1` 元素，内容是 `Hello, Prop Drilling!`，还有一个 `h2` 元素，内容是 `I'm not here to play!`。

为了避免 prop drilling，尤其是在大型复杂应用中，可以考虑使用 Context API 或状态管理库，比如 Redux、Redux Toolkit、Zustand、Recoil 等。

你将在后续课程中学习这些内容。

# --questions--

## --text--

一个 prop 如何从父组件流向孙组件？

## --answers--

在孙组件内部定义该 prop。

### --feedback--

prop 必须先经过子组件才能到达孙组件。

---

通过先从父组件传给子组件，再从子组件传给孙组件。

---

通过 `useEffect` 钩子动态获取该 prop。

### --feedback--

prop 必须先经过子组件才能到达孙组件。

---

在孙组件中使用 `useState` 钩子。

### --feedback--

prop 必须先经过子组件才能到达孙组件。

## --video-solution--

2

## --text--

什么是 React 中的 prop drilling？

## --answers--

只把 props 直接传给需要它们的组件。

### --feedback--

prop drilling 指的是 props 被不必要地传递到多层组件。

---

使用 context 在组件间共享状态。

### --feedback--

prop drilling 指的是 props 被不必要地传递到多层组件。

---

从父组件传递 props 到深层嵌套的子组件。

---

通过 hooks 深入组件状态。

### --feedback--

prop drilling 指的是 props 被不必要地传递到多层组件。

## --video-solution--

3

## --text--

为什么 prop drilling 在大型应用中被认为是个问题？

## --answers--

它让状态管理更容易。

### --feedback--

太多 props 在多个组件间传递会让代码变得混乱。

---

它通过减少重新渲染提升了性能。

### --feedback--

太多 props 在多个组件间传递会让代码变得混乱。

---

它让代码更难阅读、调试和维护。

---

它消除了对状态管理库的需求。

### --feedback--

太多 props 在多个组件间传递会让代码变得混乱。

## --video-solution--

3

