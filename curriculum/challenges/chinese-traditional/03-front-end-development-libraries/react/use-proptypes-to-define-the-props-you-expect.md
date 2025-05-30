---
id: 5a24c314108439a4d403616d
title: 使用 PropTypes 來定義 Props 的類型
challengeType: 6
forumTopicId: 301419
dashedName: use-proptypes-to-define-the-props-you-expect
---

# --description--

React provides useful type-checking features to verify that components receive props of the correct type. For example, your application makes an API call to retrieve data that you expect to be in an array, which is then passed to a component as a prop. You can set `propTypes` on your component to require the data to be of type `array`. This will throw a useful warning when the data is of any other type.

當提前知道 prop 的類型時，最佳實踐是設置其 `propTypes`。 可以爲組件定義 `propTypes` 屬性，方法與定義 `defaultProps` 相同。 這樣做將檢查一個鍵的 prop 是否是給定類型。 這裏有一個示例，表示名爲 `handleClick` 的 prop 應爲 `function` 類型：

```js
MyComponent.propTypes = { handleClick: PropTypes.func.isRequired }
```

在上面的示例中，`PropTypes.func` 部分檢查 `handleClick` 是否爲函數。 添加 `isRequired`，告訴 React `handleClick` 是該組件的必需屬性。 如果沒有那個屬性，將出現警告。 還要注意 `func` 代表 `function` 。 在 7 種 JavaScript 原始類型中，`function` 和 `boolean`（寫爲 `bool` ）是唯一使用異常拼寫的兩種類型。 除了原始類型，還有其他類型可用。 例如，你可以檢查 prop 是否爲 React 元素。 請查看<a href="https://reactjs.org/docs/typechecking-with-proptypes.html#proptypes" target="_blank" rel="noopener noreferrer nofollow">文檔</a>以獲取所有選項。

**注意：**在 React v15.5.0 中, `PropTypes` 可以從 React 中單獨引入，例如：`import PropTypes from 'prop-types';`。

# --instructions--

爲 `Items` 組件定義 `propTypes`，以要求 `quantity` 作爲 prop，並驗證它是否爲 `number` 類型。

# --hints--

應該渲染 `ShoppingCart` 組件。

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ShoppingCart));
    return mockedComponent.find('ShoppingCart').length === 1;
  })()
);
```

應該渲染 `Items` 組件。

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ShoppingCart));
    return mockedComponent.find('Items').length === 1;
  })()
);
```

`Items` 組件應該包含一個 `propTypes` 檢查，要求 `quantity` 有一個值，並且這個值的類型是 number。

```js
const noWhiteSpace = __helpers.removeWhiteSpace(code);
assert(noWhiteSpace.includes('quantity:PropTypes.number.isRequired') && noWhiteSpace.includes('Items.propTypes='));
```

# --seed--

## --before-user-code--

```jsx
var PropTypes = {
  number: { isRequired: true }
};
```

## --after-user-code--

```jsx
ReactDOM.render(<ShoppingCart />, document.getElementById('root'))
```

## --seed-contents--

```jsx
const Items = (props) => {
  return <h1>Current Quantity of Items in Cart: {props.quantity}</h1>
};

// Change code below this line

// Change code above this line

Items.defaultProps = {
  quantity: 0
};

class ShoppingCart extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <Items />
  }
};
```

# --solutions--

```jsx
const Items = (props) => {
  return <h1>Current Quantity of Items in Cart: {props.quantity}</h1>
};

// Change code below this line
Items.propTypes = {
  quantity: PropTypes.number.isRequired
};
// Change code above this line

Items.defaultProps = {
  quantity: 0
};

class ShoppingCart extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <Items />
  }
};
```
