---
id: 5a24c314108439a4d403616d
title: Usare i PropTypes per definire le Prop attese
challengeType: 6
forumTopicId: 301419
dashedName: use-proptypes-to-define-the-props-you-expect
---

# --description--

React provides useful type-checking features to verify that components receive props of the correct type. For example, your application makes an API call to retrieve data that you expect to be in an array, which is then passed to a component as a prop. You can set `propTypes` on your component to require the data to be of type `array`. This will throw a useful warning when the data is of any other type.

È considerata una buona pratica impostare `propTypes` quando si conosce il tipo di una prop in anticipo. Puoi definire una proprietà `propTypes` per un componente nello stesso modo in cui hai definito `defaultProps`. In questo modo verrà verificato che la prop con una data chiave sia presente con un dato tipo. Ecco un esempio per richiedere il tipo `function` per una prop chiamata `handleClick`:

```js
MyComponent.propTypes = { handleClick: PropTypes.func.isRequired }
```

Nell'esempio sopra, la parte `PropTypes.func` controlla che `handleClick` sia una funzione. Aggiungendo `isRequired` si dice a React che `handleClick` è una proprietà richiesta per quel componente. Se quella prop non è fornita vedrai un avviso. Nota anche che `func` rappresenta `function`. Tra i sette tipi primitivi JavaScript, `function` e `boolean` (scritto come `bool`) sono gli unici che usano un'ortografia insolita. Oltre ai tipi primitivi, ci sono altri tipi disponibili. Ad esempio, puoi controllare che una prop sia un elemento React. Fai riferimento alla <a href="https://reactjs.org/docs/typechecking-with-proptypes.html#proptypes" target="_blank" rel="noopener noreferrer nofollow">documentazione</a> per tutte le opzioni.

**Nota:** A partire da React v15.5.0, `PropTypes` viene importato indipendentemente da React, in questo modo: `import PropTypes from 'prop-types';`

# --instructions--

Definisci `propTypes` in modo che il componente `Items` richieda `quantity` come prop e verifica che sia di tipo `number`.

# --hints--

Il componente `ShoppingCart` dovrebbe essere presentato.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ShoppingCart));
    return mockedComponent.find('ShoppingCart').length === 1;
  })()
);
```

Il componente `Items` dovrebbe essere presentato.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(ShoppingCart));
    return mockedComponent.find('Items').length === 1;
  })()
);
```

Il componente `Items` dovrebbe includere un controllo di `propTypes` per richiedere un valore per `quantity` e assicurarsi che il suo valore sia un numero.

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
