---
id: 5a24c314108439a4d4036151
title: Usar um comando switch para lidar com várias ações
challengeType: 6
forumTopicId: 301449
dashedName: use-a-switch-statement-to-handle-multiple-actions
---

# --description--

You can tell the Redux store how to handle multiple action types. Say you are managing user authentication in your Redux store. You want to have a state representation for when users are logged in and when they are logged out. You represent this with a single state object with the property `authenticated`. You also need action creators that create actions corresponding to user login and user logout, along with the action objects themselves.

# --instructions--

O editor de código tem uma store, actions e criadores de actions configurados para você. Preencha a função `reducer` para lidar com várias ações de autenticação. Use a instrução do JavaScript `switch` no `reducer` para responder a diferentes eventos de ação. Este é um padrão para escrever reducers do Redux. O comando switch deve mudar acima de `action.type` e retornar o estado de autenticação apropriado.

**Observação:** neste ponto, não se preocupe com imutabilidade do state, já que é pequeno e simples neste exemplo. Para cada ação, você pode retornar um novo objeto — por exemplo, `{authenticated: true}`. Além disso, não se esqueça de escrever um caso `default` na sua instrução switch que retorna o `state`atual. Isso é importante porque, como seu aplicativo tem vários redutores, eles são executados toda vez que uma ação é enviada, mesmo quando a ação não é relacionada a esse reducer. Nesses casos, você quer garantir que você retorna o `state` atual.

# --hints--

Chamar a função `loginUser` deve retornar um objeto com a propriedade type definida para a string `LOGIN`.

```js
assert(loginUser().type === 'LOGIN');
```

Chamar a função `logoutUser` deve retornar um objeto com a propriedade type definida para a string `LOGOUT`.

```js
assert(logoutUser().type === 'LOGOUT');
```

A store deve ser inicializada com um objeto com a propriedade `authenticated` definido como `false`.

```js
assert(store.getState().authenticated === false);
```

Despachar `loginUser` deve atualizar a propriedade `authenticated` no state da store para `true`.

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

Despachar `logoutUser` deve atualizar a propriedade `authenticated` no state da store para `false`.

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

A função `authReducer` deve lidar com vários tipos de ação com um comando `switch`.

```js
assert(
    code.toString().includes('switch') &&
      code.toString().includes('case') &&
      code.toString().includes('default')
  );
```

# --seed--

## --seed-contents--

```js
const defaultState = {
  authenticated: false
};

const authReducer = (state = defaultState, action) => {
  // Change code below this line

  // Change code above this line
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
