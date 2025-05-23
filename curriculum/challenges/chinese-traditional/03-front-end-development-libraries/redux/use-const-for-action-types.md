---
id: 5a24c314108439a4d4036152
title: 使用 const 聲明 Action Types
challengeType: 6
forumTopicId: 301450
dashedName: use-const-for-action-types
---

# --description--

A common practice when working with Redux is to assign action types as read-only constants, then reference these constants wherever they are used. You can refactor the code you're working with to write the action types as `const` declarations.

# --instructions--

將 `LOGIN` 和 `LOGOUT` 聲明爲 `const` 的值，併爲它們分別分配字符串 `'LOGIN'` 和 `'LOGOUT'`。 然後，編輯 `authReducer()` 和 action creators 來引用這些常量而不是字符串值。

**注意：** 通常以全部大寫形式寫出常量，這也是 Redux 的標準做法。

# --hints--

調用函數 `loginUser` 應該返回一個 `type` 屬性設置爲字符串 `LOGIN` 的對象。

```js
assert(loginUser().type === 'LOGIN');
```

調用函數 `logoutUser` 應該返回一個 `type` 屬性設置爲字符串 `LOGOUT` 的對象。

```js
assert(logoutUser().type === 'LOGOUT');
```

store 應該用屬性 `login` 設置爲 `false` 的對象初始化。

```js
assert(store.getState().authenticated === false);
```

dispatch `loginUser` 以後應將 store 中的 state 的 `login` 值更新爲 `true`。

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

dispatch `logoutUser` 應將 store 中的 state 的 `login` 值更新爲 `false`。

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

`authReducer` 函數應該使用 switch 語句處理多個 action 類型。

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

`LOGIN` 和 `LOGOUT` 應該聲明爲 `const` 值，並且應該分配爲 `LOGIN` 和 `LOGOUT` 的字符串。

```js
const noWhiteSpace = __helpers.removeWhiteSpace(code);
assert(LOGIN === 'LOGIN' && LOGOUT === 'LOGOUT')
assert(noWhiteSpace.includes('const'))
```

action creator 和 reducer 中應該引用 `LOGIN` 和 `LOGOUT` 常量。

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
