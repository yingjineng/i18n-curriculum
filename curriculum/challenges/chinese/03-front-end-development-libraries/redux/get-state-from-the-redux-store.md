---
id: 5a24c314108439a4d403614c
title: 从 Redux Store 获取状态
challengeType: 6
forumTopicId: 301443
dashedName: get-state-from-the-redux-store
---

# --description--

The Redux store object provides several methods that allow you to interact with it. For example, you can retrieve the current `state` held in the Redux store object with the `getState()` method.

# --instructions--

在代码编辑器中可以将上一个挑战中的代码更简洁地重写， 在 `store` 中使用 `store.getState()` 检索`state`，并将其分配给新变量 `currentState`。

# --hints--

Redux store 的 state 应该有一个初始值 5。

```js
assert(store.getState() === 5);
```

应该存在一个变量 `currentState`，并为其分配 Redux store 的当前状态。

```js
assert(currentState === 5 && code.includes('store.getState()'));
```

# --seed--

## --seed-contents--

```js
const store = Redux.createStore(
  (state = 5) => state
);

// Change code below this line
```

# --solutions--

```js
const store = Redux.createStore(
  (state = 5) => state
);

// Change code below this line
const currentState = store.getState();
```
