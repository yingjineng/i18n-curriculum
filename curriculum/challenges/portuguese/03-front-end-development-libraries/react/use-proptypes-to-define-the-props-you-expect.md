---
id: 5a24c314108439a4d403616d
title: Usar propTypes para definir os props que você espera
challengeType: 6
forumTopicId: 301419
dashedName: use-proptypes-to-define-the-props-you-expect
---

# --description--

React provides useful type-checking features to verify that components receive props of the correct type. For example, your application makes an API call to retrieve data that you expect to be in an array, which is then passed to a component as a prop. You can set `propTypes` on your component to require the data to be of type `array`. This will throw a useful warning when the data is of any other type.

É considerada uma boa prática definir `propTypes` quando você sabe o tipo de uma "prop" antes do tempo. Você pode definir uma propriedade `propTypes` para um componente da mesma forma que você definiu `defaultProps`. Fazer isso verificará se as "props" de uma determinada chave estão presentes com um determinado tipo. Aqui está um exemplo para exigir o tipo `function` para uma propriedade chamada `handleClick`:

```js
MyComponent.propTypes = { handleClick: PropTypes.func.isRequired }
```

No exemplo acima, a parte `PropTypes.func` verifica se `handleClick` é uma função. Adicionar `isRequired` diz ao React que `handleClick` é uma propriedade necessária para esse componente. Você verá um aviso se essa propriedade não for fornecida. Também observe que `func` representa `function`. Entre os sete tipos primitivos de JavaScript, `function` e `boolean` (escrito como `bool`) são os únicos dois que usam ortografia incomum. Além dos tipos primitivos, existem outros tipos disponíveis. Por exemplo, você pode verificar que uma prop é um elemento React. Consulte a <a href="https://reactjs.org/docs/typechecking-with-proptypes.html#proptypes" target="_blank" rel="noopener noreferrer nofollow">documentação</a> para ver todas as opções.

**Observação:** a partir do React v15.5.0, `PropTypes` é importado independentemente do React, como: `import PropTypes from 'prop-types';`

# --instructions--

Defina `propTypes` para o componente `Items` para exigir `quantity` como uma propriedade e verifique se é do tipo `number`.

# --hints--

O componente `ShoppingCart` deve renderizar.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ShoppingCart));
    return mockedComponent.find('ShoppingCart').length === 1;
  })()
);
```

O componente `Items` deve renderizar.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ShoppingCart));
    return mockedComponent.find('Items').length === 1;
  })()
);
```

O componente `Items` deve incluir uma verificação de `propTypes` para exigir um valor para a `quantity` e garantir que o seu valor é um número.

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
