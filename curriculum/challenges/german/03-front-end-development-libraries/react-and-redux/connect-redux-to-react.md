---
id: 5a24c314108439a4d4036147
title: Redux mit React verbinden
challengeType: 6
forumTopicId: 301426
dashedName: connect-redux-to-react
---

# --description--

Now that you've written both the `mapStateToProps()` and the `mapDispatchToProps()` functions, you can use them to map `state` and `dispatch` to the `props` of one of your React components. The `connect` method from React Redux can handle this task. This method takes two optional arguments, `mapStateToProps()` and `mapDispatchToProps()`. They are optional because you may have a component that only needs access to `state` but doesn't need to dispatch any actions, or vice versa.

Um diese Methode zu verwenden, übergibst du die Funktionen als Argumente und rufst das Ergebnis sofort mit deiner Komponente auf. Diese Syntax ist ein wenig ungewöhnlich und sieht wie folgt aus:

```js
connect(mapStateToProps, mapDispatchToProps)(MyComponent)
```

**Hinweis:** Wenn du eines der Argumente für die Methode `connect` weglassen willst, übergibst du stattdessen `null`.

# --instructions--

Der Code-Editor enthält die Funktionen `mapStateToProps()` und `mapDispatchToProps()` und eine neue React-Komponente namens `Presentational`. Verbinde diese Komponente mit der `connect`-Methode aus dem globalen `ReactRedux`-Objekt mit Redux und rufe sie sofort in der `Presentational`-Komponente auf. Weise das Ergebnis einer neuen Konstanten (`const`) namens `ConnectedComponent` zu, die die verbundene Komponente darstellt. Das war's, jetzt bist du mit Redux verbunden! Versuche, eines der Argumente von `connect` in `null` zu ändern und beobachte die Testergebnisse.

# --hints--

Die Komponente `Presentational` sollte gerendert werden.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(AppWrapper));
    return mockedComponent.find('Presentational').length === 1;
  })()
);
```

Die Komponente `Presentational` sollte über `connect` eine Eigenschaft `messages` erhalten.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(AppWrapper));
    const props = mockedComponent.find('Presentational').props();
    return props.messages === '__INITIAL__STATE__';
  })()
);
```

Die Komponente `Presentational` sollte eine Eigenschaft`submitNewMessage` über `connect` erhalten.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(AppWrapper));
    const props = mockedComponent.find('Presentational').props();
    return typeof props.submitNewMessage === 'function';
  })()
);
```

# --seed--

## --after-user-code--

```jsx
const store = Redux.createStore(
  (state = '__INITIAL__STATE__', action) => state
);
class AppWrapper extends React.Component {
  render() {
    return (
      <ReactRedux.Provider store = {store}>
        <ConnectedComponent/>
      </ReactRedux.Provider>
    );
  }
};
ReactDOM.render(<AppWrapper />, document.getElementById('root'))
```

## --seed-contents--

```jsx
const addMessage = (message) => {
  return {
    type: 'ADD',
    message: message
  }
};

const mapStateToProps = (state) => {
  return {
    messages: state
  }
};

const mapDispatchToProps = (dispatch) => {
  return {
    submitNewMessage: (message) => {
      dispatch(addMessage(message));
    }
  }
};

class Presentational extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <h3>This is a Presentational Component</h3>
  }
};

const connect = ReactRedux.connect;
// Change code below this line
```

# --solutions--

```jsx
const addMessage = (message) => {
  return {
    type: 'ADD',
    message: message
  }
};

const mapStateToProps = (state) => {
  return {
    messages: state
  }
};

const mapDispatchToProps = (dispatch) => {
  return {
    submitNewMessage: (message) => {
      dispatch(addMessage(message));
    }
  }
};

class Presentational extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <h3>This is a Presentational Component</h3>
  }
};

const connect = ReactRedux.connect;
// Change code below this line

const ConnectedComponent = connect(mapStateToProps, mapDispatchToProps)(Presentational);
```
