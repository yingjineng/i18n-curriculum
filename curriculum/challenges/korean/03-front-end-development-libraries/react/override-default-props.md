---
id: 5a24c314108439a4d403616c
title: Props 기본값 덮어쓰기
challengeType: 6
forumTopicId: 301399
dashedName: override-default-props
---

# --description--

The ability to set default props is a useful feature in React. The way to override the default props is to explicitly set the prop values for a component.

# --instructions--

`ShoppingCart` 컴포넌트는 자식 컴포넌트인 `Items` 컴포넌트를 렌더링합니다. `Items` 컴포넌트는 정수 `0`를 가진 `quantity`프로퍼티가 기본값으로 설정되어 있습니다. `quantity`에 `10`을 전달해서 prop의 기본값을 덮어씌워보세요.

**참고:** 컴포넌트에 prop을 추가하는 문법은 HTML 속성을 추가하는 방법과 비슷합니다. 단, `quantity`의 값은 정수이므로, 따옴표가 아닌 중괄호로 묶어야 합니다. 예를 들면 `{100}`. 이 것은 JSX한테 중괄호 안의 값을 자바스크립트로 해석하라고 말해주는 겁니다.

# --hints--

`ShoppingCart` 컴포넌트가 렌더링되어야 합니다.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ShoppingCart));
    return mockedComponent.find('ShoppingCart').length === 1;
  })()
);
```

`Items` 컴포넌트가 렌더링되어야 합니다.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ShoppingCart));
    return mockedComponent.find('Items').length === 1;
  })()
);
```

`Items` 컴포넌트는 `ShoppingCart` 컴포넌트에서 전달받은 `{ quantity: 10 }` prop이 있어야 합니다.

```js
() =>
  assert(
    (function () {
      const mockedComponent = Enzyme.mount(React.createElement(ShoppingCart));
      return (
        mockedComponent.find('Items').props().quantity == 10 &&
        code.replace(/ /g, '')
          .includes('<Itemsquantity={10}/>')
      );
    })()
  );
```

# --seed--

## --after-user-code--

```jsx
ReactDOM.render(<ShoppingCart />, document.getElementById('root'))
```

## --seed-contents--

```jsx
const Items = (props) => {
  return <h1>Current Quantity of Items in Cart: {props.quantity}</h1>
}

Items.defaultProps = {
  quantity: 0
}

class ShoppingCart extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    { /* Change code below this line */ }
    return <Items />
    { /* Change code above this line */ }
  }
};
```

# --solutions--

```jsx
const Items = (props) => {
  return <h1>Current Quantity of Items in Cart: {props.quantity}</h1>
}

Items.defaultProps = {
  quantity: 0
}

class ShoppingCart extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    { /* Change code below this line */ }
    return <Items quantity = {10} />
    { /* Change code above this line */ }
  }
};
```
