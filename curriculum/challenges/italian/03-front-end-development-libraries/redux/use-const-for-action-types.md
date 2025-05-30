---
id: 5a24c314108439a4d4036152
title: Usare const per i tipi di azione
challengeType: 6
forumTopicId: 301450
dashedName: use-const-for-action-types
---

# --description--

A common practice when working with Redux is to assign action types as read-only constants, then reference these constants wherever they are used. You can refactor the code you're working with to write the action types as `const` declarations.

# --instructions--

Dichiara `LOGIN` e `LOGOUT` come valori `const` e assegnali rispettivamente alle stringhe `'LOGIN'` e `'LOGOUT'`. Quindi, modifica `authReducer()` e i creatori di azione in modo che facciano riferimento a queste costanti invece che ai valori stringa.

**Nota:** È una convenzione generale scrivere le costanti tutte in maiuscolo e questa è la pratica standard anche in Redux.

# --hints--

Chiamando la funzione `loginUser` dovrebbe essere restituito un oggetto con la proprietà `type` impostata alla stringa `LOGIN`.

```js
assert(loginUser().type === 'LOGIN');
```

Chiamando la funzione `logoutUser` dovrebbe essere restituito un oggetto con la proprietà `type` impostata alla stringa `LOGOUT`.

```js
assert(logoutUser().type === 'LOGOUT');
```

Lo store dovrebbe essere inizializzato con un oggetto con proprietà `login` impostata su `false`.

```js
assert(store.getState().authenticated === false);
```

Il dispatch di `loginUser` dovrebbe impostare a `true` la proprietà `login` nello stato dello store.

```js
assert(
  (function () {
    const initialState = store.getState();
    store.dispatch(loginUser());
    const afterLogin = store.getState();
    return (
      initialState.authenticated === false && afterLogin.authenticated === true
    );
  })()
);
```

Il dispatch di `logoutUser` dovrebbe impostare a `false` la proprietà `login` nello stato dello store.

```js
assert(
  (function () {
    store.dispatch(loginUser());
    const loggedIn = store.getState();
    store.dispatch(logoutUser());
    const afterLogout = store.getState();
    return (
      loggedIn.authenticated === true && afterLogout.authenticated === false
    );
  })()
);
```

La funzione `authReducer` dovrebbe gestire più tipi di azione con un'istruzione switch.

```js
assert(
    (function () {
      return (
        typeof authReducer === 'function' &&
        code.toString().includes('switch') &&
        code.toString().includes('case') &&
        code.toString().includes('default')
      );
    })()
  );
```

`LOGIN` e `LOGOUT` dovrebbero essere dichiarati come valori `const` e dovrebbero essere assegnate loro le stringhe `LOGIN` e `LOGOUT`.

```js
const noWhiteSpace = __helpers.removeWhiteSpace(code);
assert(LOGIN === 'LOGIN' && LOGOUT === 'LOGOUT')
assert(noWhiteSpace.includes('const'))
```

I creatori di azioni e il reducer dovrebbero fare riferimento alle costanti `LOGIN` e `LOGOUT`.

```js
  assert(
    (function () {
      const noWhiteSpace = __helpers.removeWhiteSpace(
        code.toString()
      );
      return (
        noWhiteSpace.includes('caseLOGIN:') &&
        noWhiteSpace.includes('caseLOGOUT:') &&
        noWhiteSpace.includes('type:LOGIN') &&
        noWhiteSpace.includes('type:LOGOUT')
      );
    })()
  );
```

# --seed--

## --seed-contents--

```js


const defaultState = {
  authenticated: false
};

const authReducer = (state = defaultState, action) => {

  switch (action.type) {
    case 'LOGIN': 
      return {
        authenticated: true
      }
    case 'LOGOUT': 
      return {
        authenticated: false
      }

    default:
      return state;

  }

};

const store = Redux.createStore(authReducer);

const loginUser = () => {
  return {
    type: 'LOGIN'
  }
};

const logoutUser = () => {
  return {
    type: 'LOGOUT'
  }
};
```

# --solutions--

```js
const LOGIN = 'LOGIN';
const LOGOUT = 'LOGOUT';

const defaultState = {
  authenticated: false
};

const authReducer = (state = defaultState, action) => {

  switch (action.type) {

    case LOGIN:
      return {
        authenticated: true
      }

    case LOGOUT:
      return {
        authenticated: false
      }

    default:
      return state;

  }

};

const store = Redux.createStore(authReducer);

const loginUser = () => {
  return {
    type: LOGIN
  }
};

const logoutUser = () => {
  return {
    type: LOGOUT
  }
};
```
