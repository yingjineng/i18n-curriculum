---
id: 5a24c314108439a4d403615b
title: Скопіюйте об’єкт за допомогою Object.assign
challengeType: 6
forumTopicId: 301437
dashedName: copy-an-object-with-object-assign
---

# --description--

The last several challenges worked with arrays, but there are ways to help enforce state immutability when state is an `object`, too. A useful tool for handling objects is the `Object.assign()` utility. `Object.assign()` takes a target object and source objects and maps properties from the source objects to the target object. Any matching properties are overwritten by properties in the source objects. This behavior is commonly used to make shallow copies of objects by passing an empty object as the first argument followed by the object(s) you want to copy. Ось приклад:

```js
const newObject = Object.assign({}, obj1, obj2);
```

Це створює `newObject` як новий об’єкт, що містить властивості, які вже існують в `obj1` та `obj2`.

# --instructions--

Стан та дії Redux були змінені, щоб обробити `object` для `state`. Відредагуйте код, щоб повернути новий об’єкт стану для дій типу `ONLINE`, що встановлює властивість `status` на рядок `online`. Спробуйте використати `Object.assign()`, щоб виконати це завдання.

# --hints--

Сховище Redux має існувати та ініціалізуватися станом, що дорівнює об’єкту `defaultState`, оголошеному в рядку 1.

```js
const expectedState = {
  user: 'CamperBot',
  status: 'offline',
  friends: '732,982',
  community: 'freeCodeCamp'
};
const initialState = store.getState();
assert.deepEqual(expectedState, initialState);
```

`wakeUp` та `immutableReducer` мають бути функціями.

```js
assert(typeof wakeUp === 'function' && typeof immutableReducer === 'function');
```

Відправлення дії типу `ONLINE` має оновити властивість `status` в стані на `online` та НЕ змінювати стан.

```js

const initialState = store.getState();
const isFrozen = !!DeepFreeze(initialState);
store.dispatch({ type: 'ONLINE' });
const finalState = store.getState();
const expectedState = {
  user: 'CamperBot',
  status: 'online',
  friends: '732,982',
  community: 'freeCodeCamp'
};
assert(isFrozen);
assert.deepEqual(finalState, expectedState);
```

Використайте `Object.assign`, щоб повернути новий стан.

```js
assert(code.includes('Object.assign'));
```

# --seed--

## --seed-contents--

```js
const defaultState = {
  user: 'CamperBot',
  status: 'offline',
  friends: '732,982',
  community: 'freeCodeCamp'
};

const immutableReducer = (state = defaultState, action) => {
  switch(action.type) {
    case 'ONLINE':
      // Don't mutate state here or the tests will fail
      return
    default:
      return state;
  }
};

const wakeUp = () => {
  return {
    type: 'ONLINE'
  }
};

const store = Redux.createStore(immutableReducer);
```

# --solutions--

```js
const defaultState = {
  user: 'CamperBot',
  status: 'offline',
  friends: '732,982',
  community: 'freeCodeCamp'
};

const immutableReducer = (state = defaultState, action) => {
  switch(action.type) {
    case 'ONLINE':
      return Object.assign({}, state, {
        status: 'online'
      });
    default:
      return state;
  }
};

const wakeUp = () => {
  return {
    type: 'ONLINE'
  }
};

const store = Redux.createStore(immutableReducer);
```
