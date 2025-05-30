---
id: 5a24c314108439a4d403614f
title: Ein Aktionsereignis auslösen
challengeType: 6
forumTopicId: 301442
dashedName: dispatch-an-action-event
---

# --description--

`dispatch` method is what you use to dispatch actions to the Redux store. Calling `store.dispatch()` and passing the value returned from an action creator sends an action back to the store.

Erinnere dich daran, dass Action Creators ein Objekt mit einer Typeigenschaft zurückgeben, die den Typ der aufgetretenen Action angibt. Dann sendet die Methode ein Aktionsobjekt an den Redux Store. Basierend auf dem Beispiel der vorherigen Aufgabe sind die folgenden Zeilen gleichwertig und senden beide die Aktion vom Typ `LOGIN`:

```js
store.dispatch(actionCreator());
store.dispatch({ type: 'LOGIN' });
```

# --instructions--

Der Redux Store im Code-Editor hat einen initialisierten Zustand, der ein Objekt mit einer `login`-Eigenschaft ist, das derzeit auf `false` gesetzt ist. Es gibt auch einen Action Creator namens `loginAction()`, der eine Aktion vom Typ `LOGIN` zurückgibt. Sende die `LOGIN`-Aktion an den Redux Store, indem du die Methode `dispatch` aufrufst und die mit `loginAction()` erstellte Aktion übergibst.

# --hints--

Der Aufruf der Funktion `loginAction` sollte ein Objekt zurückgeben, dessen Eigenschaft `type` auf den String `LOGIN` gesetzt ist.

```js
assert(loginAction().type === 'LOGIN');
```

Der Store sollte mit einem Objekt initialisiert werden, dessen Eigenschaft `login` auf `false` gesetzt ist.

```js
assert(store.getState().login === false);
```

Die Methode `store.dispatch()` sollte verwendet werden, um eine Aktion vom Typ `LOGIN` zu versenden.

```js
assert(
    (function () {
      let noWhiteSpace = code.replace(/\s/g, '');
      return (
        noWhiteSpace.includes('store.dispatch(loginAction())') ||
        noWhiteSpace.includes("store.dispatch({type: 'LOGIN'})") === true
      );
    })()
);
```

# --seed--

## --seed-contents--

```js
const store = Redux.createStore(
  (state = {login: false}) => state
);

const loginAction = () => {
  return {
    type: 'LOGIN'
  }
};

// Dispatch the action here:
```

# --solutions--

```js
const store = Redux.createStore(
  (state = {login: false}) => state
);

const loginAction = () => {
  return {
    type: 'LOGIN'
  }
};

store.dispatch(loginAction());
```
