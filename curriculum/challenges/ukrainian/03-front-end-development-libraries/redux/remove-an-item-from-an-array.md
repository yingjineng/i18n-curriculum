---
id: 5a24c314108439a4d403615a
title: Видаліть елемент з масиву
challengeType: 6
forumTopicId: 301447
dashedName: remove-an-item-from-an-array
---

# --description--

Time to practice removing items from an array. The spread operator can be used here as well. Other useful JavaScript methods include `slice()` and `concat()`.

# --instructions--

Редюсер та автор дії були змінені, щоб вилучати елемент з масиву на основі індексу елемента. Допишіть редюсер, щоб масив нового стану повернувся з елементом на основі видаленого індексу.

# --hints--

Сховище Redux має існувати й ініціалізуватися станом, який дорівнює `[0,1,2,3,4,5]`

```js
const initialState = store.getState();
assert.isArray(initialState) 
assert.deepEqual(initialState, [0, 1, 2, 3, 4, 5])
```

`removeItem` та `immutableReducer` мають бути функціями.

```js
assert(
  typeof removeItem === 'function' && typeof immutableReducer === 'function'
);
```

Відправлення автора дії `removeItem` має видалити елементи зі стану та НЕ змінювати стан.

```js
const initialState = store.getState();
const isFrozen = !!DeepFreeze(initialState);
store.dispatch(removeItem(3));
const state_1 = store.getState();
store.dispatch(removeItem(2));
const state_2 = store.getState();
store.dispatch(removeItem(0));
store.dispatch(removeItem(0));
store.dispatch(removeItem(0));
const state_3 = store.getState();

assert(isFrozen)
assert.deepEqual(state_1, [0, 1, 2, 4, 5]) 
assert.deepEqual(state_2, [0, 1, 4, 5]) 
assert.deepEqual(state_3, [5])

```

# --seed--

## --seed-contents--

```js
const immutableReducer = (state = [0,1,2,3,4,5], action) => {
  switch(action.type) {
    case 'REMOVE_ITEM':
      // Don't mutate state here or the tests will fail
      return
    default:
      return state;
  }
};

const removeItem = (index) => {
  return {
    type: 'REMOVE_ITEM',
    index
  }
}

const store = Redux.createStore(immutableReducer);
```

# --solutions--

```js
const immutableReducer = (state = [0,1,2,3,4,5], action) => {
  switch(action.type) {
    case 'REMOVE_ITEM':
      return [
        ...state.slice(0, action.index),
        ...state.slice(action.index + 1)
      ];
    default:
      return state;
  }
};

const removeItem = (index) => {
  return {
    type: 'REMOVE_ITEM',
    index
  }
}

const store = Redux.createStore(immutableReducer);
```
