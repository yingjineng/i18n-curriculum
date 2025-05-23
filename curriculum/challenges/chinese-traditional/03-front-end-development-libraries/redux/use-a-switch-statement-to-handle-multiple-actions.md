---
id: 5a24c314108439a4d4036151
title: 使用 Switch 語句處理多個 Actions
challengeType: 6
forumTopicId: 301449
dashedName: use-a-switch-statement-to-handle-multiple-actions
---

# --description--

You can tell the Redux store how to handle multiple action types. Say you are managing user authentication in your Redux store. You want to have a state representation for when users are logged in and when they are logged out. You represent this with a single state object with the property `authenticated`. You also need action creators that create actions corresponding to user login and user logout, along with the action objects themselves.

# --instructions--

代碼編輯器爲你創建了 store、actions、action creators。 通過編寫 `reducer` 函數來處理多個身份驗證操作。 可以在 `reducer` 裏通過使用 JavaScript 的 `switch` 來響應不同的 action 事件。 這是編寫 Redux reducers 的標準模式。 switch 語句應該切換 `action.type` 並返回適當的身份驗證狀態。

**注意：** 此時，不要擔心 state 的不變性，因爲在這個示例中它很小而且很簡單。 所以對於每個操作都可以返回一個新對象，比如 `{authenticated: true}`。 另外，不要忘記在 switch 語句中寫一個 `default` case，返回當前的 `state`。 這是很重要的，因爲當程序有多個 reducer，當每一個 action 被 dispatch 時它們都會運行，即使 action 與該 reducer 無關。 在這種情況下，你要確保返回當前的 `state`

# --hints--

調用函數 `loginUser` 應該返回一個 type 屬性設置爲字符串 `LOGIN` 的對象。

```js
assert(loginUser().type === 'LOGIN');
```

調用函數 `logoutUser` 應該返回一個 type 屬性設置爲字符串 `LOGOUT` 的對象。

```js
assert(logoutUser().type === 'LOGOUT');
```

store 應該設置一個 `authenticated` 屬性設置爲 `false` 的初始化對象。

```js
assert(store.getState().authenticated === false);
```

dispatch `loginUser`應該將 store 中的 state 的 `authenticated` 值更新爲 `true`。

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

dispatch `logoutUser` 應該將 store 中的 state 的 `authenticated` 值更新爲 `false`。

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

`authReducer` 函數應該使用 `switch` 語句處理多個 action 類型。

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
