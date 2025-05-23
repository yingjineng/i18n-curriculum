---
id: 5a24c314108439a4d4036152
title: 使用 const 声明 Action Types
challengeType: 6
forumTopicId: 301450
dashedName: use-const-for-action-types
---

# --description--

A common practice when working with Redux is to assign action types as read-only constants, then reference these constants wherever they are used. You can refactor the code you're working with to write the action types as `const` declarations.

# --instructions--

将 `LOGIN` 和 `LOGOUT` 声明为 `const` 的值，并为它们分别分配字符串 `'LOGIN'` 和 `'LOGOUT'`。 然后，编辑 `authReducer()` 和 action creators 来引用这些常量而不是字符串值。

**注意：** 通常以全部大写形式写出常量，这也是 Redux 的标准做法。

# --hints--

调用函数 `loginUser` 应该返回一个 `type` 属性设置为字符串 `LOGIN` 的对象。

```js
assert(loginUser().type === 'LOGIN');
```

调用函数 `logoutUser` 应该返回一个 `type` 属性设置为字符串 `LOGOUT` 的对象。

```js
assert(logoutUser().type === 'LOGOUT');
```

store 应该用属性 `login` 设置为 `false` 的对象初始化。

```js
assert(store.getState().authenticated === false);
```

dispatch `loginUser` 以后应将 store 中的 state 的 `login` 值更新为 `true`。

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

dispatch `logoutUser` 应将 store 中的 state 的 `login` 值更新为 `false`。

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

`authReducer` 函数应该使用 switch 语句处理多个 action 类型。

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

`LOGIN` 和 `LOGOUT` 应该声明为 `const` 值，并且应该分配为 `LOGIN` 和 `LOGOUT` 的字符串。

```js
const noWhiteSpace = __helpers.removeWhiteSpace(code);
assert(LOGIN === 'LOGIN' && LOGOUT === 'LOGOUT')
assert(noWhiteSpace.includes('const'))
```

action creator 和 reducer 中应该引用 `LOGIN` 和 `LOGOUT` 常量。

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
