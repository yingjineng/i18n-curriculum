---
id: 5a24c314108439a4d403615a
title: Remover um item de um array
challengeType: 6
forumTopicId: 301447
dashedName: remove-an-item-from-an-array
---

# --description--

Time to practice removing items from an array. The spread operator can be used here as well. Other useful JavaScript methods include `slice()` and `concat()`.

# --instructions--

O reducer e o criador de ação foram modificados para remover um item de um array com base no índice do item. Termine de escrever o reducer para que um novo array de state seja retornado com o item no índice especificado removido.

# --hints--

A store do Redux deve existir e inicializar com um estado igual a `[0,1,2,3,4,5]`

```js
const initialState = store.getState();
assert.isArray(initialState) 
assert.deepEqual(initialState, [0, 1, 2, 3, 4, 5])
```

`removeItem` e `immutableReducer` devem ser funções.

```js
assert(
  typeof removeItem === 'function' && typeof immutableReducer === 'function'
);
```

Despachar o criador de ação `removeItem` deve remover itens do state e NÃO deve modificar o state.

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
