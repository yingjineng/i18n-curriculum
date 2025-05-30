---
id: 5a24c314108439a4d4036172
title: 以另一種方式在用戶界面中渲染狀態
challengeType: 6
forumTopicId: 301408
dashedName: render-state-in-the-user-interface-another-way
---

# --description--

There is another way to access `state` in a component. In the `render()` method, before the `return` statement, you can write JavaScript directly. For example, you could declare functions, access data from `state` or `props`, perform computations on this data, and so on. Then, you can assign any data to variables, which you have access to in the `return` statement.

# --instructions--

在 `MyComponent` 的 render 方法中，定義一個名爲 `name` 的 `const`（常量），並將其設置爲組件 `state` 中的 name 值。 因爲可以直接在代碼部分編寫 JavaScript，所以不需要用大括號括起來。

接下來，在 return 語句中，在 `h1` 標籤中渲染變量 `name` 的值。 記住，在 return 語句中需要使用 JSX 語法（用到 JavaScript 的花括號）。

# --hints--

`MyComponent` 應該有一個鍵 `name`，其值 `freeCodeCamp` 存儲在其 state 中。

```js
assert(
  Enzyme.mount(React.createElement(MyComponent)).state('name') ===
    'freeCodeCamp'
);
```

`MyComponent` 應該在 `div` 中渲染一個 `h1` 標題元素。

```js
assert(
  /<div><h1>.*<\/h1><\/div>/.test(
    Enzyme.mount(React.createElement(MyComponent)).html()
  )
);
```

渲染的 `h1` 標籤應該包含 `{name}` 的引用。

```js
assert(/<h1>\n*\s*\{\s*name\s*\}\s*\n*<\/h1>/.test(code));
```

渲染的 `h1` 標題元素應包含從組件狀態渲染的文本。

```js
async () => {
  const waitForIt = (fn) =>
    new Promise((resolve, reject) => setTimeout(() => resolve(fn()), 250));
  const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
  const first = () => {
    mockedComponent.setState({ name: 'TestName' });
    return waitForIt(() => mockedComponent.html());
  };
  const firstValue = await first();
  assert(firstValue === '<div><h1>TestName</h1></div>');
};
```

# --seed--

## --after-user-code--

```jsx
ReactDOM.render(<MyComponent />, document.getElementById('root'))
```

## --seed-contents--

```jsx
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'freeCodeCamp'
    }
  }
  render() {
    // Change code below this line

    // Change code above this line
    return (
      <div>
        { /* Change code below this line */ }

        { /* Change code above this line */ }
      </div>
    );
  }
};
```

# --solutions--

```jsx
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'freeCodeCamp'
    }
  }
  render() {
    // Change code below this line
    const name = this.state.name;
    // Change code above this line
    return (
      <div>
        { /* Change code below this line */ }
        <h1>{name}</h1>
        { /* Change code above this line */ }
      </div>
    );
  }
};
```
