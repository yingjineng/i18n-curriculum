---
id: 5a24c314108439a4d4036168
title: Scrivere un componente React da zero
challengeType: 6
forumTopicId: 301424
dashedName: write-a-react-component-from-scratch
---

# --description--

Now that you've learned the basics of JSX and React components, it's time to write a component on your own. React components are the core building blocks of React applications so it's important to become very familiar with writing them. Remember, a typical React component is an ES6 `class` which extends `React.Component`. It has a render method that returns HTML (from JSX) or `null`. This is the basic form of a React component. Once you understand this well, you will be prepared to start building more complex React projects.

# --instructions--

Definisci una classe `MyComponent` che estenda `React.Component`. Il suo metodo render dovrebbe restituire un `div` che contiene un tag `h1` con il testo: `My First React Component!` in esso. Usa questo testo esattamente, le maiuscole e la punteggiatura contano. Assicurati di chiamare anche il costruttore per il tuo componente.

Presenta questo componente nel DOM usando `ReactDOM.render()`. C'è un `div` con `id='challenge-node'` pronto all'uso per te.

# --hints--

Ci dovrebbe essere un componente React chiamato `MyComponent`.

```js
assert(__helpers.removeWhiteSpace(code).includes('classMyComponentextendsReact.Component{'));
```

`MyComponent` dovrebbe contenere un tag `h1` con testo `My First React Component!` Maiuscole e punteggiatura contano.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
    return mockedComponent.find('h1').text() === 'My First React Component!';
  })()
);
```

`MyComponent` dovrebbe essere presentato nel DOM.

```js
assert(document.getElementById('challenge-node').childNodes.length === 1);
```

`MyComponent` dovrebbe avere un costruttore che chiama `super` con `props`.

```js
assert(
  MyComponent.toString().includes('MyComponent(props)') &&
    MyComponent.toString().includes('_super.call(this, props)')
);
```

# --seed--

## --seed-contents--

```jsx
// Change code below this line
```

# --solutions--

```jsx
// Change code below this line
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>My First React Component!</h1>
      </div>
    );
  }
};

ReactDOM.render(<MyComponent />, document.getElementById('challenge-node'));
```
