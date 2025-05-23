---
id: 5a24c314108439a4d403615b
title: Ein Objekt mit Object.assign kopieren
challengeType: 6
forumTopicId: 301437
dashedName: copy-an-object-with-object-assign
---

# --description--

The last several challenges worked with arrays, but there are ways to help enforce state immutability when state is an `object`, too. A useful tool for handling objects is the `Object.assign()` utility. `Object.assign()` takes a target object and source objects and maps properties from the source objects to the target object. Any matching properties are overwritten by properties in the source objects. This behavior is commonly used to make shallow copies of objects by passing an empty object as the first argument followed by the object(s) you want to copy. Hier ist ein Beispiel:

```js
const newObject = Object.assign({}, obj1, obj2);
```

Dadurch wird `newObject` als neues `object` erstellt, das die Eigenschaften enthält, die derzeit in `obj1` und `obj2` existieren.

# --instructions--

Der Redux-Zustand und die Actions wurden geändert, um ein `object` für den `state` zu verwenden. Bearbeite den Code, um ein neues `state`-Objekt für Actions mit dem Typ `ONLINE` zurückzugeben, das die `status`-Eigenschaft auf den String `online` setzt. Versuche, `Object.assign()` zu verwenden, um diese Aufgabe zu lösen.

# --hints--

Der Redux-Store sollte existieren und mit einem Zustand initialisiert werden, der dem `defaultState`-Objekt entspricht, das in Zeile 1 deklariert wurde.

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

`wakeUp` und `immutableReducer` sollten beide Funktionen sein.

```js
assert(typeof wakeUp === 'function' && typeof immutableReducer === 'function');
```

Das Senden einer Aktion vom Typ `ONLINE` sollte die Eigenschaft `status` im Zustand auf `online` aktualisieren und sollte den Zustand NICHT verändern.

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

`Object.assign` sollte verwendet werden, um einen neuen Zustand zurückzugeben.

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
