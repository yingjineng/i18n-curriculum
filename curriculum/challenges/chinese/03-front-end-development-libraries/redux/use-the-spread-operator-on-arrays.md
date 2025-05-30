---
id: 5a24c314108439a4d4036159
title: 在数组中使用扩展运算符
challengeType: 6
forumTopicId: 301452
dashedName: use-the-spread-operator-on-arrays
---

# --description--

One solution from ES6 to help enforce state immutability in Redux is the spread operator: `...`. The spread operator has a variety of applications, one of which is well-suited to the previous challenge of producing a new array from an existing array. This is relatively new, but commonly used syntax. For example, if you have an array `myArray` and write:

```js
let newArray = [...myArray];
```

`newArray` 现在是 `myArray` 的克隆。 两个数组仍然分别存在于内存中。 如果你执行像 `newArray.push(5)` 这样的变异， `myArray` 不会改变。 `...` 有效将 `myArray` 中的值*展开*到一个新数组中。 要克隆数组，但在新数组中添加其他值，可以编写 `[...myArray, 'new value']`。 这将返回一个由 `myArray` 中的值和字符串 `new value`（作为最后一个值）组成的新数组。 扩展语法可以像这样在数组组合中多次使用，但重要的是要注意它只是生成数组的浅拷贝副本。 也就是说，它只为一维数组提供不可变的数组操作。

# --instructions--

添加待办事项时，使用 spread 运算符返回新的状态副本。

# --hints--

Redux store 应该在代码编辑器中存在，并使用 `["Do not mutate state!"]` 进行状态初始化。

```js
assert(
  (function () {
    const initialState = store.getState();
    return (
      Array.isArray(initialState) === true &&
      initialState[0] === 'Do not mutate state!'
    );
  })()
);
```

`addToDo` 和 `immutableReducer` 都应该是函数。

```js
assert(typeof addToDo === 'function' && typeof immutableReducer === 'function');
```

在 Redux store 上 dispatch 一个类型为 `ADD_TO_DO` 的 aciton，应该添加一个 `todo` 项，并且不应该改变 state。

```js
const initialState = store.getState();
const isFrozen = !!DeepFreeze(initialState);
store.dispatch(addToDo('__TEST__TO__DO__'));
const finalState = store.getState();
const expectedState = ['Do not mutate state!', '__TEST__TO__DO__'];
assert(isFrozen)
assert.deepEqual(finalState, expectedState);
```

应使用扩展运算符返回新的 state。

```js
assert(code.includes('...state'));
```

# --seed--

## --seed-contents--

```js
const immutableReducer = (state = ['Do not mutate state!'], action) => {
  switch(action.type) {
    case 'ADD_TO_DO':
      // Don't mutate state here or the tests will fail
      return
    default:
      return state;
  }
};

const addToDo = (todo) => {
  return {
    type: 'ADD_TO_DO',
    todo
  }
}

const store = Redux.createStore(immutableReducer);
```

# --solutions--

```js
const immutableReducer = (state = ['Do not mutate state!'], action) => {
  switch(action.type) {
    case 'ADD_TO_DO':
      return [
        ...state,
        action.todo
      ];
    default:
      return state;
  }
};

const addToDo = (todo) => {
  return {
    type: 'ADD_TO_DO',
    todo
  }
}

const store = Redux.createStore(immutableReducer);
```
