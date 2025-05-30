---
id: 5a24c314108439a4d4036172
title: Renderizar estado na interface de usuário de outra forma
challengeType: 6
forumTopicId: 301408
dashedName: render-state-in-the-user-interface-another-way
---

# --description--

There is another way to access `state` in a component. In the `render()` method, before the `return` statement, you can write JavaScript directly. For example, you could declare functions, access data from `state` or `props`, perform computations on this data, and so on. Then, you can assign any data to variables, which you have access to in the `return` statement.

# --instructions--

No método de renderização do `MyComponent`, defina uma `const` chamada `name` e defina-a igual ao valor do nome no `state` do componente. Como você pode escrever JavaScript diretamente nesta parte do código, você não precisa incluir essa referência em chaves.

Em seguida, na instrução return, renderize este valor em uma tag `h1` usando a variável `name`. Lembre-se, você precisa usar a sintaxe JSX (chaves para JavaScript) na instrução de retorno.

# --hints--

`MyComponent` deve ter uma chave `name` com o valor `freeCodeCamp` armazenado no seu state.

```js
assert(
  Enzyme.mount(React.createElement(MyComponent)).state('name') ===
    'freeCodeCamp'
);
```

`MyComponent` deve renderizar um elemento de título `h1` que está dentro de um único `div`.

```js
assert(
  /<div><h1>.*<\/h1><\/div>/.test(
    Enzyme.mount(React.createElement(MyComponent)).html()
  )
);
```

A tag `h1` renderizada deve ter uma referência a `{name}`.

```js
assert(/<h1>\n*\s*\{\s*name\s*\}\s*\n*<\/h1>/.test(code));
```

O elemento de título `h1` renderizado deve conter apenas texto renderizado do estado do componente.

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
